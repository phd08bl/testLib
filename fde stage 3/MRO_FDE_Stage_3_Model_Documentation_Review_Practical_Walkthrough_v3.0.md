# MRO FDE — Stage 3 Practical Walkthrough
## Model Documentation Review · Reusable Discovery Framework & Grill-Skill-Ready Specification

**Version:** 3.0 — modular, reusable and skill-ready  
**Owner:** MRO FDE / AI Tech & Tooling  
**Primary users:** FDE Leads, Process Owners, operational validators, Methodology Owners  
**Companions:** *MRO FDE Stage 3 Discovery & Operating Guide v1.2*; *Stage 3 Live Discovery Canvas*  
**Scope:** Stage 3 business/process discovery, **not** Stage 4 solution architecture or approval for production use.  
**Status of examples:** Every filled-in example is **illustrative and unverified**. Replace with actual interview findings and authorised evidence before issuing a decision.

> **Core design:** One universal discovery protocol (**U01–U08**), one six-section Canvas, and one Gate 3 standard. Add a **DOC** specialist module only where documentation-review questions clarify material facts. Use a common evidence/decision record, then generate **opportunity-specific Stage 4 Briefs** and a **parent-priority SLT Update**. A future Discovery Grill Skill can facilitate and draft; people must verify facts and authorise decisions.

---

# Part A — Core operating protocol (reusable for every MRO process)

## A1. What is reusable, and what changes?

| Layer | Reuse rule | Purpose |
|---|---|---|
| **Universal questions U01–U08** | **Stable across all MRO processes** | Consistent discovery coverage; not eight questions to read mechanically |
| **Four conversational phases** | **Stable; timing is indicative** | A natural 60-minute Process Owner conversation |
| **Six-section Discovery Canvas** | **Stable across all MRO processes** | Single structured record and common downstream inputs |
| **Evidence, uncertainty and action rules** | **Stable** | Prevent assumptions from becoming asserted facts |
| **Six Gate 3 criteria / decision authority** | **Stable, proportionate** | Determine when each opportunity is ready for further assessment |
| **Process module** | **Swap** `DOC`, `CODE`, `TEST`, `BENCH`, `RPT-GEN`, `RPT-REV`, etc. | Specialist probes for the actual work and judgement |
| **Representative work-item evidence** | **Varies by process** | A documentation review, code assessment, test, benchmark exercise or report |
| **Stage 4 Brief / SLT Update formats** | **Stable**; content varies | Detailed engineering handover versus concise leadership narrative |

**Do not** create different universal questions, Canvas structures, Gate 3 thresholds or SLT report formats for each process. **Do** add or revise specialist follow-ups as teams teach FDE how their work differs.

## A2. End-to-end engagement and accountabilities

| Step | Owner | What happens | Artefact |
|---|---|---|---|
| **0. Prepare** | FDE Lead | Review Stage 1/2 brief, known process guidance, existing tools; select process module; identify one real work item | Pre-populated Canvas, agenda, selected probes |
| **1. Discover** | FDE facilitates; Process Owner and real user explain | Conduct U01–U08 coverage through a natural work-item walkthrough; use specialist/adaptive probes selectively | Draft Canvas §§1–6, evidence links, actions |
| **2. Analyse** | FDE Lead | Separate problems, symptoms, causes and solution hypotheses; decompose consequential tasks; assess existing initiatives, success measures and critical gaps | Revised Canvas, linked opportunities, measurement plan |
| **3. Validate** | Process Owner, supported by actual users/Methodology Owner as necessary | Confirm description, business problem, desired outcome and business constraints; resolve or assign uncertainties | Validated/qualified Canvas, corrections, owner/date |
| **4. Route** | FDE recommends; delegated decision owner decides | Apply six Gate 3 criteria **per material opportunity** and record disposition | Gate 3 decision and opportunity routing |
| **5. Communicate** | FDE Lead | Prepare Stage 4 Brief only for authorised progressions; issue SLT Update at steering cadence, labelled preliminary if discovery is incomplete | Stage 4 Brief(s), one SLT Update per parent priority |

**Role boundaries:** Process Owner owns accuracy of business process/outcome and acceptance needs; Methodology Owner governs formal standards where applicable; FDE owns discovery analysis and technical recommendation; SLT retains material reprioritisation and further-wave decisions. Gate authority must follow the agreed MRO delegation, not an invented approval hierarchy.

**Effort rule:** One 60-minute call + asynchronous playback can be sufficient. Use a targeted SME follow-up only for an issue that could change scope, evidence quality, business value, risk or feasibility. The Canvas is not a form the Process Owner must complete.

## A3. Universal Question Bank — exact primary questions

These **eight primary questions are the stable contract** for every process module. Process-specific modules add follow-ups, not alternative primary questions.

