# MRO FDE — Stage 3 Discovery & Operating Guide

**Version:** 1.2 — 24 October 2026  
**Status:** Proposed MRO operating standard, for piloting and refinement  
**Primary users:** MRO FDE / AI Tech & Tooling engineers and Process Owners  
**Also relevant to:** Operational validators, Methodology Owners, team leads and specialist SMEs  
**Applies to:** Model documentation review; front-office model code assessment; independent quantitative testing; benchmarking / alternative-model development; validation report drafting; validation report review; and comparable MRO work.

> **Stage 3 objective:** Translate an SLT-prioritised business process into an evidence-backed understanding of actual work, validated problems, measurable desired outcomes and actionable improvement opportunities. **Discover the work before designing the solution.**

**Quick-use rule:** FDE works through **four practical steps**, records results in **one six-section Discovery Canvas**, applies **six Gate 3 criteria**, and prepares the appropriate downstream output: **opportunity-specific Stage 4 Brief(s)** and a **one-page SLT Discovery Update**. Detailed question banks and methods are reference material, **not extra mandatory forms**.

---

# Part A — Practical operating guide (use in every engagement)

## A1. What Stage 3 is / is not

| Stage 3 does | Stage 3 does not |
|---|---|
| Understand process, analytical work, key decisions, controls and genuine completion | Assume all MRO work is linear or reducible to a simple workflow diagram |
| Examine a **representative work item** and relevant exceptions | Require a full process audit or a large data collection for every candidate |
| Distinguish validated business problems, symptoms, root-cause hypotheses and solution hypotheses | Treat “build an AI agent” as a validated business requirement |
| Understand existing scripts, tools, PoCs, methodology, data and dependencies | Select the final platform, agent architecture or engineering components |
| Define meaningful business outcomes, baseline **or owned measurement plan**, and quality/risk guardrails | Assert that future benefits have already been delivered or invent percentage improvement targets |
| Identify opportunity-level scope, ownership and next actions | Unilaterally reprioritise the SLT portfolio, authorise a production system or change validation methodology |

**Working principle:** Investigate at the level that affects a business improvement decision. A routine process may need a task list; a technical validation activity may need an experiment or decision/evidence lifecycle. Use diagrams only when they clarify something consequential.

### Inputs

- Stage 1 Candidate Brief and Stage 2 leadership priority / discovery boundary.
- Identified Process Owner or accountable business sponsor; representative users and relevant Methodology Owner as needed.
- Existing process documents, method standards, example work items, scripts/tools, PoCs and performance data **where already available**.

### Roles and decision rights

| Participant | Stage 3 contribution / accountability |
|---|---|
| **FDE Lead** | Facilitates discovery, assesses technical feasibility signals, captures evidence and opportunities, prepares Gate recommendation, Stage 4 Briefs and SLT update. |
| **Process Owner** | Confirms how the process works and the intended business outcome; validates findings, scope and proposed success measures. |
| **Methodology Owner (where relevant)** | Clarifies professional standards, model-validation judgement, independence, controls and ownership of methodology changes. |
| **Actual validators / end users** | Demonstrate real tasks, code/experiment/review decisions, exceptions, workarounds and evidence. |
| **Handoff / team owners** | Validate interfaces, queues, dependencies and escalation responsibilities. |
| **Tech / Data / Platform / Security SMEs (only as needed)** | Identify material access, control, environment and service constraints; do not substitute for later formal approvals. |
| **SLT / delegated Stage 2 authority** | Owns prioritisation and material priority/scope changes; receives progress and decisions requiring sponsorship. No routine sign-off of every Card. |

## A2. Four working steps (mapped to the original seven activities)

| Working step | Existing stage activities | What FDE does | Exit evidence |
|---|---|---|---|
| **1. Frame the process** | 3.1 | Confirm Stage 2 intent, business process/task, boundary, genuine completion, Process Owner, users and relevant methodology authority. | Canvas §1 populated; engagement/evidence plan. |
| **2. Understand actual work** | 3.2–3.4 | Walk through a real item; map significant steps or iterations, decisions, controls and evidence; distinguish problems from symptoms; obtain baseline or measurement approach. | Canvas §§2–4 with representative evidence and meaningful problem statements. |
| **3. Identify valuable improvements** | 3.5–3.6 | Review available information, constraints, existing initiatives, user/adoption needs; define opportunities and measures **without selecting a solution**. Compare cross-team variants only where evidenced. | Canvas §§5–6; compact Opportunity Register. |
| **4. Validate and route** | 3.7 | Playback findings; Process Owner confirms/corrects; check six Gate Criteria, log uncertainty and recommend next action for each opportunity. | Gate record; Stage 4 Brief(s) and SLT Update as appropriate. |

