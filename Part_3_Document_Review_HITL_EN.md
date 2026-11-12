# Part 3. Implementing Human-in-the-Loop (HITL) Review with LangChain 1.1

### Key Technology for Making AI Review Results Controllable and Subject to Human Intervention

![Original notebook illustration](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171917194.png)

In the previous lesson, we built a document review system using LangChain 1.1. The AI can identify issues and suggest changes. However, AI judgements are not always 100% correct. How can a human verify them?

This introduces **Human-in-the-Loop (HITL)**.

![HITL concept](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171544626.png)

Simply put, HITL inserts a **human confirmation step before AI executes a critical action**, allowing a person to review, edit, or reject the AI decision.

HITL is important in many AI applications:

| Scenario | AI role | Human intervention |
|---|---|---|
| Document review | Identify issues and suggest edits | Confirm issue validity and reasonableness of suggestions |
| Content moderation | Detect prohibited content | Confirm whether a violation exists and decide how to handle it |
| Code review | Find potential bugs | Decide whether and how to fix them |
| Customer service | Generate suggested responses | Check suitability or take over manually |
| Data annotation | Automatically label data | Review labels and correct errors |

This lesson covers HITL implementation in LangChain 1.1, including:

- `HumanInTheLoopMiddleware`.
- `create_agent()` for an interruptible Agent.
- `InMemorySaver` for state persistence.

## 1. Basic Environment Preparation

Before starting, configure the environment with the following dependencies:

| Library | Purpose | Explanation |
|---|---|---|
| `langchain` | LLM application framework | Agent and middleware APIs |
| `langgraph` | Graph execution engine | Underlying HITL support (`Checkpointer`, `Command`) |
| `langchain-openai` | OpenAI-compatible interface | Calls DeepSeek and compatible APIs |
| `pydantic` | Data validation | Defines data structures |

```python
%pip install langchain==1.1.3 langgraph langchain-openai pydantic python-dotenv -q
```

**Original notebook output:**

```text
[33mWARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager, possibly rendering your system unusable. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv. Use the --root-user-action option if you know what you are doing and want to suppress this warning.[0m[33m
[0mNote: you may need to restart the kernel to use updated packages.
```

```python
# 方式一：直接在代码中配置（仅用于学习，生产环境不推荐）
# DEEPSEEK_API_KEY = "your-deepseek-api-key-here"
# MINERU_API_KEY = "your-mineru-api-key-here"

# 方式二：使用环境变量（推荐）
import os
from dotenv import load_dotenv

# 加载 .env 文件中的环境变量
load_dotenv(override=True)

DEEPSEEK_API_KEY = os.getenv("DEEPSEEK_API_KEY")
MINERU_API_KEY = os.getenv("MINERU_API_KEY")

# 验证配置
print(f"DeepSeek API Key 已配置: {DEEPSEEK_API_KEY[:10]}")
print(f"MinerU API Key 已配置: {MINERU_API_KEY[:10]}")
```

**Original notebook output:**

```text
DeepSeek API Key 已配置: sk-04a9c72
MinerU API Key 已配置: eyJ0eXBlIj
```

## 2. Core HITL Concepts

Before developing the Agent, understand the central HITL concepts. When an AI action is interrupted for human review, three decisions are possible:

| Decision | Name | Data structure | Subsequent action |
|---|---|---|---|
| **Approve** | `approve` | `{"type": "approve"}` | Execute the original AI-proposed action |
| **Edit** | `edit` | `{"type": "edit", "edited_action": {...}}` | Execute with the edited parameters |
| **Reject** | `reject` | `{"type": "reject", "message": "..."}` | Cancel the action; do not execute |

A key challenge is **preserving state during an interruption**. For example:

1. A user submits a review request at 9:00 AM.
2. The AI analyses it, interrupts execution, and waits for confirmation.
3. A reviewer responds at 2:00 PM.

During those five hours, the system must remember its earlier state. This requires a **Checkpointer**:

```text
Checkpointer state preservation
thread_id: "issue:abc123:xyz789"
State 0 (Start) → State 1 (Interrupted) → State 2 (Resumed) → ...
Saved information:
- Current execution position
- AI-proposed action
- Relevant contextual information
```