| ID | Primary question (unchanged) | Primary Canvas | Main evidence needed |
|---|---|---|---|
| **U01** | **What is the purpose of this process, and what outcome is it intended to achieve?** | §1 | Purpose, trigger and genuine completion |
| **U02** | **Who performs, owns and makes the key decisions in this process?** | §1 | Operational owner, users, methodology/control authorities, variants |
| **U03** | **Could you walk us through a recent representative piece of work, from start to finish?** | §2 | Work-item trace; tasks, inputs/outputs, tools, handoffs |
| **U04** | **Which steps involve important professional judgement, controls, exceptions or dependencies?** | §2 | Decision criteria, human control, exceptions and consequences |
| **U05** | **Where are the most material problems, inefficiencies or risks in the current process?** | §3 | Impact, examples, observed symptoms, possible root causes |
| **U06** | **What improvement would be most valuable, and how could we demonstrate that it has been achieved?** | §4 | Outcome, metric, baseline/plan and quality/risk guardrails |
| **U07** | **What existing tools, information, constraints and dependencies should we consider?** | §5 | Authoritative information, usability, access, existing tools/initiatives |
| **U08** | **Which improvement opportunities appear worth exploring, and what do we need to confirm next?** | §6 | Opportunity hypotheses, owner, gaps and actions |

**Universal optional probes to retain:**

- **U03:** What happens upstream/downstream, and where are handoffs, queues, waiting or rework?
- **U04:** What if an important judgement is wrong or the process cannot complete? Who handles the consequence?
- **U07:** Is the required information sufficiently complete, reliable, current and accessible for the business task?
- **U08:** Who needs to participate in business acceptance and adoption of an improvement?

Use these only when a material answer is not already available. A single answer can fill multiple sections; **do not repeat it to satisfy the table**.

## A4. Four phases — six aligned Canvas sections (60-minute reference)

| Phase | Time | Question/Canvas sections | Facilitation priority |
|---|---:|---|---|
| **A — Frame** | 0–10 min | **§1**: U01–U02 | Purpose, real completion, scope, ownership |
| **B — Actual work** | 10–35 min | **§2**: U03–U04 | A recent representative work item, decision-making and controls |
| **C — Diagnose & value** | 35–50 min | **§3**: U05; **§4**: U06 | Material problems, evidence, expected improvement and measures |
| **D — Constraints & next action** | 50–60 min | **§5**: U07; **§6**: U08 | Existing tools, information constraints, action owners; brief readback |

**Facilitation rule:** Start broad, listen, ask a relevant specialist probe, request evidence **when consequential**, and stop probing when sufficient understanding is reached. Do not fill every field live; unresolved items become named follow-ups. This is not an interrogation, audit, requirements sign-off or AI product-design workshop.

## A5. Common Canvas capture contract (six sections)

| Canvas | Minimum useful record | Typical unanswered items to assign |
|---|---|---|
| **§1 Process & Ownership** | Purpose; trigger; genuine finish; boundaries/variants; owner, actual users and decision/methodology roles | Unclear approval or methodology authority |
| **§2 Actual Work & Decisions** | Representative work item; 5–8 meaningful steps when useful; input → judgement/action → output; actors, tools, controls, exceptions | Work item inaccessible or decision rule uncertain |
| **§3 Problems & Evidence** | Up to three important business problems; symptoms, affected parties, impact, links and root-cause status | Unverified claims or contradictory accounts |
| **§4 Desired Outcomes & Measures** | Desired outcome, one useful metric, baseline or owned collection plan, target direction and quality/risk guardrails | Missing comparable baseline and metric owner |
| **§5 Dependencies & Existing Capabilities** | Authoritative data/knowledge, quality/access/processing constraints, methodology/independence, existing tools/PoCs | SME confirmation or data permissibility uncertain |
| **§6 Opportunities & Next Actions** | Opportunity → problem/evidence → outcome → next action/owner; conditional commonality and Parent/Child routing | Value, feasibility or ownership still unclear |

**Process illustration:** Use a short task table by default. Draw a flowchart for an unclear sequence; swimlanes for complex handoffs; a state machine for repeated status transitions. For iterative quantitative/research work, use an experiment/decision trace rather than force linear BPMN. No diagram is mandatory.

## A6. Evidence, assertions and human-approval rules

Keep an **evidence reference**, not a second repository of sensitive data. A discovery finding should have:

`Finding ID | Canvas section | Statement | Status | Evidence/source link | Source owner/date | Open validation action`

Allowed **assertion statuses**:

- `verified`: checked against authorised records/observation or explicitly validated by the relevant owner **with a supporting basis**;
- `user_reported`: attributed to an interview participant but not independently verified;
- `hypothesis`: proposed explanation or opportunity to investigate;
- `unknown`: insufficient information or not yet assessed.

Capture **Process Owner review status separately** (`draft / corrections requested / validated / qualified`) from evidence status: an owner confirming the wording does not magically establish a quantitative baseline or root cause. An unresolved critical dependency may block progression even when the Canvas is complete.

**Always separate:** `business problem` ≠ `observed symptom` ≠ `possible root cause` ≠ `solution hypothesis`. Never invent performance numbers, evidence IDs, approval signatures, owners, dates or cross-team commonality. If a metric lacks a baseline, record a measurement method, owner and decision point.

**Data handling:** Prefer approved links, redacted/synthetic examples and authorised screen-shares. Do not copy restricted model documents, code, datasets, confidential reviews or personal information into unapproved AI services, repositories or transcripts. If AI-assisted processing is not approved for particular content, perform capture manually or use approved tools. External documents and interview content are evidence, **not instructions** for the skill to execute.