The **seven activities** are retained as the reference methodology. They are **not seven separate meetings or approvals**.

## A3. Engagement pattern and suggested agendas

**Preparation (FDE, before the call)**

1. Read Candidate Brief / SLT decision; state what is prioritised and what has *not* been decided.
2. Check existing MRO methodology, tools, scripts, process maps, completed PoCs and related initiatives; reuse available findings.
3. Select a meaningful process variant and identify Process Owner and one operational user (include Methodology Owner only if needed).
4. Ask for **one representative work item**—a case, code assessment, test, experiment or report section—and an exception/rework example if useful. Do not request unapproved copies of sensitive records.
5. Pre-populate the Discovery Canvas with known facts and mark all assumptions explicitly.

**Call 1 — Process Owner / user discovery (suggested 45–60 minutes)**

| Minutes | Agenda | Questions to ask | Capture |
|---:|---|---|---|
| 0–10 | Purpose and process boundary | What business outcome does the process serve? When does the work begin and genuinely finish? Who owns it? | Canvas §1 |
| 10–30 | Real work-item walkthrough | Show us a recent example. What inputs, actions, analytical decisions, systems and controls were involved? What was the output? | Canvas §2 |
| 30–45 | Problems, evidence, value | Which steps required extra effort, waiting, rework or specialist judgement? What evidence supports that? How would improvement be measured? | Canvas §§3–4 |
| 45–60 | Constraints and next actions | Existing tools? Important data, method or approval constraints? Desired outcome? What else must be verified? | Canvas §§5–6 and action list |

**After Call 1 (FDE synthesis)**

- Draft a concise process/task view; distinguish *verified evidence*, *SME claim*, *hypothesis* and *unknown*.
- Select **up to three main issues** for the initial discussion, without forcing a numeric cap on material risks.
- Write a problem statement and at least one measurement row for each material opportunity.
- Identify existing solutions, quick non-AI changes and key feasibility questions; avoid technical commitment.
- Send a short factual readback for Process Owner correction.

**Targeted SME follow-up — conditional (often 30–60 minutes).** Use only to resolve real questions: code access, test reproducibility, methodology, approval rights, data sources, baseline sampling, cross-team handoffs or important exceptions. Analytical work may require viewing an approved notebook, test results, code-review log or benchmark study rather than a meeting about a flowchart.

**Playback and Gate (suggested 30 minutes, or asynchronous for a straightforward case).** Confirm the current-state description, evidence-backed problems, measurements or collection plans, controls and ownership. Review opportunity dispositions and agree any conditions for Stage 4 or further discovery. Record disagreements, not manufactured consensus.

**Proportionate path:** A single call + readback can be sufficient for a clear, low-complexity task. A novel, high-consequence or cross-team activity can justify additional focused discovery. Do not mandate three meetings for every initiative.

## A4. One Discovery Canvas — six sections

Complete this as **one working record**. The former six Cards remain identifiers for structuring data and potential automation; they are **not six additional reports**. Aim for **around two pages for a straightforward case**, with links to optional supporting analysis.

### §1 — Process & ownership (C3-01)

- **Parent Stage 2 priority / FDE ID:** [ ]
- **Team / process variant / Discovery Wave:** [ ]
- **Process purpose and intended output:** [ ]
- **Start / genuine completion / out of scope:** [ ]
- **Process Owner / FDE Lead / key users:** [ ]
- **Methodology, control or handoff owner (if material):** [ ]

### §2 — Actual work, decisions & controls (C3-02)