This lesson uses `InMemorySaver` (in-memory checkpoints). In production, checkpoints can be stored in a database.

LangChain 1.1 provides **`HumanInTheLoopMiddleware`** for this workflow. The pseudocode is:

```python
from langchain.agents import create_agent
from langchain.agents.middleware import HumanInTheLoopMiddleware
from langgraph.checkpoint.memory import InMemorySaver

agent = create_agent(
    model=llm,
    tools=[my_tool],
    middleware=[HumanInTheLoopMiddleware(
        interrupt_on={"my_tool": True},  # Interrupt before calling my_tool
    )],
    checkpointer=InMemorySaver(),
)
```

Advantages:

- **Declarative configuration:** Specify only which tools require human confirmation.
- **Automatic state management:** Middleware handles saving and resuming state.
- **Standardised decisions:** `approve`, `edit`, and `reject`.

## 3. Implementing HITL with LangChain 1.1

Build an HITL-enabled Agent from scratch using a simple **document issue review** scenario:

1. The AI detects an issue in a document.
2. The user wants to accept or not accept the issue.
3. Human confirmation is required before updating the database.

### 3.1 Define the Data Structure

First define the `Issue` data structure, the central object that the system will operate on:

```python
# 我们使用 Pydantic 定义问题（Issue）的数据结构

from pydantic import BaseModel, Field
from typing import Dict, Any, Optional, List
from enum import Enum
from datetime import datetime
import uuid

# 问题状态枚举
class IssueStatus(str, Enum):
    not_reviewed = "not_reviewed"  # 未审核
    accepted = "accepted"          # 已采纳
    dismissed = "dismissed"        # 已忽略

# 问题数据结构
class Issue(BaseModel):
    id: str = Field(default_factory=lambda: str(uuid.uuid4()))
    doc_id: str                           # 文档 ID
    text: str                             # 问题文本
    type: str                             # 问题类型
    status: IssueStatus = IssueStatus.not_reviewed
    explanation: str = ""                 # 问题解释
    suggested_fix: str = ""               # 修改建议
    resolved_by: Optional[str] = None     # 处理人
    resolved_at: Optional[str] = None     # 处理时间
```

Next create a test example:

```python
# 创建一个示例问题（模拟 AI 发现的问题）
sample_issue = Issue(
    doc_id="doc_001",
    text="我们保证100%的投资回报率",
    type="Definitive Language",
    explanation="使用了绝对化表述'保证100%'，可能造成法律风险",
    suggested_fix="建议修改为'预期投资回报率可达'",
)

print("="*60)
print("示例问题")
print("="*60)
print(f"ID: {sample_issue.id}")
print(f"文档: {sample_issue.doc_id}")
print(f"问题文本: {sample_issue.text}")
print(f"问题类型: {sample_issue.type}")
print(f"当前状态: {sample_issue.status.value}")
print(f"解释: {sample_issue.explanation}")
print(f"建议: {sample_issue.suggested_fix}")
print("="*60)
```

**Original notebook output:**

```text
============================================================
示例问题
============================================================
ID: 205508d5-346d-459b-824c-52a93d9b47dd
文档: doc_001
问题文本: 我们保证100%的投资回报率
问题类型: Definitive Language
当前状态: not_reviewed
解释: 使用了绝对化表述'保证100%'，可能造成法律风险
建议: 建议修改为'预期投资回报率可达'
============================================================
```

### 3.2 Create a Mock Database

In a real project, issues would be stored in a database. This demonstration uses a simple in-memory mock database:

```python
# 这是一个简单的内存数据库，用于存储和更新问题

class IssuesDatabase:
    """
    模拟的问题数据库
    在实际项目中，这会是 SQLite/PostgreSQL 等真实数据库
    """
    
    def __init__(self):
        self._issues: Dict[str, Issue] = {}
    
    def add_issue(self, issue: Issue) -> None:
        """添加问题"""
        self._issues[issue.id] = issue
        print(f"问题已添加到数据库: {issue.id}")
    
    def get_issue(self, issue_id: str) -> Optional[Issue]:
        """获取问题"""
        return self._issues.get(issue_id)
    
    def update_issue(self, issue_id: str, update_fields: Dict[str, Any]) -> Issue:
        """
        更新问题
        这是 HITL 要保护的关键操作
        """
        issue = self._issues.get(issue_id)
        if not issue:
            raise ValueError(f"问题不存在: {issue_id}")
        
        # 更新字段
        issue_dict = issue.model_dump()
        issue_dict.update(update_fields)
        
        # 创建更新后的 Issue
        updated_issue = Issue(**issue_dict)
        self._issues[issue_id] = updated_issue
        
        print(f"问题已更新: {issue_id}")
        print(f"   更新的字段: {list(update_fields.keys())}")
        
        return updated_issue
    
    def list_issues(self) -> List[Issue]:
        """列出所有问题"""
        return list(self._issues.values())

# 创建数据库实例并添加示例问题
db = IssuesDatabase()
db.add_issue(sample_issue)

# 保存问题 ID 供后续使用
ISSUE_ID = sample_issue.id

print(f"\n数据库中共有 {len(db.list_issues())} 个问题")
```

**Original notebook output:**

```text
问题已添加到数据库: 205508d5-346d-459b-824c-52a93d9b47dd

数据库中共有 1 个问题
```

### 3.3 Initialise the LLM

Initialise the LLM driving the Agent, using DeepSeek-v3.2:

```python
from langchain_openai import ChatOpenAI

# 检查 API Key
if not DEEPSEEK_API_KEY:
    raise ValueError("DEEPSEEK_API_KEY 未配置，请先设置环境变量")

# 初始化 DeepSeek LLM
llm = ChatOpenAI(
    api_key=DEEPSEEK_API_KEY,
    base_url="https://api.deepseek.com",
    model="deepseek-chat",
    temperature=0.2,
)

print("LLM 初始化完成")
```

**Original notebook output:**

```text
LLM 初始化完成
```

### 2.5 Create the HITL Agent (Core Code)

This is the central part of the lesson. To build the HITL Agent:

1. **Define a tool:** `update_issue` updates an issue.
2. **Configure middleware:** `HumanInTheLoopMiddleware` interrupts before tool execution.
3. **Configure checkpoints:** `InMemorySaver` preserves execution state.
4. **Create the Agent:** Assemble the components using `create_agent()`.

```python
import json
from langchain.agents import create_agent
from langchain.agents.middleware import HumanInTheLoopMiddleware
from langchain_core.messages import HumanMessage
from langgraph.checkpoint.memory import InMemorySaver
from langgraph.types import Command

# -----------------------------
# Step 1: 定义工具函数
# -----------------------------
# 这个函数会被 HITL 中间件拦截
# 在执行前会触发中断，等待人工确认

def update_issue(issue_id: str, update_fields: Dict[str, Any]) -> str:
    """
    更新问题（需要人工确认）
    
    Args:
        issue_id: 要更新的问题 ID
        update_fields: 要更新的字段字典
    
    Returns:
        "ok" 表示更新成功
    """
    # 实际执行数据库更新
    db.update_issue(issue_id, update_fields)
    return "ok"

# -----------------------------
# Step 2: 创建 HITL Agent
# -----------------------------

# System Prompt：告诉 AI 它的角色和任务
SYSTEM_PROMPT = """你是一个审阅工作流执行器。
你会收到 issue_id 和 update_fields。
你必须且只能调用一次 `update_issue` 工具，并严格使用提供的参数。
不要自行猜测、不要新增字段、不要修改字段含义。
"""

# 创建支持 HITL 的 Agent
hitl_agent = create_agent(
    model=llm,
    tools=[update_issue],  # 注册工具
    system_prompt=SYSTEM_PROMPT,
    middleware=[
        # 配置 HITL 中间件
        HumanInTheLoopMiddleware(
            interrupt_on={
                "update_issue": True,  # 在调用 update_issue 前触发中断
            },
            description_prefix="需要人工确认的操作",
        ),
    ],
    checkpointer=InMemorySaver(),  # 使用内存检查点保存状态
)

print("="*60)
print("HITL Agent 创建完成")
print("="*60)
print("配置说明:")
print("   - 工具: update_issue (更新问题)")
print("   - 中间件: HumanInTheLoopMiddleware")
print("   - 触发中断: 调用 update_issue 前")
print("   - 状态保存: InMemorySaver (内存检查点)")
print("="*60)
```