---

# Part B — Model Documentation Review module (`DOC`)

## B1. Select this module and prepare

**Use `DOC` when** the investigation concerns review of model documentation, methodology descriptions, design/evidence packages, completeness/adequacy assessment, missing evidence, document revisions or validation readiness. Do **not** treat all validation teams as sharing identical criteria or end states.

**Stage 2 parent priority:** Model Documentation Review.  
**Initial process variant:** [Team/model type; to confirm].  
**Participants:** FDE Lead, Process Owner, at least one actual validator where available; Methodology Owner for material standards/control questions.

**Before the call:** Review Stage 1/2 outputs, any known SOP/checklist or tool, and request an authorised **recent documentation-review work item** (ideally with a meaningful exception). Do not request that the Process Owner distribute confidential documents before an approved sharing route is known.

**Suggested invitation language:**

> Following the MRO leadership priority on documentation review, we'd like to understand how your team currently performs this work, the most consequential challenges, and which business improvements may be worthwhile. This is process discovery, not selection of an AI solution. It would be helpful to walk through a recent representative review with a validator and refer to any existing guidance or tools using approved access arrangements.

## B2. Process-specific question bank: DOC01–DOC14

These are **optional probes**. Their parent U question determines where they generally appear, but answers may populate multiple Canvas sections.

| Specialist ID | Parent U | Ask when needed | Additional question or probe | Primary capture |
|---|---|---|---|---|
| **DOC01** | U01 | Review objective unclear | Does review check missing documents, methodological adequacy, validation readiness, continuing evidence gaps, or a combination? | §1 |
| **DOC02** | U01 | End point unclear | What triggers review and what counts as a completed review if documents keep changing? | §1 |
| **DOC03** | U02 | Ownership unclear | Who sets requirements, judges evidence adequacy and approves how unresolved gaps are handled? | §§1/2 |
| **DOC04** | U02 | Possible variants | How does review differ across model families, risk/materiality, validation stage or agile updates? | §1 |
| **DOC05** | U03 | Inputs/version ambiguous | Which documents, technical artefacts and versions are received? Which copy is authoritative? | §§2/5 |
| **DOC06** | U03 | Requirement selection unclear | How are applicable documentation or methodology requirements identified? | §2 |
| **DOC07** | U03 | Decision criteria unclear | How does the validator distinguish *present*, *sufficient*, *inconsistent*, *missing* and *materially inadequate* evidence? | §2 |
| **DOC08** | U03 | Rework loop | How are clarification requests issued, updated evidence reviewed and remaining gaps recorded? | §2 |
| **DOC09** | U04 | Professional judgement | What is checklist-based versus expert judgement? How is materiality reasoned, evidenced and independently challenged? | §§2/5 |
| **DOC10** | U04 | Material exception | What happens with conflicting versions, an incomplete package, urgent validation or a material unresolved gap? | §2 |
| **DOC11** | U05 | Business problem vague | Is the material friction locating evidence, submission quality, adequacy assessment, versioning, duplicate effort or clarification loops? Which actual case demonstrates it? | §3 |
| **DOC12** | U06 | KPI/guardrail unclear | Would improved active effort, early gap identification, lower *unnecessary* rework, consistency or traceability be the meaningful business outcome? | §4 |
| **DOC13** | U07 | Information dependency | Where are authoritative records, who can use them, and are content quality, recency, permissions or retention barriers material? | §5 |
| **DOC14** | U07 | Existing capability unclear | What standards, templates, scripts, prompts, Copilot features or PoCs already help, and what remains unsolved? | §5 |

For **U08**, the universal opportunity/adoption probes normally suffice; don't invent a DOC question just to fill a numbering slot.

## B3. Call 1 facilitator script — aligned exactly to six Canvas sections

### Canvas §1 — Process & Ownership · U01–U02 · Phase A (0–10 min)

**Ask U01:** “What is the purpose of this process, and what outcome is it intended to achieve?”  
**Ask U02:** “Who performs, owns and makes the key decisions in this process?”

Choose `DOC01–DOC04` only when purpose, finish, validation/approval authority or variants are unclear. Useful natural prompts:

- “Does a review mean a completeness check, a judgement about methodological adequacy, or both?”
- “If material documentation remains outstanding, who decides what validation activity can continue?”

**Capture in §1:** Purpose; genuine start/finish; scope; team/model variant; Process Owner; actual validators; requirements/methodology authority; affected downstream activity. Mark unresolved role decisions as follow-ups.

### Canvas §2 — Actual Work & Decisions · U03–U04 · Phase B (10–35 min)

**Ask U03:** “Could you walk us through a recent representative piece of work, from start to finish?”  
**In DOC context:** “Could a validator show one recent documentation review from material receipt to the documented outcome or next action?”

Use `DOC05–DOC08` as needed:

- “What came in, and how did you know the requirements and documents were the applicable/current versions?”
- “At what point did you determine whether the information was adequate rather than simply present?”
- “What requests went to the model owner, and what happened when revised evidence arrived?”
- “What happened just before the review reached you and what happened afterwards? Where was time actively spent versus waiting?”