- **Representative item / approved evidence reference:** [ ]
- **Key work stages / iterations and handoffs:** [ ]
- **Important inputs and final outputs:** [ ]
- **Analytical judgement / methodology / independence requirements:** [ ]
- **Systems, scripts, tools and environments used:** [ ]
- **Exceptions, rework, failure paths, escalation and authorisation boundaries:** [ ]

Use **one short table** where needed:

| Task or decision | Input → output | Actor / tool | Judgement / required control | Friction / evidence |
|---|---|---|---|---|
| [ ] | [ ] | [ ] | [ ] | [Reference] |

For iterative research/testing, show **hypothesis → preparation → execution → interpretation → revision → decision**, including possible loops, rather than forcing an artificial linear business process.

### §3 — Problems & evidence (C3-03)

Record the top issues using this minimal structure. A solution request is not evidence of a problem.

| ID / process step | Observed problem and affected user | Evidence / confidence | Impact | Likely cause / uncertainty |
|---|---|---|---|---|
| PP-01 / [ ] | [ ] | [EV-ID, verified/claimed/unknown] | [ ] | [ ] |

**Problem discipline:** `Business problem ≠ observed symptom ≠ root-cause hypothesis ≠ proposed solution.` Identify the desired improvement separately. Keep significant professional judgement and controls visible.

### §4 — Desired outcomes & measures (C3-03 / C3-06)

For each **material opportunity**, record **one primary improvement measure** and **one or two quality/risk guardrails** as a default; add more only when necessary.

| Outcome | Metric + unit | Baseline + source/status | Proposed target or direction | Quality/risk guardrail | Owner / measurement plan |
|---|---|---|---|---|---|
| [ ] | [ ] | [measured / estimate / unavailable] | [agreed / proposed / TBD] | [ ] | [who / how / when] |

**Baseline** = current measured/estimated state; **Target** = desired change, not necessarily agreed; **Acceptance criteria** = conditions on a particular future solution, refined in Stage 4. If baseline is unavailable, specify the metric, evidence source, collection approach, owner, timing and the downstream decision that requires it. **Never invent values.** Distinguish elapsed cycle time, active work time and waiting time.

For MRO, metrics often concern **efficiency, quality, control/risk assurance, reproducibility and capacity**, not direct revenue. Higher throughput alone is not proof of better independent validation.

### §5 — Dependencies & existing capabilities (C3-04 / C3-05)

- **Authoritative evidence/data and owner; quality, access and sensitivity:** [ ]
- **Critical methodologies, validation independence, controls and approvals:** [ ]
- **Existing scripts, templates, Python libraries, Copilot tools, validation platform or PoCs:** [ ]
- **Main technical / organisational / adoption unknowns:** [ ]
- **Business process commonality across teams:** Local / Potentially Common / Clearly Common / Unknown **with reason**. Do not assume a shared solution.

Record high-consequence **side effects** when material: read-only advice, draft/recommendation, communication to a model owner, changes to official records, risk decisions or approvals. Detailed safeguards are designed later.

### §6 — Opportunities & next actions (C3-04 / C3-06)

Use a **short Opportunity Register**, not additional full cards:

| ID | Opportunity / problem ID | Desired outcome and indicative value | Key constraints / existing work | Next action / owner | Reuse / routing |
|---|---|---|---|---|---|
| OPP-01 | [ ] | [High/Medium/Low + why] | [ ] | [ ] | [local/common/unknown; parent/child/TBD] |

If an improvement is simply better submission guidance, methodology clarification or an existing tool configuration, route it to the relevant owner instead of automatically creating a software/AI build.

**Minimal traceability:** `Representative evidence → problem → opportunity → business outcome/measure → next decision.` Evidence can be stored as **references** to approved locations, not duplicated in the Canvas.

## A5. Six Gate 3 criteria — decision, not bureaucracy

Tick only when supported, or document a defensible exception/condition:

- [ ] **Process:** Boundaries, significant tasks/decisions, ownership and controls are understood at the level relevant to the opportunity.
- [ ] **Evidence:** Material business problems are supported by evidence or explicitly marked as unverified with owned follow-up.
- [ ] **Value:** A credible desired business outcome and indicative impact are stated.
- [ ] **Measurement:** Success metric(s) and an evidenced baseline **or actionable measurement plan**, with guardrails, exist for Stage 4 candidates.
- [ ] **Constraints:** Material methodology, independence, data/access, existing-solution and operational dependencies are identified.
- [ ] **Action:** Process Owner has reviewed findings, and each material opportunity has a disposition, action owner and any conditions.