**Original notebook output:**

```text
============================================================
HITL Agent 创建完成
============================================================
配置说明:
   - 工具: update_issue (更新问题)
   - 中间件: HumanInTheLoopMiddleware
   - 触发中断: 调用 update_issue 前
   - 状态保存: InMemorySaver (内存检查点)
============================================================
```

## 4. HITL Execution Tests

Demonstrate the complete HITL workflow by simulating a user accepting an issue. First wrap two core functions:

- `start_hitl()`: Start HITL and trigger an interruption.
- `resume_hitl()`: Resume execution according to the human decision.

```python
async def start_hitl(
    thread_id: str,
    issue_id: str,
    update_fields: Dict[str, Any]
) -> Dict[str, Any]:
    """
    启动 HITL 流程
    
    Args:
        thread_id: 唯一标识本次 HITL 流程
        issue_id: 要更新的问题 ID
        update_fields: 要更新的字段
    
    Returns:
        中断信息（包含 interrupt_id 和提议的操作）
    """
    # 配置（thread_id 用于检索检查点）
    config = {"configurable": {"thread_id": thread_id}}
    
    # 构建提示词，告诉 Agent 要执行什么操作
    prompt = (
        "请按照提供的参数更新 issue。\n"
        f"issue_id: {issue_id}\n"
        f"update_fields(JSON): {json.dumps(update_fields, ensure_ascii=False)}\n"
        "你必须调用 update_issue。\n"
    )
    
    # 运行 Agent，直到遇到中断
    async for step in hitl_agent.astream(
        {"messages": [HumanMessage(content=prompt)]},
        config,
        stream_mode="values"
    ):
        # 检查是否有中断
        if "__interrupt__" in step:
            interrupt = step["__interrupt__"][0]
            try:
                return {
                    "id": interrupt.id,
                    "value": interrupt.value,
                    "thread_id": thread_id,
                }
            except AttributeError:
                return {
                    "value": interrupt,
                    "thread_id": thread_id,
                }
    
    # 如果没有中断（不应该发生），返回 None
    return None


async def resume_hitl(
    thread_id: str,
    decision: Dict[str, Any],
    interrupt_id: str = None
) -> None:
    """
    根据人工决策恢复 HITL 流程
    
    Args:
        thread_id: HITL 流程的 thread_id
        decision: 人工决策，格式：
            - 批准: {"type": "approve"}
            - 修改: {"type": "edit", "edited_action": {...}}
            - 拒绝: {"type": "reject", "message": "..."}
        interrupt_id: 中断 ID（可选）
    """
    config = {"configurable": {"thread_id": thread_id}}
    
    # 使用 Command 恢复执行
    cmd = Command(resume={"decisions": [decision]})
    
    # 继续执行直到完成
    async for step in hitl_agent.astream(cmd, config, stream_mode="values"):
        # 检查是否有新的中断（不应该发生）
        if "__interrupt__" in step:
            raise RuntimeError("HITL 恢复后产生了新的中断（异常情况）")
    
    print("HITL 流程已完成")


print("="*60)
print("HITL 操作函数已定义")
print("="*60)
print("start_hitl(thread_id, issue_id, update_fields)")
print("   - 启动 HITL 流程，触发中断")
print("   - 返回中断信息（包含 thread_id 用于后续恢复）")
print("")
print("resume_hitl(thread_id, decision, interrupt_id)")
print("   - 根据人工决策恢复执行")
print("   - decision: approve/edit/reject")
print("="*60)
```

**Original notebook output:**

```text
============================================================
HITL 操作函数已定义
============================================================
start_hitl(thread_id, issue_id, update_fields)
   - 启动 HITL 流程，触发中断
   - 返回中断信息（包含 thread_id 用于后续恢复）

resume_hitl(thread_id, decision, interrupt_id)
   - 根据人工决策恢复执行
   - decision: approve/edit/reject
============================================================
```

### 4.1 Scenario 1: Approve