**Ask U04:** “Which steps involve important professional judgement, controls, exceptions or dependencies?”

Use `DOC09–DOC10` as needed:

- “Which judgement follows explicit requirements, and which relies on model-specific expertise?”
- “How are significant unresolved gaps handled, recorded and escalated?”
- “If an important review judgement were wrong, what could happen and who owns escalation?”
- “Which review/control activities must not be removed simply to save time?”

**Capture in §2:** Real work-item reference; a meaningful task/decision sequence, inputs and outputs; validators and tools; handoffs; review judgements; control/independence; key exceptions and rework. Use a task table; add a diagram **only if necessary**.

**If no case can be shown:** Use approved SOP plus a validator's recollection; mark `user_reported`, then assign an evidence-verification action. Do not fabricate a case.

### Canvas §3 — Problems & Evidence · U05 · Phase C (35–43 min)

**Ask U05:** “Where are the most material problems, inefficiencies or risks in the current process?”

Use `DOC11` or adaptive probes:

- “Which step actually creates the active effort, delay, rework or risk?”
- “Can we point to a representative case, observation or log rather than only an impression?”
- “Why might it happen? Is that established or still a hypothesis? What is different when review goes well?”

**Capture in §3:** Up to three material problems; symptom and affected users; supporting evidence/status; approximate impact; potential cause, identified as verified or hypothesised. A request to “build an agent” belongs under possible solution hypotheses, not problem definition.

### Canvas §4 — Desired Outcomes & Measures · U06 · Phase C (43–50 min)

**Ask U06:** “What improvement would be most valuable, and how could we demonstrate that it has been achieved?”

Use `DOC12` and selective probes:

- “Would the more valuable change be less time locating evidence, fewer avoidable clarification loops, earlier identification of significant gaps, or more consistent review?”
- “Do we have an observed baseline, an informed estimate, or no measurement?”
- “What one business measure and one or two quality/risk guardrails would be meaningful?”
- “If there's no baseline, who could gather comparable examples and how?”

**Capture in §4:** Outcome, primary KPI and definition (e.g. **active evidence-location time**, not unspecified “review speed”), current source/measurement plan, target direction, guardrails such as material-gap detection and source traceability, business acceptance owner.

### Canvas §5 — Dependencies & Existing Capabilities · U07 · Phase D (50–55 min)

**Ask U07:** “What existing tools, information, constraints and dependencies should we consider?”

Use `DOC13–DOC14` and the optional U07 probe:

- “Where are the authoritative documents and versions, and who controls access?”
- “Are the necessary sources sufficiently complete, current, reliable and available for the intended review?”
- “What restrictions apply to sharing, retention or AI processing? We can follow up separately with the appropriate specialist.”
- “Which existing templates, scripts, prompts, tools or PoCs already help?”

**Capture in §5:** Known source/ownership, quality/usability and restrictions, material methodological/independence dependencies, existing initiatives and what remains unresolved. Do **not** seek or promise a security/integration approval in this call.

### Canvas §6 — Opportunities & Next Actions · U08 · Phase D (55–58 min)

**Ask U08:** “Which improvement opportunities appear worth exploring, and what do we need to confirm next?”

- “Could some problems be improved through guidance or an existing process/tool, rather than new AI?”
- “Which candidate improvement is most promising in business terms?”
- “Who would help validate the result and adopt an improved workflow?”
- “What evidence is still missing, who owns it, and which other MRO team/variant would be useful to compare?”

**Capture in §6:** Opportunity, linked problem and evidence, desired outcome, indicative value, current unknowns, business acceptance participants and action owner. Classify commonality as `Unknown` until evidence across teams supports a stronger label. Do not commit to RAG, agent frameworks, integration architecture or a development plan here.

**Closing readback (58–60 min):**

> “Our working understanding is that **[process and genuine completion]**. The main issues appear to be **[up to three, with evidence/uncertainty]**. The outcome worth improving is **[outcome]** while retaining **[control or judgement]**. We will confirm **[key open items]** with **[owners]**. Is anything materially incorrect or missing?”

**Call 1 success:** Business participants recognise the process description; FDE has a real work-item trace (or documented verification gap), candidate problems, a useful outcome hypothesis and named follow-ups. Full sign-off, numerical target setting and solution design are **not** expected during the first hour.

## B4. Adapt the `DOC` module to another team/variant

Re-use validated sections of the parent priority and existing evidence rather than run a duplicate interview. Keep the universal eight questions; ask only which documentation requirements, roles, evidence sources, risk decisions, baseline or actual pain points differ. Mark process similarity `Local / Potentially Common / Clearly Common / Unknown` based on verified cross-team evidence. Stage 4, **not Stage 3**, decides whether technical architecture can be reused.

---

# Part C — Synthesis, approval and downstream outputs

## C1. From conversation to an evidence-aware Canvas

**Immediately after the call:**