**G3 decision at Discovery Wave level:** `Ready for opportunity routing` / `Ready with explicit conditions` / `Targeted discovery required` / `Revise` / `Stop or escalate`.

**Each opportunity receives TWO independent decisions:**

| Dimension | Available values |
|---|---|
| **Progression** | Stage 4 / More discovery / Use or merge existing initiative / Defer / Stop |
| **Case routing** | Stay in Parent FDE Case / Recommend Child Case / TBD |

FDE recommends progression; the Process Owner validates business findings. Follow established delegation for Gate sign-off. **SLT or delegated Stage 2 authority retains control of material reprioritisation, expanded waves and resource decisions.** A ticked checklist does not approve production deployment or methodological change.

**Decision record (minimum):** parent/wave, owner confirmation and date, G3 disposition, key evidence/unknowns, each opportunity progression and case routing, metric/measurement conditions, next owner and SLT decision required (if any).

## A6. Two downstream outputs, produced from the same Canvas

### Output 1 — Stage 4 Opportunity Brief (one to two pages **per progressing opportunity**)

Stage 4 should not have to re-interview the Process Owner to discover the basic problem.

| Field | Stage 3 handover requirement |
|---|---|
| Opportunity ID and accountable Process Owner | [ ] |
| **Validated problem and evidence** | What happens, whom it affects, evidence links and confidence |
| **Actual work / key decisions** | Relevant task/experiment/review stages; input, output, human judgement and controls |
| **Business outcome and scope** | Minimum valuable business outcome, initial users, exclusions and boundaries |
| **Measure and guardrails** | Primary KPI, baseline/status or measurement plan, target direction, quality/risk constraints |
| **Known constraints** | Methodology/independence, data access, security, environment, operational responsibilities |
| **Existing assets and options to assess** | Scripts, PoCs, process changes or potential solution families **as hypotheses only** |
| **Open design questions** | Feasibility assumptions, specialist input, evaluation design and unresolved dependencies |
| **Decision and conditions** | G3 progression decision, Stage 4 actions, owners and required evidence milestones |

**Stage 4 decides** whether the right route is process/methodology change, a user prompt, Copilot/low-code, deterministic software, analytics, RAG, agentic automation or a specialised validation tool, including reuse and architecture. Stage 3 must not pre-select it.

### Output 2 — SLT Stage 3 Discovery Update (one page **per parent priority**)

**Purpose:** Enable the monthly MRO steering discussion without exposing SLT to technical task tables or unverified benefit claims.

| Heading | Maximum content |
|---|---|
| **Priority / scope / status** | Parent priority; which teams/variants reviewed; `Not started / In Discovery / Findings validated / Stage 4 candidates ready` |
| **What we found** | Up to three most important **evidence-supported** problems and differences across teams |
| **Business value and measures** | Indicative impact, candidate primary measures, baseline confidence and guardrails; distinguish measured from estimated |
| **Opportunities and route** | Up to three key opportunities; proposed Stage 4 / existing-solution / further discovery dispositions |
| **Dependencies / decisions** | Material blockers, cross-team owner questions, next wave or resource decisions **only if SLT action is required** |
| **Next milestone and owner** | Concrete near-term action, accountable owner, target milestone (if known) |

**SLT narrative:** `We reviewed [scope]; evidence indicates [problem and impact]; we recommend [opportunity/route] because [value/constraints]; the next step is [action]; SLT input is [none / specific decision].`

Do not create a technical deck for each Discovery Wave; aggregate waves under the shared leadership priority. An unverified benefit remains a **hypothesis**, not a delivered KPI.

## A7. Scaling across teams: Parent Cases, variants and reuse

- **Parent FDE Initiative:** the Stage 2 prioritised outcome (e.g., improve model documentation review).
- **Discovery Wave:** a specific team, workflow or material process variant; sequence by leadership direction, value and availability.
- **Child Case:** recommended **only** where opportunity outcome, ownership, risk, scope or delivery decisions differ materially; a naming difference is not enough.
- **Reuse class:** `Local`, `Potentially Common`, `Clearly Common` or `Unknown` applies to the **business requirement/process**. Technology/component reuse is assessed in Stage 4.
- An adequately evidenced first-team opportunity can progress to Stage 4 **without completing all MRO Discovery Waves**. FDE may recommend further waves; leadership controls material changes to priority.