The most common scenario: after review, a person agrees with the AI proposal and approves execution.

```python
# 用户想要「采纳」一个问题，将其状态改为 accepted

from datetime import datetime, timezone

# 查看问题当前状态
print("="*60)
print("Step 1: 查看问题当前状态")
print("="*60)
current_issue = db.get_issue(ISSUE_ID)
print(f"问题 ID: {current_issue.id}")
print(f"当前状态: {current_issue.status.value}")
print(f"处理人: {current_issue.resolved_by or '(无)'}")

# 准备更新字段
update_fields = {
    "status": IssueStatus.accepted.value,
    "resolved_by": "user_001",
    "resolved_at": datetime.now(timezone.utc).isoformat(),
}

print(f"\n准备更新的字段:")
for key, value in update_fields.items():
    print(f"   {key}: {value}")
```

**Original notebook output:**

```text
============================================================
Step 1: 查看问题当前状态
============================================================
问题 ID: 205508d5-346d-459b-824c-52a93d9b47dd
当前状态: not_reviewed
处理人: (无)

准备更新的字段:
   status: accepted
   resolved_by: user_001
   resolved_at: 2025-12-17T11:00:13.381728+00:00
```

```python
# ============================================================
# Step 2: 启动 HITL 流程（触发中断）
# ============================================================

# 生成唯一的 thread_id
thread_id = f"issue:{ISSUE_ID}:{uuid.uuid4()}"

print("="*60)
print("Step 2: 启动 HITL 流程")
print("="*60)
print(f"thread_id: {thread_id}")
print("正在启动 Agent...")

# 启动 HITL（这会触发中断）
interrupt_info = await start_hitl(
    thread_id=thread_id,
    issue_id=ISSUE_ID,
    update_fields=update_fields,
)

if interrupt_info:
    print("\n⏸中断已触发！等待人工决策...")
    print(f"\n中断信息:")
    print(f"   thread_id: {interrupt_info.get('thread_id')}")
    print(f"   interrupt_id: {interrupt_info.get('id', '(无)')}")
    print(f"\nAI 提议的操作:")
    print(f"   工具: update_issue")
    print(f"   参数: issue_id={ISSUE_ID}")
    print(f"   更新字段: {update_fields}")
else:
    print("未触发中断（异常情况）")

print("="*60)
```

**Original notebook output:**

```text
============================================================
Step 2: 启动 HITL 流程
============================================================
thread_id: issue:205508d5-346d-459b-824c-52a93d9b47dd:e4366a97-814a-4825-8e1c-39327fe1ed0a
正在启动 Agent...

⏸中断已触发！等待人工决策...

中断信息:
   thread_id: issue:205508d5-346d-459b-824c-52a93d9b47dd:e4366a97-814a-4825-8e1c-39327fe1ed0a
   interrupt_id: 603e551ad1b9d24f5ea0fbc87429118d

AI 提议的操作:
   工具: update_issue
   参数: issue_id=205508d5-346d-459b-824c-52a93d9b47dd
   更新字段: {'status': 'accepted', 'resolved_by': 'user_001', 'resolved_at': '2025-12-17T11:00:13.381728+00:00'}
============================================================
```

```python
# ============================================================
# Step 3: 人工决策 - 批准（Approve）
# ============================================================
# 模拟审核员查看 AI 提议后，选择「批准」

print("="*60)
print("Step 3: 人工决策 - 批准")
print("="*60)
print("审核员查看了 AI 的提议：")
print(f"   - 操作: 将问题状态改为 'accepted'")
print(f"   - 处理人: user_001")
print("")
print("审核员决定: 批准")

# 构建批准决策
approve_decision = {"type": "approve"}
print(f"\n决策数据: {approve_decision}")

# 恢复执行
print("\n恢复执行中...")
await resume_hitl(
    thread_id=thread_id,
    decision=approve_decision,
    interrupt_id=interrupt_info.get("id") if interrupt_info else None,
)

# 检查更新结果
print("\n" + "="*60)
print("Step 4: 检查更新结果")
print("="*60)
updated_issue = db.get_issue(ISSUE_ID)
print(f"问题 ID: {updated_issue.id}")
print(f"状态: {updated_issue.status.value} {'' if updated_issue.status == IssueStatus.accepted else ''}")
print(f"处理人: {updated_issue.resolved_by}")
print(f"处理时间: {updated_issue.resolved_at}")
print("="*60)
print("\nHITL 批准流程演示完成！")
```

