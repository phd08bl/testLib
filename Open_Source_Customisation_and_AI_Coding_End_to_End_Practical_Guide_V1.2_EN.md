# Practical Guide to Open-Source Customisation and End-to-End AI-Assisted Development — V1.2

> This guide explains how to efficiently customise branding and extend an open-source project. More importantly, it shows how to use an **end-to-end AI coding workflow** with assistants such as Cursor and Claude Code to evolve the project. By combining clear responsibilities, human–AI collaboration and engineering Skills, you can accelerate the complete lifecycle: requirement alignment, PRD definition, Issue breakdown, test-driven development (TDD), architectural governance and long-term maintenance.
>
> **Audience:** Developers who want to use Cursor, Claude Code or similar AI coding assistants to **rebrand and customise an open-source project** (change its name/logo, use it commercially in a closed-source product) and maintain their own version over time.
>
> **End-to-end walkthrough:** Clone the upstream project → push to a private repository and `custom/main` → introduce engineering Skills (requirements / PRD / Issues / TDD / PRs) → continuously merge upstream updates.

---

## 1. Prerequisites

| Requirement | Mandatory? | Description |
| --- | --- | --- |
| An AI coding assistant | ✅ Yes | Cursor, Claude Code, Codex, etc. |
| GitHub account | ✅ Yes | Host code, track Issues and use Pull Requests |
| GitHub CLI (`gh`) | ✅ Yes | Create PRs and link Issues using the GitHub API from a terminal or agent |
| Git | ✅ Yes | Local version control |
| Engineering Skills | ✅ Yes | The engineering Skill collection |

### 1.1 Register with GitHub and set up SSH