---

# Part B — Reference methods (consult only when needed)

## B1. Ten essential questions for FDE interviews

1. What business outcome does this work support, and who owns it?
2. What starts this work, and what counts as genuinely finished or accepted?
3. Can we follow **one real work item** from inputs through expert decisions to evidence/output?
4. Where does time go: active work, waiting, analysis iteration, rework or approvals?
5. What judgement is based on methodology, documented rules or specialist experience?
6. What are the material errors, exceptions, failure consequences and human control boundaries?
7. What is the main business problem, **what evidence demonstrates it**, and what is only a hypothesis?
8. How often or how materially does it occur, and what current measure or sampling plan is available?
9. What existing tools, scripts, processes or experiments already help—and what data/access constraints matter?
10. What improvement would be valuable, how would we recognise success, and what must **not deteriorate**?

**Evidence probes:** “Show an example”, “Who decided?”, “What standard was used?”, “What happened when it failed?”, “Is that a measured figure or an estimate?”, “How would you falsify the root-cause hypothesis?”, “Could we improve this without AI?”

## B2. Process representation — select the lightest useful method

| Method | Use when |
|---|---|
| **Task list / simple flowchart (default)** | Fairly predictable work; clarify steps, input/output, bottleneck. |
| **Swimlane / BPMN** | Multiple teams, handoffs, queue time, approvals or control ownership materially affect the problem. |
| **State-transition diagram** | An object moves through submitted, queried, revised, reviewed and accepted states; transition conditions matter. |
| **Experiment/decision lifecycle** | Quantitative testing, code analysis, benchmarking or alternative models require iteration, hypotheses, reproducible evidence and professional challenge. |

Do **not** require BPMN or a state machine for each case. Preserve branching and iteration where it is inherent to the validation method; do not label all iterations as avoidable rework.

## B3. Deeper task, problem and KPI templates — use for consequential or ambiguous cases

**Detailed task decomposition (C3-04):**

| ID | Input | Judgement / rule | Action | Output | Side effect / official-state consequence | Owner | Control | Evidence |
|---|---|---|---|---|---|---|---|---|
| T-01 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

Decompose only to the **smallest business-meaningful task**, not every mouse click or line of code.

**Verifiable problem statement (C3-03):**

> In [team / process], [affected users] experience [observed current problem] when [circumstance], evidenced by [approved case/source], causing [effort, quality, risk or delay impact]. The likely cause is [verified/assumed mechanism]. The desired improvement is [business outcome] subject to [methodology, independence and control constraints]. [Any proposed technology] is a separate solution hypothesis.

**Extended measurement row (only when necessary):** Metric ID; definition/unit/denominator; linked problem/opportunity; current value/status; evidence/sample period/confidence; intended target/direction; baseline collection owner/method/milestone if missing; quality/risk guardrail; Process Owner; later-stage evaluation condition. Do not confuse cycle time, active effort and waiting time.

**Evidence quality:** Link approved evidence as `EV-ID | source and access location | date | supports which claim/task | owner | verified / asserted / unresolved`. Maintain unresolved decisions as `Assumption/Dependency | impact | verification action | owner | due or stage condition`. Do not copy confidential model source, test data, candidate CVs or restricted files into unapproved repositories or AI prompts.

## B4. Six MRO workflow lenses (the common Canvas still applies)