**Original notebook output:**

```text
============================================================
Step 3: 人工决策 - 批准
============================================================
审核员查看了 AI 的提议：
   - 操作: 将问题状态改为 'accepted'
   - 处理人: user_001

审核员决定: 批准

决策数据: {'type': 'approve'}

恢复执行中...
问题已更新: 205508d5-346d-459b-824c-52a93d9b47dd
   更新的字段: ['status', 'resolved_by', 'resolved_at']
HITL 流程已完成

============================================================
Step 4: 检查更新结果
============================================================
问题 ID: 205508d5-346d-459b-824c-52a93d9b47dd
状态: accepted 
处理人: user_001
处理时间: 2025-12-17T11:00:13.381728+00:00
============================================================

HITL 批准流程演示完成！
```

### 4.2 Scenario 2: Edit

A reviewer may wish to modify the parameters proposed by the AI, such as changing the assignee or adding notes.

```python
# ============================================================
# 演示场景 2：修改（Edit）
# ============================================================
# 添加一个新问题用于演示修改场景

# 创建新问题
sample_issue_2 = Issue(
    doc_id="doc_002",
    text="本产品绝对安全可靠",
    type="Definitive Language",
    explanation="使用了绝对化表述'绝对'",
    suggested_fix="建议修改为'本产品经过严格测试'",
)

db.add_issue(sample_issue_2)
ISSUE_ID_2 = sample_issue_2.id

# 准备原始更新字段
original_update = {
    "status": IssueStatus.dismissed.value,  # 原本要忽略
    "resolved_by": "user_002",
    "resolved_at": datetime.now(timezone.utc).isoformat(),
}

# 启动 HITL
thread_id_2 = f"issue:{ISSUE_ID_2}:{uuid.uuid4()}"

print("="*60)
print("演示场景 2：修改（Edit）")
print("="*60)
print(f"原始提议: 将问题状态改为 '{IssueStatus.dismissed.value}'")

# 启动 HITL
interrupt_info_2 = await start_hitl(
    thread_id=thread_id_2,
    issue_id=ISSUE_ID_2,
    update_fields=original_update,
)

print("\n中断已触发...")
print("\n审核员查看后决定: 修改")
print("   - 原始操作: 忽略问题 (dismissed)")
print("   - 修改后: 采纳问题 (accepted)")

# 构建修改决策
edit_decision = {
    "type": "edit",
    "edited_action": {
        "name": "update_issue",
        "args": {
            "issue_id": ISSUE_ID_2,
            "update_fields": {
                "status": IssueStatus.accepted.value,  # 改为采纳
                "resolved_by": "supervisor_001",       # 修改处理人
                "resolved_at": datetime.now(timezone.utc).isoformat(),
            }
        }
    }
}

print(f"\n修改后的决策:")
print(f"   状态: {IssueStatus.dismissed.value} → {IssueStatus.accepted.value}")
print(f"   处理人: user_002 → supervisor_001")

# 恢复执行
print("\n恢复执行中...")
await resume_hitl(
    thread_id=thread_id_2,
    decision=edit_decision,
)

# 检查结果
updated_issue_2 = db.get_issue(ISSUE_ID_2)
print(f"\n最终结果:")
print(f"   状态: {updated_issue_2.status.value}")
print(f"   处理人: {updated_issue_2.resolved_by}")
print("="*60)
```

**Original notebook output:**

```text
问题已添加到数据库: 1d1e858c-ff57-4d7d-9ffd-3f475ff5d276
============================================================
演示场景 2：修改（Edit）
============================================================
原始提议: 将问题状态改为 'dismissed'

中断已触发...

审核员查看后决定: 修改
   - 原始操作: 忽略问题 (dismissed)
   - 修改后: 采纳问题 (accepted)

修改后的决策:
   状态: dismissed → accepted
   处理人: user_002 → supervisor_001

恢复执行中...
问题已更新: 1d1e858c-ff57-4d7d-9ffd-3f475ff5d276
   更新的字段: ['status', 'resolved_by', 'resolved_at']
HITL 流程已完成

最终结果:
   状态: accepted
   处理人: supervisor_001
============================================================
```