1. Convert notes into the six Canvas sections; include the representative work-item source and where restrictions prevent copying it.
2. Break only **material** work into `input → judgement/decision → action → output → side effect → owner/control`; no mouse-click decomposition.
3. Distinguish problem, observed symptom, plausible root cause, and solution hypothesis.
4. Attach authorised evidence references; assign a status to every significant finding; record conflicts rather than choosing a convenient answer.
5. For each proposed business improvement, name a measurable outcome, baseline **or owned plan**, and risk/quality guardrails.
6. Check existing solutions/PoCs and business-process changes before suggesting new development.
7. Draft opportunity routes and open actions. FDE can recommend; cannot certify or authorise on behalf of the business.

### Sample task trace (illustrative, not verified)

| Task | Input → output | Judgement/control | Possible side effect |
|---|---|---|---|
| Identify applicable requirements | Model category, standards → applicable requirement set | Validator/Methodology Owner determines applicability | Incorrect selection could omit necessary challenge |
| Locate and review evidence | Approved documents → evidence notes | Distinguish *present* from *adequate* | Weak source/version provenance |
| Classify gaps | Requirements and evidence → gap record | Determine significance and uncertainty | Missed material weakness |
| Request clarification | Gap record → questions to model owner | Appropriate scope and approval | Avoidable rework or necessary challenge |
| Reassess changes and record conclusion | Updated evidence → next validation action | Validator retains independent judgement | Inaccurate acceptance or delayed testing |

### Sample Problem Statement (illustrative, not verified)

> Validators **may** spend significant active effort locating model-design evidence across changing documentation versions. This could delay review and cause duplicate requests. **Evidence required:** recent approved case trace and effort observations. **Root cause:** fragmented or outdated sources (**hypothesis**). **Desired outcome:** less evidence-location effort with preserved provenance, material gap coverage and human validation judgement.

### Sample measurement contract (illustrative, not verified)

| Outcome | Metric definition | Baseline | Target | Guardrail | Measurement owner |
|---|---|---|---|---|---|
| Reduce evidence-location effort | Active minutes spent locating/reconciling sources per comparable review | **Not established**; collect approved case observations | Direction: decrease; numeric value TBD | No loss of material gap detection; source/version traceability; validator remains accountable | Process Owner to nominate |

**Do not** invent “30% saved” or call total elapsed time active work time. For professional risk work, apparent speed is not meaningful if independent challenge degrades.

## C2. Process Owner playback and six Gate 3 criteria

**Playback (30 minutes or asynchronous for a simple case):** Show the process boundaries, task/decision map, up to three important problems, evidence statuses, measures/guardrails, constraints and opportunities. Ask for corrections. Capture **who reviewed what and when**, without implying approval the owner did not give.

**Six universal Gate 3 checks:**

- [ ] **Process/owners:** Purpose, work boundaries, roles and key decisions understood.
- [ ] **Evidence:** Material problems supported or uncertainty explicitly qualified and assigned.
- [ ] **Value:** Credible desired business outcome and indicative benefit/impact.
- [ ] **Measurement readiness:** Primary KPI and baseline **or owned, credible measurement plan**, plus guardrails.
- [ ] **Constraints:** Critical methodology, independence, information and existing-initiative dependencies considered.
- [ ] **Actions:** Process Owner validation recorded; each material opportunity has a recommended next action.

**Separate two decisions:**

| Dimension | Choices | Notes |
|---|---|---|
| **Progression** | Proceed Stage 4 / Targeted Discovery / Existing process-or-tool route / Defer / Stop | One decision **per material opportunity**, with rationale/conditions |
| **Case routing** | Remain in Parent / Recommend Child / Propose another Discovery Wave | A Child Case is justified by distinct outcome, owner, risk or delivery needs, **not merely another team** |

**Approval rule:** A filled checklist is **not automatic sign-off**. FDE records a recommendation; named delegated authority determines progression. Methodology/control exceptions require the appropriate authority. SLT owns material priority changes and later-wave direction.

## C3. Output A — Stage 4 Opportunity Brief (one to two pages per progressed opportunity)

**Prepare only when progression has been authorised.** Fields below can be generated from the Canvas, but unsupported statements must remain qualified.

| Brief field | What Stage 4 needs |
|---|---|
| Identification | Parent priority, process variant, opportunity ID, Process Owner, FDE Lead, decision reference |
| Business problem | Validated/qualified problem with **evidence references and confidence status** |
| Actual work | Bounded task/decision trace; key users, inputs/outputs and human controls |
| Desired outcome | Business objective; metric definition, baseline or measurement plan, target direction and quality/risk guardrails |
| Initial business scope | In/out boundaries, model/team variant and exclusions |
| Dependencies | Methodology, independence, authorised data/evidence, systems, operational acceptance |
| Existing approaches | Related tools/PoCs and non-AI or process options that Stage 4 should compare |
| Open design questions | Feasibility, option selection, architecture, authorised test data and evaluation design **to be resolved in Stage 4** |
| Gate/owners | Gate decision, conditions, responsibility for open actions |

**Illustrative OPP-01 (not approved):** Improve evidence identification for a bounded class of documentation reviews. Measure active evidence-location time per comparable review; preserve material gap coverage, sources/versions and validator judgement. **Stage 4 asks how to achieve and verify this; Stage 3 does not prescribe RAG or an agent.**