| Process type | Representative work item | Specialist discovery focus | Example primary measure | Necessary guardrail / quality condition |
|---|---|---|---|---|
| **Model documentation review** | A model submission and completed review/query cycle | Completeness vs adequacy; standards and evidence gaps; changing documents; requests for clarification | Reviewer active time or avoidable rework per review | Material gap detection and validator judgement retained |
| **Front-office model code assessment** | Approved source-code module/commit plus design specification and past review findings | Implemented logic vs intended model design; code execution access; review methods and discrepancies; secure handling | Time to defensible assessment of a defined component | Detection of material implementation issues and reviewer independence |
| **Independent quantitative testing** | A completed test: data, script, environment, results and interpretation | Test selection, independent implementation, reproducibility, diagnostics, environment, model-owner challenge | Preparation effort for comparable tests | Correctness, test coverage relevance and reproducibility |
| **Benchmarking / alternative model** | One benchmark/challenger study with hypothesis, calibration, iterations and comparison | Why benchmark selected; assumptions; experiment cycles; data; defensibility of comparison | Time to documented, defensible comparison | Scientific validity, methodological challenge and traceability |
| **Validation report generation** | Report section traced back to test outputs, findings and citations | Evidence aggregation; interpretation vs paraphrasing; approval workflow; report templates | Drafting effort per comparable report section | Evidence fidelity, completeness and human authorship/approval |
| **Validation report review** | A report with reviewer comments, revisions, resolution and approvals | Methodology compliance, consistency, findings, citations, material issues and sign-off | Review effort or number of unnecessary correction cycles | Material issue detection, review independence and approval trail |

Candidate KPIs above are **options to validate**, not universal metrics or established performance levels. Particularly for quantitative/research work, speed must not displace defensibility or independent challenge.

## B5. Cross-team comparison, existing capabilities and scope decisions

When multiple teams share a leadership priority, compare **business outcomes, actual inputs, judgement criteria, required outputs, controls, exceptions, measures and users**. If differences are material, a separate opportunity/Child Case may be justified. If requirements overlap, Stage 4 explores shared components; do not prescribe a single agent on Stage 3 evidence alone.

Log known existing capability as `Name / Owner / relevant task / maturity (in use, PoC, idea) / actual gaps / reusable evidence`. An existing solution can be the recommended answer; discovery should not create redundant engineering work.

**Opportunity routing:** `Proceed Stage 4`, `Targeted discovery`, `Merge/use existing`, `Defer`, `Stop`. Independently specify `Parent / Recommend Child / TBD`. If a business-process or methodology-only change is sufficient, route to the appropriate owner, noting whether it remains in the FDE portfolio.

## B6. Illustrative Model Documentation Review example (hypotheses only)

**Stage 2 priority:** Improve the documentation review process across relevant MRO teams. No solution type selected.

**Possible work lifecycle to verify:** receipt of documentation → determine applicable requirements → find supporting evidence → assess completeness/adequacy → communicate gaps → re-review → determine readiness or residual evidence needs.

**Potential differing variants (do not treat as actual findings):**

- **Trade Surveillance Validation:** material friction might involve missing required design content before testing starts; an opportunity might be earlier completeness/consistency checking.
- **AI Independent Validation:** material friction might involve changing artefacts and risk-based analysis of incomplete evidence; an opportunity might be structured evidence-gap assessment supporting validator judgement.

**Example problem:** “Validators may repeatedly search across documentation versions to locate evidence needed for independent assessment.” Mark as **hypothesis** until demonstrated with approved work items; do not equate it with a request for RAG.

**Example outcome/measure:** Reduce active time locating evidence in comparable reviews; establish baseline from approved samples; preserve material evidence-gap identification and human risk decision. Numeric target remains `TBD` until evidence supports it.

**Example dispositions:** Standardise document submissions (business/methodology route); investigate completeness checks (Stage 4 candidate); examine risk-based gap assessment as a distinct opportunity where methodology and controls warrant it. Do not split into Child Cases automatically.

## B7. Worked engagement examples for other processes (starting questions)

- **Code assessment:** “Show one significant code-to-methodology discrepancy. How was it detected, challenged and recorded? Which repository/access rules apply?”
- **Independent quantitative testing:** “Show one test from rationale to reproducible run and interpretation. What took time: test design, dataset, environment or analysis? Which parts must remain independently verified?”
- **Benchmark/alternative model:** “Show a benchmark choice and a changed hypothesis. What was the decision criterion, what evidence justified iterations and how was the comparison defended?”
- **Report generation:** “Trace one material conclusion from analysis result through citation and drafting to validator approval. Where is manual work duplicative?”
- **Report review:** “Show a materially changed finding or review comment and its resolution. How are policy consistency and reviewer independence demonstrated?”

