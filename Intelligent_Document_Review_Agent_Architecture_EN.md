<!-- English translation of the uploaded notebook. Source only; original image and video URLs retained. -->


# Part 1. Overview of the Technical Architecture of an Intelligent Document Review Agent

## From Technology Selection to Product Implementation

```python
from IPython.display import Video

Video("https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171715947.mp4", width=1500, height=400)
```

**In this public course, we will explore in depth the technical solution for a document review agent based on large language models.**

- **Overview of document review agent system functions**

Core function 1: Supports online upload and parsing of `.pdf` files, with rapid extensibility to `.doc`, `.docx`, `.ppt`, `.pptx`, `.png`, `.jpg`, `.jpeg`, and other formats.

![Original source illustration 5.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171217557.png)

Core function 2: Supports highly accurate extraction of text content and positional information from structured data, with highlighted display.

![Original source illustration 6.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171724269.png)

Core function 3: Supports human–machine interaction, allowing reviewers to intervene at any point in the review process and provide review comments.

![Original source illustration 7.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171727069.png)

Core function 4: Supports online custom rules for individual files, immediate re-review, and persistent data management.

![Original source illustration 8.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171729773.png)

Developing this intelligent document review system requires core agent development technologies, comprising the following technical modules:

![Original source illustration 9.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171741927.png)

# 1. Introduction to Mature AI Products for Document Review

First, consider the data presented in the following paper. It compares legal large language models with traditional legal contract reviewers, junior lawyers, and legal process outsourcing providers, examining accuracy, speed, and cost-effectiveness in contract review. The experimental results indicate that advanced LLMs can match or exceed human accuracy in identifying legal issues. Reviews take seconds rather than hours, and operating costs are reported to be 99.97% lower than traditional approaches.

> Paper: https://arxiv.org/pdf/2401.16212

![Original source illustration 11.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202511171625258.png)

As LLM capabilities improve, using them as intelligent agents to review professional documents for compliance has moved from theory to practice, delivering substantial efficiency improvements across industries.

**Document compliance review** means checking the content and formatting of professional documents against laws and regulations, industry standards, or internal corporate rules to identify potential violations or defects. Typical examples include legal compliance checks of contracts, validation of financial documents, and rule-compliance checks of tenders and official documents with specified formats. The following are examples of deployed domestic document review products:

- **Alibaba Tongyi Farui**: Identifies potential contract risks and provides professional risk assessments and revision suggestions. Demo: https://tongyi.aliyun.com/farui/review



![Original source illustration 14.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202511171645949.png)

- **Baidu OCR recognition and automatic review for financial, medical, and educational documents**: https://ai.baidu.com/tech/ocr_receipts/vat_invoice



![Original source illustration 16.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202511171631930.png)

- **Langcore Technology digital employees (document review)**: https://langcore.cn/zh



![Original source illustration 18.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202511171634735.png)

Detailed explanations of reproducing the above review systems are available in the author’s previous public courses:



![Original source illustration 20.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171209858.png)

The frontend and backend source code has been uploaded to Baidu Netdisk and can be downloaded free by scanning the QR code:

![Original source illustration 21.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202511281211724.png)



![Original source illustration 22.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171342119.png)

Document compliance review agents of this kind are intelligent agent systems built on LLMs. They automatically check professional documents for content and formatting against laws, industry standards, and internal corporate rules, identifying potential violations or defects and reducing time-consuming manual review. Typical applications include:

| Scenario | Review content | Core value | Difficulty |
|---|---|---|---|
| **Legal contract review** | Required clauses, legal risk identification, compliant wording | Reduce legal risk and improve review efficiency | ⭐⭐⭐⭐⭐ |
| **Financial document validation** | Invoice authenticity, amount calculations, policy compliance | Reduce financial errors and accelerate reimbursement | ⭐⭐⭐⭐ |
| **Tender and official document review** | Formatting standards, required content, section completeness | Improve tender success rates and ensure document quality | ⭐⭐⭐ |

These complex workflows are possible because **LLM-based agents have autonomous decision-making and tool-calling capabilities**:

1. **Autonomous reasoning:** Understand document semantics and logical relationships between clauses, rather than merely executing predefined rules.
2. **Tool orchestration:** Call external tools, such as calculators, database queries, and APIs, to support decisions.
3. **Knowledge retrieval:** Retrieve relevant regulations and cases from knowledge bases and provide evidence-based review opinions.
4. **Chain-of-thought reasoning:** Complete complex review tasks step by step, following a logical process similar to a human expert.

![Original source illustration 24.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202511281052021.png)

> Paper: https://arxiv.org/pdf/2501.09136

For contracts, invoices/receipts, and lengthy official documents, “LLM + tool calling + external knowledge retrieval + planning/reflection (agentic mode)” connects extraction, verification, and evidence-based judgement into multistep workflows for automated or semi-automated compliance review. The CUAD annotated dataset supports the feasibility of clause-level legal contract review. Multimodal document AI, such as LayoutLMv3 / LayoutLLM, improves structuring and question answering for invoices, forms, and PDFs. Agentic RAG / RA-LLM incorporates retrieval, tool use, and multistep reasoning into controllable workflows.

The document review implementation shown above can be divided further into three core technical modules:

![Original source illustration 27.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202511181424904.png)

A more detailed breakdown is shown below:



![Original source illustration 29.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202511181443709.png)

The components are:

- **Parsing and structuring:** Mainstream Document AI extracts OCR, layout, key–value pairs, and tables into a unified JSON representation, with **confidence scores and coordinates** to support downstream rules and traceability to evidence.
- **Rules and knowledge:** Enterprise review requires a **configurable rule engine** (versioning and auditing) and **RAG** (searchable, citable regulations and policies), using **hybrid retrieval and reranking** to improve retrieval accuracy and traceability.
- **Agent orchestration:** LangGraph/LangChain and similar frameworks support **planning, tool calls, memory, and long-running workflow orchestration**, with **human-in-the-loop** intervention as a fallback for low-confidence cases.
- **Evaluation and governance:** Production systems require field-level and RAG evaluation, tracing/monitoring, and PII/audit compliance governance to establish continuous improvement.

A relatively complete document review agent therefore requires an understanding not only of agent and RAG fundamentals, but also multimodal LLMs, multi-agent collaboration, prompt engineering, and agent orchestration. Taken together, this is a relatively challenging implementation scenario.

Accurate document parsing is also critical to implementing document review agents. There are two main approaches: `OCR` and `VLM`. The field has evolved from traditional OCR plus rules towards VLM-based methods, each with advantages in different scenarios.



![Original source illustration 33.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171748193.png)

> Technical overview: https://www.firstsource.com/insights/whitepapers/document-processing-with-vlm

This project uses `MinerU`, a typical open-source pipeline-based document parsing solution. It combines four core components through a pipeline for efficient and accurate document parsing. The following figure is from its official paper: https://arxiv.org/pdf/2409.18839v1



![Original source illustration 36.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202503271440433.png)

The main `MinerU` workflow comprises the following stages:

1. **Input:** Accepts `PDF` documents, ranging from simple text to multimodal PDFs containing two-column text, formulas, tables, and figures.
2. **Document preprocessing:** Checks language, page size, scanned status, and encryption status.
3. **Content parsing:**
   - **Layout analysis:** Distinguishes text, tables, and images.
   - **Formula detection and recognition:** Identifies formula types (inline, display, or ignored) and converts them to `LaTeX`.
   - **Table recognition:** Outputs tables in `HTML/LaTeX`.
   - **OCR:** Recognises text in scanned PDFs.
4. **Content post-processing:** Fixes potential parsing issues, such as overlapping text, image, table, and formula blocks, and reorders content to follow natural human reading order.
5. **Format conversion:** Produces `Markdown` or `JSON`.
6. **Output:** A high-quality, well-structured parsed document.

At the time described in the source, `MinerU` had `48.2K` GitHub stars and `4K` forks, with strong community support, active contributors, and ongoing development.



![Original source illustration 39.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202511071014588.png)

`MinerU` provides an online demo for direct testing: https://opendatalab.com/OpenSourceTools/Extractor/PDF/



![Original source illustration 41.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202503271502432.png)