## C4. Output B — SLT Discovery Update (one page per parent priority)

May be issued **during discovery** as long as clearly labelled `Preliminary / In Discovery` and no hypothetical benefit is presented as realised.

1. **Leadership priority and coverage:** Parent priority, teams/variants investigated, current status.
2. **Validated findings:** Up to three material observations with the evidence maturity stated; explicitly separate emerging hypotheses.
3. **Potential outcomes/value:** Direction of improvement, proposed measures and baseline maturity; material quality/risk guardrails.
4. **Opportunities/routing:** Proceed / More Discovery / Existing initiative / Defer; material common-vs-variant findings.
5. **Dependencies/decisions:** Important blockers, business owners, further-wave recommendation and **specific SLT action only if needed**.
6. **Next action:** Owner and agreed next milestone (date only if provided).

**Example headline (illustrative):** “Documentation review discovery indicates *possible* effort in locating/versioning evidence and clarification loops; verification and baseline are outstanding. FDE recommends completing a representative case trace before assessing a bounded evidence-identification opportunity. No technology or investment decision requested at this stage.”

## C5. Stage 3 completion and quality checks

**Deliverables:** (a) one six-section Canvas **per meaningful process variant** with evidence/action references, (b) Gate 3 decision record, (c) Stage 4 Briefs **for authorised** progressing opportunities, and (d) one consolidated SLT Update for the parent priority as needed. A long standalone Discovery Report is **not mandatory**.

**Quality questions before distribution:**

- Can a reviewer trace each material claimed problem back to a source or a plainly marked assumption?
- Are business problems distinct from symptoms, root-cause theories and technology requests?
- Does each opportunity link to a problem, intended business outcome, metric/measurement plan and material guardrail?
- Have restricted information and unsupported quantitative claims been excluded?
- Did the Process Owner review the current-state understanding? Are disagreement and unresolved conditions explicit?
- Does the Stage 4 Brief say what to assess, not which implementation must be built? Does SLT see implications and decision requests, not engineering detail?

---

# Part D — Discovery Grill Skill blueprint (build-time specification, not a deployed skill)

## D1. Recommended architecture: one core plus specialist modules

```text
stage3-discovery-grill/
├── SKILL.md                      # Human-facing purpose, triggers, guardrails, workflow
├── references/
│   ├── universal-questions.md    # U01–U08, stable source of truth
│   ├── canvas-contract.md        # Six sections, evidence statuses, Gate 3
│   ├── facilitation-rules.md     # Adaptive probing, stop conditions, escalation
│   └── output-contracts.md       # Stage 4 Brief and SLT Update requirements
├── modules/
│   ├── DOC.md                    # Documentation Review: DOC01–DOC14
│   ├── CODE.md                   # Model code assessment (future)
│   ├── TEST.md                   # Independent quantitative testing (future)
│   ├── BENCH.md                  # Benchmark/challenger modelling (future)
│   ├── RPT-GEN.md                # Validation report generation (future)
│   └── RPT-REV.md                # Validation report review (future)
├── templates/
│   ├── live-discovery-canvas.md
│   ├── evidence-and-action-log.md
│   ├── gate3-record.md
│   ├── stage4-opportunity-brief.md
│   └── slt-discovery-update.md
└── tests/
    ├── synthetic-doc-review.md
    ├── synthetic-quant-testing.md
    └── expected-behaviours.md
```

**Implementation note:** This is a portable content layout for an agent-skill repository; adapt any manifest, metadata or paths to the **approved organisation-specific GitHub Copilot/agent runtime**. This document does not itself install or execute a skill. Keep approved data storage and identity/permissions outside the prompt.

## D2. Skill operating modes and allowed outputs

| Mode | Trigger/input | What the skill does | What it must **not** do |
|---|---|---|---|
| **Prepare** | Stage 1/2 brief, chosen team/process, existing approved materials | Identify gaps, select process module and candidate probes; pre-fill *clearly sourced* context | Infer a Process Owner, approved access or solution direction |
| **Interview Assist** | Human-provided notes/answers during or after a call | Suggest the **next most useful** question from uncovered U anchors/specialist triggers; draft neutral notes | Interrogate through every question, interrupt with long surveys or process live content without permission |
| **Synthesis** | Notes and authorised evidence references | Populate Canvas; separate problems/symptoms/causes/hypotheses; surface contradictions, metric gaps and open actions | Promote reported claims into verified facts; invent metrics, evidence or approvals |
| **Playback Prep** | Draft Canvas | Prepare a short Process Owner readback and corrections checklist; propose targeted SME follow-ups | Mark business validation complete without an actual response |
| **Gate Prep** | Reviewed Canvas, named authorities | Check six criteria, propose *per-opportunity* disposition and blockers | Approve Gate 3 or re-prioritise leadership decisions |
| **Output Drafting** | Gate record and Canvas | Draft Stage 4 Brief(s) **only for authorised progression**; draft preliminary or validated SLT Update with status | Call an unapproved Stage 4 Brief authorised; present projected benefit as achieved |