## B8. Optional quality indicators for improving the FDE operating model

Monitor at programme level **after accumulating usable data**, not as targets that encourage shallow discovery:

1. **Discovery lead time:** start of substantive engagement to validated Gate 3, segmented by complexity.
2. **Stage 4 clarification/rework:** proportion of progressing opportunities returned for insufficient business context/evidence.
3. **Measurement readiness:** share of progressing opportunities with a meaningful KPI and evidenced baseline **or credible owned measurement plan**.

Do not reward the number of diagrams, interviews, Cards or opportunities produced. Stage 8 should assess realised benefits against Stage 3's original business measures where comparable.

---

# Part C — Copy-and-use outputs

## C1. Post-call readback (copy into email or Confluence)

**Process / team / Stage 2 priority:** [ ]  
**Current understanding (2–4 sentences):** [ ]  
**Representative work evidence reviewed:** [Reference; no restricted payloads]  
**Main material problems:** [Problem ID, evidence/confidence, impact]  
**Desired outcome and candidate measure:** [ ]  
**Baseline status / measurement owner:** [ ]  
**Required judgement or quality/risk condition:** [ ]  
**Known existing tool/initiative:** [ ]  
**Open questions / assigned actions:** [ ]  
**Process Owner confirmation requested:** Please correct any inaccurate workflow, methodology, controls or findings.

## C2. Gate 3 record (copy and use)

**Parent / Discovery Wave / team:** [ ]  
**Process Owner confirmation and date:** [ ]  
**FDE Lead assessment:** [ ]  
**Six criteria:** Process [ ]; Evidence [ ]; Value [ ]; Measurement [ ]; Constraints [ ]; Action [ ]  
**Overall Gate:** [Ready / Conditional / Further discovery / Revise / Escalate or stop]  
**Material conditions, evidence/measurement plan and owners:** [ ]

| Opportunity | Progression | Parent/Child routing | KPI / baseline status / guardrail | Rationale / owner / next action |
|---|---|---|---|---|
| OPP-01 | [ ] | [ ] | [ ] | [ ] |

**Any SLT decision required?** [No / precise ask and why]  
**Next Discovery Wave proposed?** [No / scope and leadership decision needed]  
**Recorded by / date:** [ ]

## C3. Stage 4 Opportunity Brief (copy and use)

**Opportunity ID and short title:** [ ]  
**Process Owner / team / priority:** [ ]  
**Validated problem, impact and evidence references:** [ ]  
**Representative task or experiment / required human judgement:** [ ]  
**Minimum valuable business outcome, users and exclusions:** [ ]  
**Primary business KPI and baseline status/collection plan:** [ ]  
**Target direction / quality and risk guardrails:** [ ]  
**Critical methodology, data/access, control and operational constraints:** [ ]  
**Existing relevant tools, PoCs and non-AI alternatives to assess:** [ ]  
**Open Stage 4 feasibility/evaluation/design questions:** [ ]  
**Gate 3 disposition, conditions, next owner:** [ ]

## C4. One-page SLT Discovery Update (copy and use)

**Stage 2 priority:** [ ] | **Reporting date:** [ ] | **FDE Lead:** [ ]  
**Scope and status:** [Teams/variants reviewed; discovery status]  
**Key findings (maximum three, with evidence confidence):** [ ]  
**Value and measurement:** [Expected benefit; primary metric; measured/estimated/planned baseline; critical guardrail]  
**Priority opportunities and recommended routes (maximum three):** [ ]  
**Dependencies / changes from earlier expectation:** [ ]  
**Decisions required from SLT (if any):** [Specific request; otherwise "None"]  
**Next milestone and accountable owner:** [ ]

---

**Definition of Done:** For the defined process variant, the Process Owner has validated the material current-state findings and intended outcome; FDE has representative evidence or explicit owned uncertainties, business measures and guardrails, the significant technical/methodological constraints, and a reasoned next disposition for each material opportunity. Gate 3 is recorded. **Outputs can be produced from one Canvas; no parallel packet of bureaucratic forms is required.**

**Enduring Stage 3 principle:** *Understand the real MRO work, independently validated decisions and evidence before committing to an AI or non-AI solution.*