The `MinerU` project was first open-sourced on `5 July 2024`. It primarily integrates the open-source `PDF-Extract-Kit` project for PDF content extraction: https://github.com/opendatalab/PDF-Extract-Kit



![Original source illustration 43.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202503251117693.png)

`PDF-Extract-Kit` focuses on PDF content extraction and integrates multiple state-of-the-art models for high-quality extraction. These include:

### Model types used by PDF-Extract-Kit

| Model type | Model name | GitHub link | Model download | Task description |
|---|---|---|---|---|
| Layout detection | LayoutLMv3 / DocLayout-YOLO | [GitHub](https://github.com/microsoft/unilm/tree/master/layoutlmv3) / [GitHub](https://github.com/opendatalab/DocLayout-YOLO) | [Download](https://huggingface.co/microsoft/layoutlmv3-base-chinese) / [Download](https://huggingface.co/juliozhao/DocLayout-YOLO-DocStructBench/tree/main) | Locate document elements, including images, tables, text, headings, and formulas |
| Formula detection | YOLO | [GitHub](https://github.com/ultralytics/ultralytics) | [Download](https://github.com/ultralytics/assets/releases/download/v8.3.0/yolo11n.pt) | Locate inline and display formulas |
| Formula recognition | UniMERNet | [GitHub](https://github.com/opendatalab/UniMERNet) | [Download](https://huggingface.co/wanderkid/unimernet_base) | Recognise formula images as LaTeX source |
| Table recognition | StructEqTable | [GitHub](https://github.com/Alpha-Innovator/StructEqTable-Deploy?tab=readme-ov-file) | [Download](https://huggingface.co/U4R/StructTable-InternVL2-1B/tree/main) | Recognise table images as LaTeX/HTML/Markdown source |
| OCR | PaddleOCR | [GitHub](https://github.com/PaddlePaddle/PaddleOCR) | [Download](https://paddlepaddle.github.io/PaddleX/latest/module_usage/tutorials/ocr_modules/text_detection.html) | Extract text from images, including localisation and recognition |

`MinerU` supports both Pipeline and VLM modes:



![Original source illustration 47.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202508061340184.png)

`VLM-Transformer` directly uses vision-language models in the `transformers` library to process multimodal image-and-text inputs. Its workflow is shown below.

The `VLM-Sglang` backend uses the high-performance `sglang` inference engine, optimises GPU acceleration and distributed deployment, and supports real-time streaming output. Its workflow is also shown below.

![Original source illustration 48.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202508061356866.png)

![Original source illustration 48.2](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202508061356864.png)

For VLM mode:



![Original source illustration 50.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202511181655278.png)

- **Pipeline mode:**

![Original source illustration 51.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202510211239047.png)

# 2. Local Deployment of the Intelligent Document Review Agent

First, download the complete project source code from Baidu Netdisk:

![Original source illustration 53.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171849271.png)



![Original source illustration 54.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171342119.png)

After downloading, upload the package to the server and extract it:

```bash
unzip ai-document-review.zip
cd ai-document-review
```

The author provides a one-click installation script to deploy frontend and backend dependencies and start services. First:

```bash
chmod +x install.sh start.sh stop.sh
```

![Original source illustration 57.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171724263.png)

Then run the installation script:

```bash
./install.sh
```

![Original source illustration 58.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171724264.png)

After installation, configure environment variables before starting:

1. **DeepSeek API Key:** Visit the [DeepSeek Open Platform](https://platform.deepseek.com/), register an account, and obtain an API key.
2. **MinerU API Key:** Visit the [MinerU website](https://mineru.net/), apply for API access, and create a token.

```bash
vim .env
```

![Original source illustration 59.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171724265.png)

After configuration, run the startup script:

```bash
./start.sh
```

![Original source illustration 60.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171724266.png)

After startup, open **http://localhost:5173** in a browser.

API documentation is available at **http://localhost:8000/docs**.

![Original source illustration 61.1](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171724267.png)

![Original source illustration 61.2](https://muyu20241105.oss-cn-beijing.aliyuncs.com/images/202512171724268.png)

The intelligent document review agent is now deployed locally, and users can upload documents and begin using its review functions.