### 4.3 Scenario 3: Reject

A reviewer may disagree completely with the AI judgement and reject the operation. In this case, no update is executed.

```python
# ============================================================
# 演示场景 3：拒绝（Reject）
# ============================================================
# 审核员完全不同意操作，选择拒绝

# 创建新问题
sample_issue_3 = Issue(
    doc_id="doc_003",
    text="请按时提交报告",
    type="Grammar & Spelling",
    explanation="疑似语法问题",
    suggested_fix="无需修改",
)
db.add_issue(sample_issue_3)
ISSUE_ID_3 = sample_issue_3.id

# 记录原始状态
original_status = sample_issue_3.status.value

# 准备更新字段
reject_update = {
    "status": IssueStatus.accepted.value,
    "resolved_by": "user_003",
    "resolved_at": datetime.now(timezone.utc).isoformat(),
}

# 启动 HITL
thread_id_3 = f"issue:{ISSUE_ID_3}:{uuid.uuid4()}"

print("="*60)
print("演示场景 3：拒绝（Reject）")
print("="*60)
print(f"原始提议: 将问题状态改为 '{IssueStatus.accepted.value}'")
print(f"问题原始状态: '{original_status}'")

# 启动 HITL
interrupt_info_3 = await start_hitl(
    thread_id=thread_id_3,
    issue_id=ISSUE_ID_3,
    update_fields=reject_update,
)

print("\n中断已触发...")
print("\n审核员查看后决定: 拒绝")
print("   原因: 这不是真正的语法问题，AI 判断有误")

# 构建拒绝决策
reject_decision = {
    "type": "reject",
    "message": "这不是真正的语法问题，AI 判断有误，无需采纳"
}

print(f"\n拒绝决策: {reject_decision}")

# 恢复执行（拒绝时不会执行工具）
print("\n恢复执行中...")
await resume_hitl(
    thread_id=thread_id_3,
    decision=reject_decision,
)

# 检查结果 - 状态应该保持不变
final_issue_3 = db.get_issue(ISSUE_ID_3)
print(f"\n最终结果:")
print(f"   状态: {final_issue_3.status.value}")
print(f"   处理人: {final_issue_3.resolved_by or '(无)'}")

if final_issue_3.status.value == original_status:
    print("\n拒绝成功！问题状态保持不变。")
else:
    print("\n状态发生了变化（可能是实现差异）")

print("="*60)
```

**Original notebook output:**

```text
问题已添加到数据库: 1ab1ec30-f275-45de-adc7-cf5a258df31c
============================================================
演示场景 3：拒绝（Reject）
============================================================
原始提议: 将问题状态改为 'accepted'
问题原始状态: 'not_reviewed'

中断已触发...

审核员查看后决定: 拒绝
   原因: 这不是真正的语法问题，AI 判断有误

拒绝决策: {'type': 'reject', 'message': '这不是真正的语法问题，AI 判断有误，无需采纳'}

恢复执行中...
HITL 流程已完成

最终结果:
   状态: not_reviewed
   处理人: (无)

拒绝成功！问题状态保持不变。
============================================================
```

## Complete HITL Workflow Diagram (Original Source)

The following is the complete original architecture diagram, retained without alteration so no details are lost. Its Chinese labels remain as they appeared in the notebook.