Human operators may work without a live assistant: the same Canvas and template remain valid. A live meeting transcript is **not** assumed available or authorised.

## D3. Module definition — required metadata

For each specialist module, maintain a small table or machine-readable equivalent:

| Field | Meaning | DOC example |
|---|---|---|
| `module_id` / `module_version` | Stable identifier and version | `DOC` / `1.0` |
| `process_scope` | When the module applies | Documentation completeness and adequacy review |
| `specialist_id` | Stable question identifier | `DOC07` |
| `parent_universal_id` | U question it supplements | `U03` |
| `trigger` | Why the question is worth asking | Adequacy criteria unclear |
| `question` | Neutral wording; one idea at a time | How is sufficient evidence distinguished from merely present information? |
| `capture_sections` | Where its answer usually contributes | `2` (and sometimes `5`) |
| `expected_evidence` | Supporting records or actor to consult | Real assessment, applicable standard, validator reasoning |
| `sensitivity_notes` | Handling or authorisation concerns | Approved artefacts only; no raw documents in unapproved tool |

**Module selection rule:** Select the actual process by the work being performed, not by the desired AI solution. If documentation review includes a separate code-assessment subprocess, follow the **relevant** probe or recommend separate targeted discovery; do not indiscriminately load two full banks.

## D4. Portable structured discovery record (illustrative YAML contract)

This is a **logical schema**, not a mandated database design. The six sections mirror the existing Canvas; store sensitive evidence through approved references.

```yaml
record_id: "[DISCOVERY-ID]"
parent_priority_id: "[STAGE-2-ID]"
team_variant: "[TEAM / VARIANT]"
process_module: "DOC"
process_owner: "[CONFIRMED ROLE/OWNER OR UNKNOWN]"
fde_lead: "[OWNER]"
status: "in_discovery"     # preparation | in_discovery | playback | gate_recorded
canvas:
  section_1_process_ownership: "[purpose, boundaries, owner, decisions]"
  section_2_actual_work: "[case reference, steps, judgement, controls]"
  section_3_problems: "[linked findings]"
  section_4_outcomes_measures: "[outcome, KPI, baseline/plan, guardrails]"
  section_5_dependencies: "[sources, restrictions, existing work]"
  section_6_opportunities: "[opportunities, actions, business acceptance]"
findings:
  - finding_id: "F-01"
    canvas_section: 3
    statement: "[specific claim; no invented facts]"
    assertion_status: "user_reported"  # verified | user_reported | hypothesis | unknown
    evidence_refs: []                  # approved links/IDs, not raw sensitive files
    validation_action: "[owner and next evidence step]"
opportunities:
  - opportunity_id: "OPP-01"
    problem_finding_ids: ["F-01"]
    outcome: "[business outcome]"
    primary_metric: "[definition or TBD]"
    baseline_status: "measurement_plan" # observed | estimated | measurement_plan | unknown
    guardrails: ["[necessary control]"]
    progression_recommendation: "targeted_discovery"
    routing_recommendation: "remain_parent"
process_owner_review:
  status: "draft"  # draft | corrections_requested | validated | qualified
  reviewer: "[actual reviewer or unknown]"
  date: null
gate3:
  readiness: "not_assessed"
  delegated_decision_authority: "[confirmed authority or unknown]"
  formal_decision: null
  decision_reference: null
```

**Traceability rule:** Every material opportunity points back to at least one Canvas §3 problem/finding and a credible outcome in §4; evidence links/status follow into Stage 4 and SLT outputs. If sources disagree, retain the disagreement. Do not produce fabricated citations, approved-case IDs or numeric claims.

## D5. Adaptive questioning policy (for the Grill)

1. **Maintain coverage**, not a count of questions asked. Track U01–U08 as `not_covered / partial / sufficient / evidence_pending` based on content, not the presence of a transcript line.
2. **Ask one high-value follow-up at a time**. Prefer missing process boundaries, consequential human decisions, real evidence, material root-cause uncertainty or outcomes over minor detail.
3. **Follow the business participant's narrative.** If U03 already revealed a pain point and tool dependency, mark U05/U07 partially covered; do not ask them again mechanically.
4. **Select specialist probes conditionally** using `trigger`, not in numerical order. More probes can be loaded offline for a specialist follow-up, never all required in Call 1.
5. **Stop or park** when a valid answer is already recorded, the timebox is nearly finished, a specialist/authorised source is needed, access restrictions apply, or additional questioning has low decision value.
6. **Challenge politely and neutrally** using a counterexample or real case; avoid assumptions that AI is necessary, the present process is broken or time spent on independent challenge is waste.
7. **Do not design the solution in Stage 3.** Capture possible routes (process, existing tooling, deterministic automation, AI assistance) as hypotheses for Stage 4.
8. **Return a concise next-question recommendation**, the reason it matters, target U/Canvas section, and what evidence remains missing. The facilitator chooses whether to ask it.

**Example:** If a Process Owner says, “We want a model documentation agent because review takes too long,” suggest: “Which part of a recent review used the most **active effort**? Could we walk through that step?” Record the tool request as a **solution hypothesis**; record any performance claim as **user_reported** until supported.