1. Go to [https://github.com](https://github.com) and create an account.
2. Navigate to **Settings → SSH and GPG keys**.
3. If you do not already have an SSH key, run:

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

Copy the public key.

**macOS:**

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

**Linux** (requires `xclip`):

```bash
xclip -sel clip < ~/.ssh/id_ed25519.pub
```

**Windows Git Bash:**

```bash
cat ~/.ssh/id_ed25519.pub | clip
```

Return to GitHub, click **New SSH key**, paste your public key and save it.

Test the connection:

```bash
ssh -T git@github.com
```

On success, you should see a message similar to `Hi your-username!`.

### 1.2 Install Git

#### macOS

```bash
git --version
xcode-select --install
git --version
```

A response such as `git version 2.x.x` indicates success.

#### Windows

1. Visit [https://gitforwindows.org](https://gitforwindows.org) and download Git for Windows.
2. Install it using the default settings.
3. Open Git Bash or Command Prompt and run:

```bash
git --version
```

A response such as `git version 2.x.x.windows.x` indicates success.

#### Linux

**Ubuntu/Debian:**

```bash
sudo apt-get update
sudo apt-get install git
git --version
```

**CentOS/Fedora:**

```bash
sudo yum install git
git --version
```

### 1.3 Install GitHub CLI (`gh`)

#### macOS

```bash
gh --version
# If gh is not installed, install it using:
brew install gh

# Authenticate after installation (SSH is recommended):
gh auth login

# If permissions cause problems, grant your user ownership of the configuration directory:
sudo chown -R "$(whoami):staff" ~/.config/gh

# Check authentication status:
gh auth status
```

#### Windows

1. Visit [https://github.com/cli/cli/releases](https://github.com/cli/cli/releases) and download the Windows installer (`gh_*_windows_amd64.msi`).
2. Run the installer, then open Command Prompt or PowerShell and execute:

```bash
gh --version
```

3. Initialise authentication for your GitHub account (SSH recommended):

```bash
gh auth login
```

4. Check the authentication status:

```bash
gh auth status
```

#### Linux

**Ubuntu/Debian example:**

```bash
# Install the latest gh version:
type -p curl >/dev/null || sudo apt install curl -y
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh -y

# Authenticate after installation (SSH recommended):
gh auth login

# Check authentication status:
gh auth status
```

You are ready when `gh version x.x.x` appears and authentication succeeds.

### 1.4 Confirm that the Skills are ready

Before starting, make sure your AI coding assistant has the engineering Skills used in this guide enabled. If not, deploy the complete Skills package in the appropriate location for your environment (for example, create `.cursor/skills` under your Cursor project root and copy the Skills package there).

| No. | Command | Category | Purpose |
| --- | --- | --- | --- |
| 1 | `/setup-skills` | Engineering | Run once per repository to configure the Issue tracker, triage label vocabulary, domain documentation, Architecture Decision Records (ADRs), UI design governance settings and other initial configuration |
| 2 | `grill-with-docs` | Engineering | Interrogate and clarify the proposed solution while maintaining the domain glossary (`CONTEXT.md`), ADRs and the UI design governance structure |
| 3 | `grill-me` | Productivity | Run an interview-style questioning process without writing repository documentation |
| 4 | `to-prd` | Engineering | Turn aligned requirements into a PRD and publish it as an Issue |
| 5 | `to-issues` | Engineering | Break the PRD into tracer-bullet vertical slices, producing complete functional and UI Issues |
| 6 | `tdd` | Engineering | Test-driven development using the red–green–refactor cycle |
| 7 | `diagnose` | Engineering | Disciplined debugging loop |
| 8 | `triage` | Engineering | Triage and route Issues using an Issue state machine |
| 9 | `improve-codebase-architecture` | Engineering | Identify architectural refactoring opportunities that deepen modules |
| 10 | `zoom-out` | Engineering | Understand unfamiliar code from a higher-level systems perspective |

---

## 2. Hands-on Walkthrough: A Complete End-to-End Cycle

This guide uses the open-source project [QwenPaw](https://qwenpaw.agentscope.io/) as a practical example. It demonstrates how to combine the AI coding workflow with an existing open-source codebase to rebrand and customise a project, launch your own version efficiently and continue evolving it over time.

### 2.1 Project initialisation

#### 2.1.1 Create a new project

```bash
# Create an empty directory:
mkdir my-qwenpaw
cd my-qwenpaw
# Open the directory in Cursor:
cursor .
```

#### 2.1.2 Clone the official repository locally

```bash
# Enter the project root:
cd my-qwenpaw
# Clone the project into the local project root:
git clone https://github.com/agentscope-ai/QwenPaw.git .
```

**Explanation:**

- `git clone` downloads the complete official codebase to your computer.

After cloning, you should see files and directories such as `README.md`, `LICENSE`, `pyproject.toml` and `src` in the project root (depending on the current official repository structure).

**Check your current remotes.** At this point there is usually only one, named `origin`, pointing to the official repository:

```bash
git remote -v
```

For example:

```text
origin  https://github.com/agentscope-ai/QwenPaw.git (fetch)
origin  https://github.com/agentscope-ai/QwenPaw.git (push)
```

Next, change the setup so that **`upstream` = the official repository** and **`origin` = your private repository**.

#### 2.1.3 Rename the existing origin to upstream

```bash
git remote rename origin upstream
git remote -v
```

**Expected result:**

```text
upstream  https://github.com/agentscope-ai/QwenPaw.git (fetch)
upstream  https://github.com/agentscope-ai/QwenPaw.git (push)
```

It is normal not to have an `origin` remote yet.

#### 2.1.4 Create an empty private repository on GitHub

1. Open [https://github.com/new](https://github.com/new) in your browser.
2. Enter the following:
   - **Repository name:** `my-qwenpaw` (or another name of your choice; remember it).
   - **Description:** Optional, for example, “Customised QwenPaw edition”.
   - Select **Private** (the guide requires a private repository for its closed-source commercial customisation example).
   - **Do not** select “Add a README file”.
   - **Do not** select “Add .gitignore”.
   - You need a **completely empty repository**.
3. Click **Create repository**.

GitHub will show the new repository address in one of two formats:

- SSH: `git@github.com:YOUR_USER/my-qwenpaw.git`
- HTTPS: `https://github.com/YOUR_USER/my-qwenpaw.git`

**Copy the SSH address** (recommended if you have already set up SSH).

#### 2.1.5 Add your private repository as origin

Replace the address below with the **address you just copied**:

```bash
# Still working in the local my-qwenpaw project directory:
git remote add origin git@github.com:YOUR_USER/my-qwenpaw.git
git remote -v
```

**Expected result** (order may vary):

```text
origin    git@github.com:YOUR_USER/my-qwenpaw.git (fetch)
origin    git@github.com:YOUR_USER/my-qwenpaw.git (push)
upstream  https://github.com/agentscope-ai/QwenPaw.git (fetch)
upstream  https://github.com/agentscope-ai/QwenPaw.git (push)
```

#### 2.1.6 Create the customisation branch custom/main

**Why create a separate branch?** Official changes can be incorporated from `main`, while your custom changes live on `custom/main`. Keeping this distinction clear makes future merges easier to manage.

```bash
# See your current branch:
git branch

# Create and switch to custom/main:
git checkout -b custom/main
```

**Expected result:** The terminal displays `Switched to a new branch 'custom/main'`, and `git branch` shows `*` next to `custom/main`.

#### 2.1.7 Push to your private repository for the first time

```bash
git push -u origin custom/main
```

**Explanation:**

- `push` uploads your local branch to GitHub.
- `-u` sets the remote tracking branch, allowing you to run `git push` without specifying the remote each time.

**Expected result:**

- No terminal error. The last line should resemble `Branch 'custom/main' set up to track remote branch 'custom/main' from 'origin'.`
- At `https://github.com/YOUR_USER/my-qwenpaw`, the code is visible when you select the `custom/main` branch.

> **If you see a permissions error:** Check SSH setup (Section 1.1), or switch to an HTTPS URL with `git remote set-url origin https://...`.

#### 2.1.8 Create CUSTOM.md (strongly recommended)

Use this file to record **what you have changed**. It will be especially useful when merging official updates later.

Create `CUSTOM.md` at the repository root (the same level as `pyproject.toml`) with this initial content:

```markdown
# Customisations Relative to Upstream

## Branding
- Product name: (to be completed)
- Logo path: (to be completed)

## Files I Have Modified
| File/directory | What changed | Date |
| --- | --- | --- |
| | | |

## Files Intentionally Removed (e.g., for Commercial Use)
| Path | Reason |
| --- | --- |
| | |

## Upstream Merge History
| Date | Upstream version | Conflicts? | Notes |
| --- | --- | --- | --- |
| | | | |
```

Save the file, then run:

```bash
git add CUSTOM.md
git commit -m "docs: add customisation tracking file CUSTOM.md"
git push
```

**Expected result:** `CUSTOM.md` appears on the `custom/main` branch on GitHub.

#### 2.1.9 Initialisation checklist

Run the following in `my-qwenpaw`:

```bash
git status
git branch
git remote -v
```

| Check | Expected result |
| --- | --- |
| `git status` | `nothing to commit, working tree clean` (or only uncommitted files you recognise) |
| `git branch` | Current branch is `* custom/main` |
| `git remote -v` | Both `origin` (your repository) and `upstream` (official repository) are present |
| GitHub | Private repository `my-qwenpaw` contains code on the `custom/main` branch |

**Initialisation is now complete.** Subsequent development will be based on `custom/main`.

### 2.2 Custom development using the engineering workflow

#### 2.2.1 Initial project configuration — `/setup-skills`

Next, configure the project. The Skill will ask about the Issue tracker, triage labels and domain-documentation layout. For a multi-platform UI project, it also asks whether UI design governance should be enabled.

**Natural-language interaction (in Cursor):**

```bash
/setup-skills
```

| Step | Question | Recommended choice for beginners |
| --- | --- | --- |
| A | Where should Issues be tracked? | **GitHub** is recommended for this walkthrough (multi-platform projects have many Issues and lengthy iterations; GitHub tracking and PRs make changes auditable) |
| B | What triage labels should be used? | Accept the defaults on your first run; multi-platform UI projects add the `design-input` category label for UI-specific work |
| C | Where should domain documentation live? | For one project, select **Single-context**: root `CONTEXT.md` plus `docs/adr/`, shared across all three platforms |
| D | Enable UI design governance? | **Enabled** if you are building an admin interface or mini-program; **Disabled** can be used for API-only projects |

The Skill will generate a structure resembling:

```text
your-project/
├── AGENTS.md or CLAUDE.md     ← Adds agent Skill configuration; use AGENTS.md in Cursor
└── docs/agents/
    ├── issue-tracker.md       ← Issue tracking approach
    ├── triage-labels.md       ← Label vocabulary
    ├── domain.md              ← Domain-documentation layout
    └── design-governance.md   ← Created if UI governance is enabled
```

**Run this only once per repository.** To change settings later, edit `docs/agents/*.md` directly. Finally, push the changes to GitHub. You can use shell commands or natural language; this guide recommends natural-language interaction throughout.

**Natural-language prompt (in Cursor):**

```text
Commit and push the changes.
```

#### 2.2.2 Understand the current code structure — `/zoom-out`

If you are unfamiliar with the dependencies and calling relationships, use `/zoom-out` to produce a system diagram.

**Natural-language prompt (in Cursor):**

```text
/zoom-out

I want a comprehensive understanding of this project's current technical architecture
and the relationships between its modules. Please draw an overall architecture
diagram and show the main module boundaries. Do not provide implementation code.
```

#### 2.2.3 Align requirements before development — `/grill-with-docs`

**Natural-language prompt (in Cursor):**

```text
/grill-with-docs

I want to customise this existing open-source codebase (QwenPaw) into my own
branded product for closed-source commercial use. My brand name is: Yibai.

Version 1 goals:
- Replace the product name, logo, copy and other brand identifiers.
- Remove or trim capabilities that are unsuitable for commercial use, where necessary
  (for example, certain Skills).
- Minimise changes to core logic; prioritise configuration, text and static assets.
- Record all customisations in CUSTOM.md to facilitate future upstream merges.

Interview me step by step until we have clearly defined the branding scope,
customisation boundaries, lists of capabilities to retain/remove, and domain terms.
```

**What to expect:**

1. The agent asks **one question at a time**.
2. It pushes you to replace vague language with precise terms.
3. Once a term is agreed, the agent **immediately creates or updates** `CONTEXT.md` (the first domain-documentation file in a new repository).
4. Decisions that are difficult to reverse are captured as **ADRs**, for example `docs/adr/0001-booking-state-pending-verified-only.md`.
5. **If there is a UI**, after the domain terminology is stable, the agent asks about brand colours, admin-interface versus mini-program UI standards, component libraries, and which customer-facing pages need reference designs. It creates `docs/design/` where appropriate.

**What you should do:**

- Answer each question carefully. If unsure, say “I accept your recommendation.”
- Review `CONTEXT.md` whenever it changes. For a new project, treat it as the foundational reference for domain language.
- **Do not start coding yet.** Without shared terminology, naming and tests may diverge later.

**Once confirmed, say in Cursor:**

```text
Commit and push the changes.
```

#### 2.2.4 Formalise the requirements — `/to-prd`

Once requirements are aligned, **say in Cursor:**

```text
/to-prd

Organise the agreed requirements into a PRD.
```

The agent generates a PRD and publishes it as an Issue on GitHub. Visit the **Issues** page of your repository to check whether the PRD Issue has been created and adjust it if necessary. You can also ask the agent for its status in natural language.

**Natural-language prompt (in Cursor):**

```text
Please verify that the PRD Issue has been created in GitHub Issues, and list
its title and Issue number.
```

#### 2.2.5 Break down tasks — `/to-issues`

When developing a project, it is **strongly recommended to break work into Issues** rather than asking the agent to “build the whole project” in one attempt.

**Natural-language prompt (in Cursor):**

```text
/to-issues

Break the version 1 PRD into vertical slices.
```

In addition to **functional vertical slices**, this example includes a web interface and mini-program, so it also requires **UI Issues**.

**Do not** split the work into “#1 design the entire database schema → #2 implement all APIs → #3 build the admin interface → #4 build the mini-program”. That is horizontal slicing and conflicts with the `/tdd` workflow. Also, **do not** design every page before beginning development.

After breaking down the work, check the number of Issues and their acceptance criteria on the GitHub **Issues** page. Once you confirm the breakdown, the agent will create Issues in dependency order.

**Natural-language prompt (in Cursor):**

```text
The breakdown looks reasonable. Create the Issues.
```

#### 2.2.6 Write code — branches + `/tdd` + PRs

Start with **Issue #2** (Issue #1 is generally the PRD). For **each Issue**, follow the full cycle: **create branch → TDD → push → CI → PR → merge**. Prioritise backend work because both the admin interface and mini-program depend on API behaviour.

**Step 1: Create a branch for Issue #2**

**Natural-language prompt (in Cursor):**

```text
Create a new branch from the latest default mainline, ready to implement Issue #[num].
```

**Step 2: Run `/tdd` in the current or a new conversation**

**Natural-language prompt (in Cursor):**

```text
/tdd

Implement this Issue.
```

**Step 3: Set up CI**

Issue #2 produces test scripts. Add a GitHub Actions workflow **on the same branch** so that checks run automatically in the cloud after pushes.

**Natural-language prompt (in Cursor):**

```text
[One-time setup] Create CI and configure whether it should run on pushes
to any branch and on pull requests.
```

**Step 4: Push and confirm that CI passes**

**Natural-language prompt (in Cursor):**

```text
Commit and push the changes.
```

After pushing, CI runs automatically. Open GitHub → **Actions** and check that the latest **CI** workflow run has passed (✅). If it fails, provide the Actions logs to `/diagnose`. At this point the code has **not yet been merged** into the main branch; you still need to create a PR.

**Natural-language prompt (in Cursor):**

```text
Create a pull request.
```

CI runs automatically after the PR is created. Open GitHub → **Actions** and check that the latest CI run is ✅. If it fails, provide the logs to `/diagnose`. You can also ask the agent to check the CI status.

**Natural-language prompt (in Cursor):**

```text
Please confirm whether CI has passed. If it failed, summarise the reasons
and recommend fixes.
```

Once the PR is ready, merge the changes into `main`.

**Natural-language prompt (in Cursor):**

```text
Merge this PR into main, do not delete the branch, and confirm that the Issue
has been closed.
```

Wait until all PR **Checks** are green before merging into `main`. Repeat for subsequent Issues: new branch → `/tdd` → push → **wait for CI** → PR → merge. This keeps conversations clean and the change history auditable.

#### 2.2.7 Debug issues — `/diagnose`

Problems are common when writing code from scratch.

**Natural-language prompt (in Cursor):**

```text
/diagnose

[Describe your specific problem]
```

The Skill guides you through **reproduce → narrow scope → form hypothesis → observe → verify → fix → add regression tests**. **Do not let the agent guess at fixes immediately.**

#### 2.2.8 Maintain architecture after version 1 — `/improve-codebase-architecture`

Once version 1 is complete, or every three to four days, run this Skill to maintain the codebase:

```text
/improve-codebase-architecture

Review the architecture for opportunities to deepen modules and narrow interfaces.
```

You can do this **from day one of a new project**, without waiting for the codebase to become a “big ball of mud”. **Invest in design from the first version**, rather than accumulating features haphazardly and paying off technical debt later.

---

## 3. When Upstream Releases an Update: How to Merge It into Your Repository

Custom development does not end after cloning. The official project will fix bugs, release security patches and add features. Meanwhile, you continue modifying branding and functionality on `custom/main` in your private repository. As both codebases evolve, you must **regularly merge upstream changes into your customisation branch**. Otherwise, divergence grows and conflicts become harder to resolve.

This section explains how to safely bring new releases or commits from the official repository into your existing `custom/main` branch.

### 3.1 Understand the three paths (mental model)

| Name | Points to | Who changes it? | Where do you develop? |
| --- | --- | --- | --- |
| `upstream` | Official repository (e.g., QwenPaw) | Upstream maintainers | Fetch/read only; do not push business customisations here |
| `origin` | Your private repository | You / your team | Destination of `git push` |
| `custom/main` | Your customised mainline | You | **Where daily development and upstream merges converge** |

In essence, merging works like this:

```text
New commits on official main (or a release tag)
         ↓  git fetch + git merge (or PR)
Your custom/main (preserves customisations and incorporates official changes)
         ↓  git push
Your origin (private repository brought up to date)
```

> **Do not** change the `upstream` remote URL during a merge, or force a merge with a dirty working tree. Ensure the local tree is clean and you are on the correct branch first.

### 3.2 Pre-merge checklist

Run the following at the project root:

```bash
git status
git branch
git remote -v
```

| Check | Expected result |
| --- | --- |
| Working tree | `nothing to commit, working tree clean` (commit or stash uncommitted changes first) |
| Current branch | `* custom/main` (or your agreed customisation mainline) |
| Remotes | Both `origin` (yours) and `upstream` (official) |
| Customisation records | `CUSTOM.md` exists at the root and its “Files I Have Modified” section is reasonably up to date |

**Natural-language prompt (in Cursor):**

```text
Run a pre-merge check: confirm that I am on custom/main, the working tree is
clean, both origin and upstream remotes exist, and summarise the "Files I
Have Modified" list in CUSTOM.md.
```

### 3.3 Fetch upstream and inspect what changed

```bash
# 1. Fetch the latest official refs without changing local files:
git fetch upstream

# 2. List commits that exist upstream but not on your current branch
# (the official mainline is usually named main):
git log --oneline HEAD..upstream/main

# 3. Preview which files are affected:
git diff --stat HEAD...upstream/main
```

If the official project publishes release tags, list them and compare against a particular version:

```bash
git fetch upstream --tags
git tag -l --sort=-v:refname | head
# Example: inspect commits in a specific release tag relative to your branch:
git log --oneline HEAD..v1.2.0
```

**How to interpret the results:**

- If `git log` is empty, your branch already includes these official commits: **no merge is required this time**.
- If there are new commits and `git diff --stat` includes files listed as modified in `CUSTOM.md`, these are **high-risk conflict areas**. Pay particular attention to them while merging.

**Natural-language prompt (in Cursor):**

```text
First switch to custom/main and fetch upstream. Compare custom/main with
upstream/main: summarise new commits, show statistics for changed files,
and identify paths overlapping with "Files I Have Modified" in CUSTOM.md.
```

### 3.4 Recommended workflow: merge upstream on a dedicated sync branch

Avoid experimenting directly on `custom/main`. A safer approach resembles everyday Issue development: **create sync branch → merge upstream → resolve conflicts → test → open PR → merge back into `custom/main`**.

#### 3.4.1 Create a sync branch from the latest customisation mainline

```bash
git checkout custom/main
git pull origin custom/main
git checkout -b sync/upstream-YYYYMMDD
```

Replace `YYYYMMDD` with today's date, or use an official version number, such as `sync/upstream-v1.2.0`.

#### 3.4.2 Merge the official mainline (or a specific tag)

```bash
# Default walkthrough: merge the official main branch:
git merge upstream/main
```

To synchronise with a particular release tag instead:

```bash
git merge v1.2.0
```

**Natural-language prompt (in Cursor):**

```text
Create a new branch sync/upstream-YYYYMMDD from the latest custom/main,
then merge upstream/main into it.
If conflicts arise, stop and list the conflicting files and reasons.
Do not discard our branding customisations or CUSTOM.md records without approval.
```

#### 3.4.3 Resolve merge conflicts

A conflict occurs when both sides have changed the same file. Follow these principles:

1. **Stop and inspect** the conflict list, comparing it with `CUSTOM.md`.
2. For **branding, copy, logos and intentionally removed commercial features**, prioritise preserving your customisations, then manually incorporate necessary upstream logic.
3. For **upstream bug fixes, security patches and unrelated core logic**, prioritise incorporating upstream changes and reapplying your customisations.
4. **Do not** resolve all conflicts by blindly selecting one side. After the merge, the application should still work and your branding should remain intact.

List conflicting files:

```bash
git status
# Or:
git diff --name-only --diff-filter=U
```

After resolving each file:

```bash
git add <resolved-file>
# After resolving everything:
git commit   # Follow Git's prompts if a merge message has already been generated.
```

**Natural-language prompt (in Cursor):**

```text
/diagnose

Conflicts occurred while merging upstream/main. Use CUSTOM.md to distinguish
"customisations that must be preserved" from "official fixes that should
be incorporated". Propose a file-by-file resolution strategy and explain
how to validate the results. Do not silently discard customisations.
```

If conflicts are extensive and cannot be understood immediately, first record the conflicting files in an Issue and resolve them one by one. **Do not force a push while conflicts are only partially resolved and call the merge complete.**

### 3.5 Validate the result after merging

Completing a commit is not sufficient. Check the following for your project (using a QwenPaw-like application as an example):

1. **Installation and startup work:** Start the service according to the official README or your project's documentation.
2. **Branding is preserved:** Product name, logo and key text have not reverted to official defaults.
3. **Custom functionality remains:** Spot-check important changes recorded in `CUSTOM.md`.
4. **Tests and CI:** Run tests locally; if CI is configured, push and wait for GitHub Actions to pass.
5. **Update the history:** Add an entry to the “Upstream Merge History” section of `CUSTOM.md`.

Example addition to `CUSTOM.md`:

```markdown
## Upstream Merge History
| Date | Upstream version | Conflicts? | Notes |
| --- | --- | --- | --- |
| 2026-07-25 | upstream/main@abc1234 | Yes: README brand-name conflict | Preserved our branding and incorporated upstream dependency upgrades |
```

```bash
git add CUSTOM.md
git commit -m "docs: record upstream merge (YYYYMMDD)"
```

### 3.6 Merge back into the custom mainline and push to your private repository

After validating the sync branch, use a PR (recommended) or a direct/fast-forward merge.

**Option A: Pull Request (recommended for reviewability and CI checks)**

**Natural-language prompt (in Cursor):**

```text
Commit and push the current sync branch, then create a PR targeting custom/main.
In the PR description, clearly document the upstream change range, files with
conflicts and the resolution decisions, and local/CI validation results.
```

Once CI is green and a human has confirmed the branding and critical paths:

```text
Merge this PR into custom/main. Do not delete the branch (or follow the
team's normal branch deletion practice), and confirm no conflicts remain.
```

**Option B: Merge locally (for personal repositories and small changes)**

```bash
git checkout custom/main
git merge sync/upstream-YYYYMMDD
git push origin custom/main
```

### 3.7 Recommended cadence and pitfalls

| Recommendation | Explanation |
| --- | --- |
| Merge regularly | If upstream is active, merge weekly or with each release. The longer you wait, the more difficult conflicts can become |
| Merge in small batches | Synchronise one upstream range (a set of commits or a tag) at a time instead of accumulating six months of changes |
| Record changes before merging | The more complete `CUSTOM.md` is, the easier conflict decisions become |
| Keep upstream sync separate from feature work | Finish or put aside in-progress Issue branches; avoid mixing incomplete feature work with a large upstream merge |

**Things to avoid:**

- Changing the version number without fetching upstream, then assuming the project is in sync.
- Using `git checkout --theirs` or `--ours` to overwrite entire conflicting files without reviewing their contents.
- Failing to start the application, check branding or update `CUSTOM.md` after merging.
- Pushing private-repository-only commits to `upstream` (you typically do not have permission and should not do so).

### 3.8 One-page command cheat sheet

```bash
# Pre-merge check:
git status && git branch && git remote -v

# Fetch and preview upstream:
git fetch upstream
git log --oneline HEAD..upstream/main
git diff --stat HEAD...upstream/main

# Merge on a sync branch:
git checkout custom/main && git pull origin custom/main
git checkout -b sync/upstream-YYYYMMDD
git merge upstream/main
# ...resolve conflicts, test, update CUSTOM.md...

# Push and merge back into custom/main via PR (or merge locally):
git push -u origin HEAD
```

**At this point:** The new upstream version has been incorporated into `custom/main`, your customisations are preserved, and your private repository is aligned with upstream again. Continue custom development using the Section 2 workflow: Issue → `/tdd` → PR.