&emsp;&emsp;一张**完整的 HITL 流程架构图**如下所示：

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                            HITL 完整工作流程                                   │
└─────────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────────┐
│                         Phase 1: 启动阶段 (Start)                               │
│                                                                                  │
│   用户请求                                                                       │
│      │                                                                          │
│      ▼                                                                          │
│   ┌──────────────────────────────────────────────────────────────────────┐     │
│   │  1. 接收更新请求                                                      │     │
│   │     - issue_id: 要更新的问题 ID                                       │     │
│   │     - update_fields: 要更新的字段（如 status, explanation 等）        │     │
│   │     - thread_id: 唯一标识本次 HITL 流程                               │     │
│   └──────────────────────────────────────────────────────────────────────┘     │
│      │                                                                          │
│      ▼                                                                          │
│   ┌──────────────────────────────────────────────────────────────────────┐     │
│   │  2. AI Agent 准备执行                                                 │     │
│   │     - Agent 接收到工具调用请求                                        │     │
│   │     - 工具: update_issue(issue_id, update_fields)                     │     │
│   │     - 但由于配置了 HumanInTheLoopMiddleware，会触发中断               │     │
│   └─────────────────────────────────────────────────────────────────────┘     │
│      │                                                                          │
│      ▼                                                                          │
│   ┌──────────────────────────────────────────────────────────────────────┐     │
│   │  3. 触发中断 (Interrupt)                                              │     │
│   │     - 保存当前状态到 Checkpointer                                     │     │
│   │     - 返回 interrupt 对象，包含:                                      │     │
│   │       • interrupt_id: 中断标识符                                      │     │
│   │       • proposed_action: AI 提议的操作                                │     │
│   │       • thread_id: 用于后续恢复的线程标识                             │     │
│   └──────────────────────────────────────────────────────────────────────┘     │
└─────────────────────────────────────────────────────────────────────────────────┘
                                        │
                    ⏸系统暂停，等待人工决策
                                        │
                                        ▼
┌─────────────────────────────────────────────────────────────────────────────────┐
│                         Phase 2: 人工决策阶段                                    │
│                                                                                  │
│   审核员查看 AI 提议的操作，做出以下三种决策之一：                                │
│                                                                                  │
│   ┌───────────────────┬───────────────────┬───────────────────┐                 │
│   │    ✅ 批准         │    ✏️ 修改         │    ❌ 拒绝         │                 │
│   │    (approve)      │    (edit)         │    (reject)       │                 │
│   ├───────────────────┼───────────────────┼───────────────────┤                 │
│   │ 同意 AI 的提议    │ 修改 AI 的提议    │ 拒绝 AI 的提议    │                 │
│   │ 按原计划执行      │ 按修改后的执行    │ 取消操作          │                 │
│   └───────────────────┴───────────────────┴───────────────────┘                 │
│                                                                                  │
│   决策数据结构:                                                                   │
│   • approve: {"type": "approve"}                                                │
│   • edit:    {"type": "edit", "edited_action": {...}}                           │
│   • reject:  {"type": "reject", "message": "拒绝原因"}                          │
│                                                                                  │
└─────────────────────────────────────────────────────────────────────────────────┘
                                        │
                                        ▼
┌─────────────────────────────────────────────────────────────────────────────────┐
│                         Phase 3: 恢复阶段 (Resume)                              │
│                                                                                  │
│   ┌──────────────────────────────────────────────────────────────────────┐     │
│   │  1. 恢复执行                                                          │     │
│   │     - 使用 thread_id 从 Checkpointer 加载之前保存的状态               │     │
│   │     - 使用 Command(resume={"decisions": [decision]}) 恢复执行         │     │
│   └──────────────────────────────────────────────────────────────────────┘     │
│      │                                                                          │
│      ▼                                                                          │
│   ┌──────────────────────────────────────────────────────────────────────┐     │
│   │  2. 根据决策类型处理                                                  │     │
│   │                                                                       │     │
│   │     ┌─ approve → 执行原始工具调用 → 更新数据库                        │     │
│   │     │                                                                 │     │
│   │     ├─ edit    → 执行修改后的工具调用 → 更新数据库                    │     │
│   │     │                                                                 │     │
│   │     └─ reject  → 跳过工具调用 → 不做任何更改                          │     │
│   └──────────────────────────────────────────────────────────────────────┘     │
│      │                                                                          │
│      ▼                                                                          │
│   ┌──────────────────────────────────────────────────────────────────────┐     │
│   │  3. 返回最终结果                                                      │     │
│   │     - 返回更新后的 Issue 对象                                         │     │
│   │     - 或返回拒绝消息（如果是 reject）                                 │     │
│   └──────────────────────────────────────────────────────────────────────┘     │
└─────────────────────────────────────────────────────────────────────────────────┘
```