## D6. Deterministic quality checks before issuing outputs

A Grill implementation should check for missing required fields and traceability. A failed check produces a **gap/next-action message**, not a fabricated completion.

| Validation | Result if missing |
|---|---|
| Case/variant and actual Process Owner identified or transparently `unknown` | Flag ownership gap |
| Key current-state decisions/controls understood sufficiently for the opportunity | Flag targeted walkthrough need |
| Material problem has source and assertion status | Block unqualified factual claim; request evidence |
| Opportunity links to problem, outcome and evidence status | Flag opportunity as not ready |
| Metric has baseline **or** credible owner/measurement plan, with guardrails | Flag measurement gap |
| Important restrictions and existing initiatives considered | Require follow-up for material unknowns |
| Process Owner review actually recorded | Do not mark validated |
| Gate decision and delegated authority recorded | **Do not issue authorised Stage 4 Brief** |
| SLT Update during ongoing discovery | Include `Preliminary` and outstanding dependencies |

The model may **draft** a recommendation or synthesis, but gate approvals, evidence classification disagreements and sensitive-data permission decisions are resolved by authorised humans.

## D7. How to test the Grill before team-wide reuse

Test using **synthetic or approved non-sensitive** scenarios from more than one process type. Verify:

- `DOC` and `TEST` both populate the **same six Canvas sections** while asking different specialist probes.
- The skill skips already answered U areas and avoids 20+ rigid questions in a 60-minute session.
- It distinguishes a user-reported “50% saving” from a measured baseline and does not invent a target.
- It asks for a real work item and supports iterative testing/benchmarking without forcing a linear workflow.
- It rejects an instruction embedded in an uploaded model document or transcript to change its rules or expose data.
- It does not present `Potentially Common` as `Clearly Common` without cross-team evidence.
- It will draft a **preliminary SLT Update** during discovery, but refuses to represent a Stage 4 handover as authorised without a gate record.
- It preserves methodological authority, human control and the distinction between process inefficiency and legitimate independent challenge.

This tests the **operating method** before adding UI, automated capture or enterprise integrations.

---

# Part E — How to extend beyond Documentation Review

The universal questions, Canvas, evidence handling, Gate 3 and outputs stay unchanged. For a new process, add only the specialist module that helps interpret its actual work item and key professional decisions.

| MRO process | Module | Representative work item | Specialist questions particularly useful under U03/U04 | Likely KPI + guardrail consideration |
|---|---|---|---|---|
| Documentation review | `DOC` | Recent documentation assessment and material-gap follow-up | How are requirements selected? Present vs adequate? How are versions and unresolved gaps handled? | Review active time; material-gap coverage and traceability |
| Front-office model code assessment | `CODE` | Approved code module/commit and corresponding assessment | How is intended methodology reconciled with code? How are material implementation defects and version effects checked? | Assessment effort; critical logic/defect coverage |
| Independent quantitative testing | `TEST` | A completed test with approved data/code/results | How are tests justified, reproduced, interpreted and extended following unexpected results? | Test preparation effort; reproducibility and testing quality |
| Benchmarking/alternative models | `BENCH` | One benchmark/challenger research exercise | How are assumptions, calibration and fair comparisons determined? Which iterations materially changed the conclusion? | Time to defensible comparison; soundness/reproducibility |
| Validation report generation | `RPT-GEN` | One report section with source evidence and revisions | How are conclusions sourced, checked, drafted and approved? | Draft effort; factual/citation accuracy |
| Validation report review | `RPT-REV` | One report with reviewer comments and resolution trail | What constitutes material inconsistency, inadequate evidence or a decision requiring escalation? | Review rework; material issue detection/quality |

**Do not clone the whole `DOC` walkthrough for these modules.** Use Part A and Part D as the shared standard; author only (a) specialist probe IDs mapped to parent U questions, (b) a representative work-item guide, (c) a short example of six-section capture, and (d) any unique controls or data-handling constraints. This keeps the Grill maintainable and the Process Owner experience consistent.

## Final working instructions (one screen)

1. **Prepare:** Choose one MRO process variant, confirm leadership scope and ask for an approved real work item.
2. **Interview:** Four conversational phases, **U01–U08 as coverage anchors**; choose only relevant process-specific/adaptive probes.
3. **Capture:** One **six-section Canvas**, with evidence links, assertion statuses and actions. Do not ask already-covered questions again.
4. **Synthesis:** Define verified/qualified problems, measurable outcomes, guardrails and actionable opportunities; consider existing tools and non-AI fixes.
5. **Validate/Gate:** Process Owner reviews the business findings; authorised decision maker records opportunity-level progression.
6. **Communicate:** Issue **Stage 4 Opportunity Briefs** for authorised opportunities, and a concise **SLT Update** with evidence maturity and decision needs.

> **Success definition:** Stage 3 makes specialist MRO work understandable, problems evidence-aware and opportunities actionable **without pre-selecting a technology or weakening independent model validation**. The Grill Skill standardises the workflow and drafts the artefacts; it does not replace the Process Owner, Methodology Owner, FDE judgement or delegated governance authority.
