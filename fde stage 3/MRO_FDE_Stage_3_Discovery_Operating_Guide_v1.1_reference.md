# MRO FDE Operating Model — Stage 3: FDE Discovery & Process Decomposition

**Version:** 1.1 — 24 October 2026 (proposed operational standard)  
**Audience:** MRO FDE / AI Tech & Tooling, Process Owners, Methodology Owners and participating SMEs  
**Status:** Draft for adoption; adapt to existing MRO governance and approved information-handling requirements  
**Change in v1.1:** Added explicit business outcome measurement, Discovery quality criteria, problem-statement discipline, proportionate process visualisation, atomic task schema, KPI/guardrail handover and measurement-readiness gate controls.

## 1. Stage definition

### Purpose and key question

Understand how the Stage 2-prioritised business process operates in practice; validate material problems using evidence; decompose important tasks, decisions, controls and dependencies; and identify actionable improvement opportunities for Stage 4.

> **Key question:** How does the selected business process actually work, where are the material problems, what evidence supports them, and which opportunities are worth taking forward?

Stage 3 translates a broad leadership priority into an evidenced chain:

**As-is process → validated problem and root-cause hypothesis → baseline → measurable desired business outcome → actionable opportunity.**

It should not assume that AI is the solution, and should not manufacture numeric benefits to make a candidate look attractive. Stage 3 **defines** how improvement will be measured; later stages design, implement, evaluate and realise it.

### Inputs and outputs

**Entry inputs** (reuse what already exists): Stage 1 Candidate Brief; Stage 2 leadership decision and intended scope; named Process Owner or accountable sponsor; available process/methodology documents and evidence; existing tools/PoCs where known.

**Primary output:** one **FDE Discovery Pack** for the defined process variant or Discovery Wave, with six structured Cards, supporting evidence, evidence-backed problem statements, baseline and measurement records (or credible measurement plans), an Opportunity Register, Process Owner validation, a Gate 3 record, and recommended next actions.

**Boundary:** Stage 3 owns business/process discovery and initial outcome/scope definition. Stage 4 owns solution comparison, detailed MVP/architecture/design and delivery route. Detailed security approvals, build, performance evaluation, deployment and support design take place at the appropriate later stages.

### Operating principles

1. **Process before features:** Ask what work and decision are difficult, not which AI agent to build.
2. **Evidence over opinion:** Use at least one recent representative case when appropriate; trace important claims to observations or records.
3. **Real users matter:** Speak to those performing the work, not only their line managers.
4. **Separate responsibilities:** Distinguish process accountability, methodological authority, execution, technical delivery and risk acceptance.
5. **Discover locally, compare deliberately:** Start with a real team/process variant; assess commonality with other teams only when supported by evidence.
6. **No premature solution lock-in:** Consider process changes, templates, deterministic rules, conventional automation, Copilot assistance, RAG or agents as hypotheses—not Stage 3 decisions.
7. **Reuse existing assets:** Existing process maps, working tools, completed experiments and validation findings are admissible evidence; do not repeat completed work without reason.
8. **Proportionate effort:** Scale the depth to complexity, impact and uncertainty. The question bank guides interviews; it is not a compulsory questionnaire.
9. **Approved evidence handling:** Prefer links/references to controlled records; use redacted or approved sample cases, and do not paste sensitive data into unapproved AI systems or repositories.
10. **Separate symptoms, root causes and solutions:** Do not treat a requested feature as a business requirement or an unverified root cause as fact.
11. **Measure outcomes rather than paperwork:** Define the current baseline, a proposed target and safety/quality guardrails; do not use number of questions, diagrams or Cards as the measure of success.

## 2. Engagement model for an MRO-wide priority

A **Parent FDE Initiative** represents the Stage 2 leadership-prioritised theme (e.g., *Model Documentation Review*). A **Discovery Wave** investigates a defined team or meaningful process variant under the parent. A **Child FDE Case** is created only when an opportunity needs distinct ownership, scope, delivery or decision tracking.

Suggested workflow:

1. Review Stage 2 priorities and identify the starting Process Owner/team.
2. Conduct a focused discovery with that team, using real-case evidence.
3. Validate findings and record actionable opportunities.
4. Repeat with another team or process variant **only where prioritised or needed**.
5. Compare cross-team findings: common requirements, variant requirements, existing initiatives and potentially reusable components.
6. Send mature opportunities to Stage 4 without waiting for every possible MRO team; recommend new waves to the leadership prioritisation owner.

**Important:** Similar business needs do not necessarily imply identical processes, acceptance criteria or technical solutions. Classify business-level commonality in Stage 3; decide engineering reuse in Stage 4.

## 3. Responsibility model

| Role | Responsibility in Stage 3 | Decision boundary |
|---|---|---|
| **FDE Lead** | Plans discovery; facilitates sessions; maps workflow, tasks and evidence; authors Cards and Discovery Pack; recommends opportunities | Owns quality of technical/business discovery and recommendation, not the business priority |
| **Process Owner** | Explains intended business outcome and process; provides access to users/examples; confirms as-is findings, scope and value hypothesis | Accountable for business-process truth and desired outcome; does not unilaterally approve enterprise architecture |
| **Methodology Owner (where relevant)** | Validates specialist methodology, judgement criteria, policy interpretation, controls and proposed changes to methodology | Retains authority for methodology or policy content under existing governance |
| **Operational users / SMEs** | Walk through actual cases, normal and exception paths, workarounds, delays and judgement | Validate operational reality; not automatically accountable for final business decisions |
| **Team leads / handoff owners** | Clarify dependencies, capacity, handoffs, queues, escalation and cross-team interactions | Confirm team processes and operational responsibilities |
| **Tech/Data/Platform/Security SMEs (conditional)** | Advise on data access, restrictions, existing services and potential hard blockers | Provide domain assessments; detailed design/approval occurs in later stages |
| **SLT / Stage 2 priority owner** | Retains authority over changed leadership priorities, material rescope, later Discovery Waves and resource prioritisation | Not required to sign off every routine Stage 3 Card |

**Three cross-cutting lines of evidence:**
- **Business Value:** problem, baseline, outcome, materiality and value evidence (Process Owner lead).
- **Engineering Credibility:** data, systems, traceability, permissions, constraints and failure consequences (FDE lead with relevant SMEs).
- **Organisational Adoption:** users, operating entry point, handoffs, business-rule ownership, feedback and ongoing accountability (Process Owner with FDE).

## 4. Stage 3 structure: seven activities

| Step | Purpose | Minimum activity and output | Main Card(s) |
|---|---|---|---|
| **3.1 Business context & ownership** | Confirm what is being investigated and who owns decisions | Review Stage 2; define the discovery boundary; distinguish business problem, observed symptom and proposed feature; identify Process/Methodology Owners and real users | C3-01 |
| **3.2 Real-case walkthrough & current state** | Establish how work truly happens | Walk a recent case; map trigger through genuine completion, roles, handoffs, controls and exceptions; choose simple flowchart, swimlane/BPMN or state model only as useful | C3-02 |
| **3.3 Problems, baselines & value** | Establish verified problem and measurable improvement objective | Use standard problem statements; distinguish symptom/root cause/hypothesis; capture baseline or owned measurement plan; propose 1–3 outcome metrics and needed guardrails | C3-03 |
| **3.4 Task/decision decomposition & opportunities** | Identify the material work units and their human/control boundaries | Decompose into input–judgement–action–output–side effect–owner; map existing tools and possible commonality; form improvement opportunities without selecting a solution | C3-04 and Opportunity Register |
| **3.5 Data, systems & initial feasibility** | Surface material dependencies and constraints | Identify authoritative evidence/data, quality, owners, permissions, systems, constraints, failure consequences and existing initiatives | C3-05 |
| **3.6 Outcomes, scope & adoption** | Confirm desired result and useful first boundary | Validate outcome measures and proposed targets/acceptance approach with business owner; define target users, scope, exclusions, adoption needs and opportunity routes | C3-06 and Opportunity Register |
| **3.7 Playback, validation & Gate 3** | Confirm sufficient evidence and measurement readiness | Review current state, verified problems, unresolved assumptions, KPI baselines/plans, guardrails and opportunity next actions; record Process Owner validation and gate decision | Discovery Pack and Gate 3 record |

**These are activities, not seven approvals.** They may overlap and be completed through one or multiple conversations. The six Cards remain the standard; no seventh KPI Card is required.

## 5. Practical operating guide: calls with a Process Owner

### 5.1 Before the first engagement (FDE preparation)

**FDE lead actions:**
1. Read Stage 1 Candidate Brief and Stage 2 decision; write one sentence on what SLT has prioritised and what it has *not* decided.
2. Review existing process maps, methodology documents, tools and open initiatives available through approved locations.
3. Draft an initial process boundary as a **hypothesis**, not a conclusion.
4. Identify the Process Owner, likely real users, potential Methodology Owner and critical handoff owners.
5. Prepare 8–10 core questions, including at least one question on **current measures** (active/waiting/cycle time, quality or risk) and one on what success would look like; adapt the longer question bank below.
6. Ask the owner to bring a recent representative case, relevant templates, existing performance/effort measures if any, and one known exception or rework case where practicable. Use approved/redacted evidence and screen sharing if copying is inappropriate.
7. Agree whether this is a single-team wave or a wider discovery and who can validate the findings.

**Minimal invitation agenda:**
- Confirm process purpose, boundary and current challenges.
- Walk through one real case and important handoffs/decisions.
- Identify pain points, existing baseline information, desired measurable outcomes and relevant evidence.
- Agree any further SMEs/case examples and next actions.

Do **not** send all discovery questions as a form for the owner to complete.

### 5.2 Call 1 — Process Owner Discovery (suggested 60 minutes)

| Minutes | Topic | Facilitation prompt | Capture |
|---:|---|---|---|
| 0–5 | Purpose and mandate | “Leadership has prioritised improving this process; today we want to understand the work, not select a tool.” | Stage 2 linkage, objectives |
| 5–15 | Scope and ownership | “What starts and genuinely completes this process? Who owns the result and the methodology?” | C3-01 |
| 15–35 | Real-case walkthrough | “Could we follow a recent case from the trigger through to its final output, including approvals and handoffs?” | C3-02; evidence references |
| 35–45 | Pain points and exceptions | “Where did it slow down, involve rework, or require expert judgement? What happens when the information is missing?” | C3-02 and C3-03 |
| 45–55 | Value and outcome | “Which measure best reflects the problem today: active time, waiting, errors, rework or missed material gaps? What improvement and quality guardrail matter?” | C3-03 KPI record and C3-06 |
| 55–60 | Confirm actions | “What have we missed? Who should we speak to, and which examples can we inspect?” | Actions; unresolved assumptions |

**Call 1 should achieve:** a credible first process map, clear owner, priority pain points, evidence requests and named follow-ups. It does **not** need to finish solution scoping.

### 5.3 Between calls (FDE synthesis)

Within the normal working cycle, FDE:
- drafts C3-01 to C3-03 and an initial process map;
- lists claims by **verified fact / owner statement / assumption / hypothesis**;
- adds evidence links rather than duplicating business-sensitive records;
- identifies task steps requiring deeper decomposition, material exceptions and possible control issues;
- drafts one standard problem statement per **material** issue, separating observed symptom, evidence, root-cause hypothesis and solution hypothesis;
- drafts a baseline/measurement row for each major candidate outcome (including `Not available` plus how/who/when if needed);
- sends a short factual summary and open questions for review.

### 5.4 Call 2 — Detailed walkthrough / SME session (typically 60–75 minutes; conditional)

Invite actual users and the Methodology Owner when required. Use this call only when the first conversation did not establish enough evidence.

| Topic | Questions to resolve | Record |
|---|---|---|
| Task and decision decomposition | What is read/checked/decided at each material step? Which rules are written, and which depend on experience? | C3-04 |
| Controls and exceptions | Which decisions require human approval? Who handles missing information or failure? | C3-02/C3-04/C3-05 |
| Systems and evidence | Which source is authoritative? What access and quality limitations exist? Can sample access differ from operational access? | C3-05 |
| Root cause and baseline | What proportion is waiting versus active work? How could baseline and follow-on outcomes be measured? Is the root cause confirmed or hypothetical? | C3-03 Problem + Measurement records |
| Existing solutions | Are prompts, scripts, Copilot tools, validation-platform components or PoCs already addressing this? | C3-04/C3-05 |
| Scope and adoption | Which first outcome is useful? Who accepts the work, maintains business rules and operates the improved process? | C3-06 |

Use a live walkthrough, not a slide-based requirements interrogation, wherever possible.

### 5.5 Playback / Gate discussion (typically 30–45 minutes, or asynchronous for simple cases)

FDE presents a **one-page process summary and concise Opportunity Register**, then asks the Process Owner and relevant Methodology Owner to:
1. Confirm process boundary, handoffs, judgements, controls and significant exceptions.
2. Correct factual disagreements and identify missing evidence.
3. Confirm the material pain points, supporting evidence and **problem statements** (including what remains a root-cause hypothesis).
4. Agree the proposed business outcome metrics, baseline confidence/measurement plan, any numeric targets and non-degradation guardrails; note any unresolved acceptance questions for Stage 4.
5. Agree which opportunities are ready for Stage 4, need more targeted discovery or can be addressed by existing work.
6. Confirm whether opportunities need separate Child Cases and whether a further Discovery Wave should be recommended.

Record validation, decision owner, date, rationale, conditions and next actions. Escalate only material changes to Stage 2 priorities to the appropriate leadership owner.

### 5.6 One-call lightweight path

For a well-understood, narrow process with adequate existing evidence, a 60-minute Process Owner session, short user confirmation and asynchronous validation may suffice. Do not impose Calls 2 and 3 simply because they appear in this guide. Conversely, complex judgement-heavy or cross-team work may require several focused SME sessions.

## 6. Stage 3 Cards — standard schema

All Cards share metadata: **Parent Case ID, Discovery Wave / Team, Process Variant, Process Owner, FDE Lead, version/date, status, evidence links, assumptions and actions**. Keep them as sections of one record, not necessarily six separate pages.

### C3-01 — Business Context & Ownership

**Required:** Stage 2 priority/reference; business problem *without assuming a solution*; process purpose; discovery boundary; Process Owner; target users; intended output; initial participants; decisions/approval authority.  
**Where relevant:** Methodology Owner; control owners; cross-team dependencies; discovery constraints.

**Prompt:** “What is the business outcome and who can confirm it is satisfactory? What did the requester propose, and what problem is that proposal intended to solve?”

### C3-02 — As-Is Process & Real-Case Evidence

**Required:** Trigger; genuine completion; core steps and inputs/outputs; principal users/systems; significant decisions, handoffs, exceptions, rework and controls; case evidence link.  
**Where relevant:** Swimlane/BPMN, state transitions, escalation paths, waiting-time estimates, multiple variants.

| Step ID | Task / handoff | Actor | Input → output | Decision / control | System | Active / wait | Exception / evidence |
|---|---|---|---|---|---|---|---|
| P01 | [Describe] | [Role] | [From → to] | [Criteria] | [Tool] | [Estimate] | [ID/link] |

**Process modelling guidance — choose the lightest useful notation:**

| Method | Use it when | Not necessary when |
|---|---|---|
| **Simple flowchart or process table (default)** | Linear or moderately branched workflow; need to establish steps and pain points quickly | — |
| **Swimlane / BPMN** | Multiple actors or teams, repeated handoffs, approvals, waiting, control transfers or unclear responsibility | Single-actor or straightforward processes; formal BPMN syntax adds no decision value |
| **State-transition model** | A business object changes status through rework, evidence requests, pauses, re-assessment or approval; entry/exit criteria matter | State transitions are trivial or an ordinary flowchart is enough |
| **Combined swimlane + state model** | Both role handoffs **and** status/transition logic materially affect the problem | Most simple discovery waves |

Example states to **verify**, not assume: `Submitted → Under review → Additional evidence requested → Re-reviewed → Accepted / Escalated`. Record **who** authorises each transition and what evidence is needed. Diagrams are optional aids to understanding, not mandatory deliverables.

### C3-03 — Problem, Baseline & Business Value (enhanced)

Create **one problem entry for each material pain point**. Avoid blending statements such as “we need a RAG agent” with observed business problems.

**Standard verifiable Problem Statement**

| Field | Capture |
|---|---|
| Problem ID / linked step | PP-__ / P__ |
| Affected process and users | Which review or decision, and who experiences the impact? |
| **Current state / observed symptom** | What *actually* happens in a recent case? |
| **Evidence and impact** | Case reference, process measurements, frequency/scale, quality or risk consequence |
| **Root-cause hypothesis** | Why might it happen? `Verified` / `Likely` / `Unknown`, with supporting or contradictory evidence |
| Workaround | How is the current issue managed? |
| **Desired outcome** | What would be different in business terms? |
| Constraints | Methodology, independence, control or access conditions that must remain |
| **Solution hypothesis (separate)** | Possible process/tool/AI approach; *not a validated requirement or selected solution* |
| Validation action | What would confirm/refute the root cause or problem? Owner and timing |

**Disambiguation to use in Discovery Grill:**

| Type | Example (hypothetical) |
|---|---|
| Business problem | Validators expend material effort finding and reconciling evidence before assessing documentation adequacy |
| Observed symptom | Repeated searches, follow-up emails and re-reading across artefacts |
| Possible root cause | Evidence sources may be fragmented, missing, changing or subject to unclear requirements |
| Solution hypothesis | Improve submission standards, use deterministic checks or trial AI-assisted evidence retrieval |
| Evidence needed | Real case traces, gap requests, timing breakdown and Process Owner/validator confirmation |

**Measurement Record (a repeated table in C3-03 — no new Card):**

| Field | What FDE must record |
|---|---|
| Metric ID and name | `KPI-01`, e.g., Review Active Time |
| Linked outcome, problem and opportunity | IDs, meaningful business decision it supports |
| Definition and unit | Precisely what counts: minutes per review, missing-items detected, etc.; denominator and observation window |
| **Baseline** | Measured / estimated / unavailable; numeric value **only if evidenced** |
| Baseline source, period and confidence | Approved records, sample sizes, method, owner; label estimate and uncertainty |
| **Proposed target** | Value/direction agreed by owner; `TBD` when evidence is insufficient. Never assume arbitrary percentages |
| **Measurement method and source** | How and by whom the metric will be collected; comparable before/after cases |
| **Guardrail / control constraint** | Quality, risk or human approval condition that must not degrade |
| Business metric owner | Person accountable for agreeing the outcome/target |
| If baseline absent: measurement plan | Who will collect what, from which cases, by when, and **before which subsequent evaluation/design decision** |
| Later-stage verification | Stage 4 details evaluation/acceptance design; Stage 5/6/7 demonstrate results; Stage 8 tracks realised benefits |

**Do not confuse:**

- **Baseline:** observed/estimated *current* performance, with method and confidence.
- **Target:** desired *future* business improvement; a proposal until Process Owner agreement.
- **Acceptance criteria:** the evidence and conditions needed for the business to accept a specific solution or workflow (may combine target, quality thresholds, risk constraints, manual controls and usability). Stage 3 drafts the business intent; Stage 4 makes the criteria technically testable.

**Relevant MRO metric dimensions (choose 1–3 primary indicators per material opportunity, plus guardrails):**

| Dimension | Candidate metrics | What it would demonstrate |
|---|---|---|
| Efficiency | Total cycle time, active reviewer effort, waiting time, rework time | Where time is consumed and what could improve |
| Quality | Completeness/error rate, consistency, rework caused by inaccurate outputs | Whether outcomes improve or degrade |
| Risk & control | Material evidence-gap detection, missed significant gaps, traceability, required reviewer approvals | Whether critical risk standards are preserved |
| Capacity | Cases per reviewer/time period, throughput, backlog | Whether workload or capacity improves |
| Adoption & usability | Eligible-user use, intervention/override rate, feedback, user effort | Whether the solution becomes useful in practice |

**Important distinction:** `Cycle time = end-to-end elapsed duration`; `Active time = people actively working`; `Waiting time = delays awaiting inputs/handoffs`. They are not interchangeable. MRO value is usually efficiency, quality and risk assurance rather than direct revenue.

**Metric example (illustrative, no invented values):** `KPI-01: Active reviewer minutes per model-documentation review; baseline = to be measured from approved case samples; target = propose after baseline and Process Owner discussion; guardrail = no unacceptable deterioration in detection of material evidence gaps; measurement owner = [role]; method = sample comparable cases at agreed milestones.`

### C3-04 — Task, Decision & Opportunity Inventory (enhanced)

Use **business-meaningful task atomicity**, not clicks or keystrokes. Decompose until a unit has a clear input, decision/action, output, owner and risk/control consequence. Stop when a finer split would not affect improvement, responsibility or the Stage 4 choice.

| Task ID | Purpose / subprocess | Input | **Judgement / rule** | **Action** | Output | **Side effect / consequence** | Responsible role | Required control | Evidence / pain point | Existing initiative | Common/variant |
|---|---|---|---|---|---|---|---|---|---|---|---|
| T01 | [Task] | [Input] | [Criteria] | [Action] | [Output] | [e.g., official status change, request for clarification, delay] | [Role] | [Review/approval] | [EV/PP] | [Link] | [Class] |

The **side effect** is particularly important for MRO: *drafting a report section* is not equivalent to *altering a model risk record*, assigning materiality or making a formal approval. Capture whether the task reads, drafts/recommends, communicates, or **changes authoritative records**.

Record which judgements are codified in policy/methodology and which are tacit or case-dependent. Human professional judgement and methodology ownership remain explicit.

**Reuse classification:** `Local` / `Potentially Common` / `Clearly Common` / `Unknown`. Classify **business requirements and process similarities** here; do not pre-decide technology reuse.

### C3-05 — Systems, Data, Knowledge & Constraints

| Source / system | Purpose / authoritative? | Owner | Data quality / traceability | Access / restriction | Operational dependency | Existing tools / PoCs | Risk / unknown |
|---|---|---|---|---|---|---|---|
| [Name] | [Purpose] | [Owner] | [Status] | [Boundary] | [Need] | [Link] | [Risk] |

Capture important information sources and expert knowledge, not just APIs. Screen for sensitive data, approvals, live access versus PoC samples, and failure/rollback implications **at requirement level**; postpone engineering design to Stage 4+.

### C3-06 — Business Outcomes, Scope & Adoption

**Required:** desired business outcome; intended users; **C3-03 metric ID(s), baseline status, proposed target and guardrail**; initial scope and exclusions; Process Owner acceptance of the intended outcome; dependencies; human accountability and adoption assumptions.  
**Where relevant:** recommended process variant, methodology change dependency, knowledge asset owner, feedback/support owner, Parent/Child Case suggestion and next Discovery Wave.

**Scope principle:** Stage 3 specifies the **minimum valuable business outcome**; Stage 4 defines the **technical MVP**. Agreement on a target in Stage 3 does not constitute technical acceptance or production authorisation.

## 7. Registers and controlled evidence

### 7.1 Opportunity Register (repeating records, not another mandatory Card)

| Field | Example / instruction |
|---|---|
| Opportunity ID / Parent ID | OPP-001 / MRO-DOC-REV |
| Team / process variant / step | [Team, variant, P## / T##] |
| Problem and root cause | [What prevents the desired outcome?] |
| Supporting evidence | [Evidence IDs; confidence] |
| Intended outcome / **metric IDs** | [Business improvement; link C3-03 KPI-__ record(s)] |
| Baseline / proposed target status | Measured / estimated / measurement plan; owner-confirmed target or TBD |
| Guardrail / acceptance considerations | Quality, risk, independence, reviewer approval conditions |
| Indicative value | High / Medium / Low + explanation; not a substitute for SLT priority |
| Relevant existing initiative | [Tool, PoC, policy work or none known] |
| Material data/control/adoption constraints | [Short note] |
| Common-vs-variant | Local / Potentially Common / Clearly Common / Unknown |
| Progression status | Stage 4 / Targeted Discovery / Existing initiative / Defer / Stop |
| Case routing | Parent / Recommend Child Case / TBD |
| Accountable owner and next action | [Name/role and action] |

An opportunity can be recommended for Stage 4 **and** for separate Child Case tracking: progression and case routing are different dimensions.

### 7.2 Evidence Register

| Evidence ID | Source / approved link | What it supports | Process step / finding | Owner / date | Verification |
|---|---|---|---|---|---|
| EV-001 | [Approved location] | [Claim] | P03 / PP-01 | [Owner/date] | Verified / Owner-reported / Assumed |

**Do not reproduce sensitive model documents, candidate data or credentials in the register.** Link to authorised records; record permissions and retention where relevant. For AI-assisted processing, use only services and materials permitted by the organisation.

### 7.3 Assumption and decision log

| ID | Type | Statement / decision | Impact | Owner | Verification / rationale | Status / date |
|---|---|---|---|---|---|---|
| A-01 | Assumption | [Unknown] | [Impact] | [Owner] | [How tested] | [Status] |
| D-01 | Decision | [What was agreed] | [Scope effect] | [Authority] | [Evidence] | [Date] |

Distinguish **fact, assumption, hypothesis, dependency and risk**. No one needs a long log: record material items only.

## 8. Interview question bank (select, do not interrogate)

### A. Business problem and value

- Can the team complete the process today? If not, what fails and why?
- What is the real problem behind the requested feature or proposed AI solution?
- What would materially improve if it were solved? How would users know?
- How often does the problem occur? What is its impact even if infrequent?
- What current measures exist for time, quality, rework or risk? **Which parts are active work, waiting and total elapsed time?** If absent, who could measure which cases, how and when?
- What 1–3 business metrics best reflect improvement, and which quality/risk condition must **not** worsen?
- What is observed versus estimated? Is a proposed target grounded or merely aspirational?

### B. Real workflow, decisions and exceptions

- What triggers the process, and what constitutes genuine completion?
- Please walk through one recent normal case and, if available, an exception.
- Who supplies each input and receives each output? Where are waiting and handoffs?
- Which steps are human, automated or mixed? How are the decisions made?
- Which rules are documented and which rely on tacit experience? What are the **input, judgement, action, output, side effect and owner** of the material task?
- Where does work loop back, fail or need approval/escalation? Do status transitions or cross-role handoffs need explicit mapping?

### C. Data, systems and knowledge

- What information is needed for each consequential decision? Where is the authoritative source?
- Who owns it; how complete, accurate and current is it?
- Can users and any future solution access it lawfully and under existing permissions?
- Do PoC samples differ from live operational access or restrictions?
- Are there experienced SMEs and enough historical cases to verify expected behaviour?
- Which existing systems, scripts, templates or PoCs already assist this task?

### D. Risk, ownership and adoption

- Which decisions must remain subject to human review or approval?
- What are the consequences of an incorrect result or a failed workflow, and who takes over?
- Who owns the business outcome, specialist methodology and business-rule updates?
- Which users need to change how they work? What adoption obstacles are likely?
- Who would accept the result and provide ongoing business feedback?

**Drill-down prompts:** “Can you show one example?”, “How often?”, “What evidence supports that?”, “What happens when it fails?”, “Who decides?”, “Is that a policy rule or an individual preference?”, “Would removing this step solve the problem without AI?”

## 8.1 Discovery success: quality standards versus outcome KPIs

**Two levels must not be conflated.**

1. **Stage 3 Discovery Quality** answers whether discovery is evidence-backed and ready for decision. These are qualitative **Gate 3 criteria**, not promises that a tool has delivered benefits.
2. **Business Outcome Metrics** state what an eventual improvement is expected to achieve and how it can be tested later. They are owned by the business and refined/tested across Stages 4–8.

| Discovery quality dimension | Gate 3 evidence / practical test |
|---|---|
| **Process understanding** | Process Owner has checked workflow, decisions, handoffs, controls and completion criteria |
| **Evidence quality** | Material findings trace to a real case/record or carry explicit uncertainty/validation action |
| **Problem validation** | Material business problems are distinguished from symptoms, root-cause hypotheses and proposed features |
| **Value & measurement readiness** | Material Stage 4 candidates have 1–3 useful metrics, baseline with source/confidence **or** owned measurement plan, and appropriate guardrails |
| **Actionability** | Each material opportunity has a bounded outcome, accountable business owner, material constraints and explicit progression/case routing |

**Do not use document volume as performance:** number of interview questions answered, BPMN diagrams created or opportunities generated are not indicators of quality.

**Optional programme-level measures, once FDE has enough history:** proportion of Stage 3 packs returned from Stage 4 for unclear requirements; evidence traceability rate for material findings; baseline/measurement readiness rate for progressing opportunities; time from Process Owner engagement to validated Gate 3, segmented by complexity. Establish definitions and baselines before setting targets; avoid incentivising shallow discovery merely to increase first-pass gate completion.

## 9. Stage 3 checklist and Gate 3

### Core exit checklist

- [ ] Stage 2 priority and discovery boundary understood.
- [ ] Process Owner and any material Methodology/approval authority identified.
- [ ] Trigger, genuine completion, core steps and significant handoffs understood, with suitable process representation.
- [ ] Real user work and at least one representative recent case examined where accessible and appropriate; justified alternative if unavailable.
- [ ] Important tasks decomposed sufficiently to understand **input, judgement, action, output, side effect, owner and controls**.
- [ ] Material exceptions, rework, failure and escalation responsibilities considered.
- [ ] **Verifiable problem statements** documented: current state, affected users, evidence/impact, likely root cause, desired outcome and constraints.
- [ ] Observed symptoms, unverified root-cause hypotheses and solution hypotheses explicitly separated.
- [ ] Material problems linked to evidence, or evidence gaps labelled and actions assigned.
- [ ] **Measurement readiness:** for each material Stage 4 candidate, 1–3 primary business outcome metrics, an evidenced baseline **or a credible owner/date/method plan**, a proposed target (or justified `TBD`) and appropriate guardrail(s) are captured.
- [ ] Business metric definitions distinguish cycle, active and waiting time where applicable.
- [ ] Material data sources, restrictions, system dependencies and uncertainties identified.
- [ ] Existing relevant tools/PoCs/initiatives considered.
- [ ] Improvement opportunities described without premature technology selection.
- [ ] Common/variant potential classified (including `Unknown` where appropriate).
- [ ] Desired outcomes, initial business scope, exclusions and business acceptance owner established.
- [ ] Process Owner has reviewed and confirmed the findings, with disagreements documented.
- [ ] Every material opportunity has a progression recommendation, owner and next action; case routing/wave recommendation recorded where relevant.

**Conditional:** Detailed BPMN/swimlane, state machine, formal RACI, quantitative business case, dedicated technical/security review, multiple real cases and further team interviews. Apply only where complexity and consequence justify them.

### Gate G3 — Is the process sufficiently understood **and measurable** to act?

**Entry:** Stage 2 selected the priority; a defined process variant/wave exists; discovery owner and relevant business owner are identified.  
**Exit:** Critical business facts are sufficiently validated; material uncertainties are visible and assigned; problem/expected outcome/initial scope are clear; **measurement readiness** is adequate for the recommended next action; Process Owner confirmation is recorded.

**Measurement-readiness decision rule:**

- A **measured** baseline is preferred but **not always mandatory** for Stage 4 entry.
- An **estimated** baseline is acceptable if it is labelled, defensible, sourced and suitable for initial option design.
- If no credible baseline exists, Stage 3 may proceed **conditionally** only when it specifies the metric definition, source/case sampling, owner, planned collection timing, intended comparison and the downstream milestone at which evidence must be available (e.g., before PoC success evaluation). The business owner must agree the uncertainty and condition.
- Do **not** claim validated business value, make ungrounded percentage targets, or begin unrestricted build where success cannot be measured. If missing data/control information undermines feasibility or valid evaluation, choose targeted Discovery or narrow scope instead.
- Stage 4 refines solution-specific acceptance criteria and evaluation design; Gate 3 **does not** certify achievement of any target.

**Overall Wave/Variant Gate:** `Complete—ready for opportunity routing` / `Complete with explicit Stage 4 conditions` / `Targeted Discovery required` / `Return/revise` / `Stop or refer for leadership decision`.

**Per-opportunity progression:** `Proceed to Stage 4` / `Continue Targeted Discovery` / `Use or merge with existing initiative` / `Defer` / `Stop`.

**Per-opportunity case routing:** `Remain in Parent` / `Recommend Child Case` / `To be decided`.

**Leadership scope:** SLT or delegated Stage 2 authority retains prioritisation and authorises material reprioritisation or additional waves outside the approved scope. FDE recommendation and Process Owner acceptance do not silently replace that authority.

**Gate record must contain:** wave/variant ID; Process Owner confirmation; FDE recommendation; summary of material evidence and problem statements; **metric readiness by progressing opportunity** (baseline status, target/guardrail, conditions and owner); unresolved dependencies; per-opportunity disposition; Child Case/next-wave request; decision authority/date; next actions. A ticked checklist is **not** automatic authorisation.

## 10. FDE Discovery Pack template

Use **one concise pack**. Include detail by linked Cards and evidence rather than copying entire transcripts or documents.

1. **Executive summary (half to one page):** Stage 2 priority, process variant/team, real problem, high-level findings and FDE recommendation.
2. **Discovery scope and accountability:** Process Owner, Methodology Owner if applicable, covered/not-covered process areas, participants.
3. **As-is process and case evidence:** annotated workflow, key roles, handoffs, controls, exceptions and case references.
4. **Verifiable problem statements, baselines and value:** current state, evidence/impact, explicit symptom–root cause–solution-hypothesis distinction, and a C3-03 Measurement Record (metric definition, baseline/source, proposed target, guardrail, owner or measurement plan) for major opportunities.
5. **Task/decision decomposition:** material tasks represented as input–judgement–action–output–side effect–owner, plus human judgement/control boundaries.
6. **Systems, data, knowledge and constraints:** authoritative sources, access, quality, restrictions, relevant existing solutions and feasibility unknowns.
7. **Opportunity Register:** outcome, indicative value, business-level reuse class, existing initiative and next action.
8. **Outcomes, scope and adoption:** expected business result, proposed business target, necessary risk/quality guardrails, preliminary acceptance approach, exclusions, target users and ownership.
9. **Cross-team/common-versus-variant synthesis:** only when multiple variants have been reviewed; otherwise state `Not yet assessed`.
10. **Decision and next steps:** Process Owner validation, **measurement-readiness status/conditions**, gate outcome, opportunity progressions, Child Case recommendations, wave recommendation, Stage 4 questions and owners.

## 11. Worked example: MRO Model Documentation Review

**This is an illustrative discovery hypothesis—not a statement of how any particular MRO team actually operates. Verify with each Process Owner.**

### Parent priority

“Improve model documentation review efficiency and effectiveness across relevant MRO processes.” Stage 2 has selected the priority; it has **not** necessarily selected an AI agent or one shared solution.

### Initial process hypothesis to test in interviews

1. Receive model documentation / submission or updated artefacts.
2. Identify applicable model category, methodology and documentary requirements.
3. Check whether required materials are present and current.
4. Assess sufficiency, consistency and evidence supporting the methodology and key risks.
5. Document gaps, query the model owner, obtain responses and re-review.
6. Record readiness, residual gaps or validation approach under applicable governance.

Do not assume this is identical for Trade Surveillance, Economic Models, AI IVT or other teams.

### Process Owner Call 1: example questions

- Where does documentation review begin in your validation process, and what marks the end?
- Could we use a recent example to trace what the validator read, checked, decided and sent back?
- Does your team primarily need completeness checking, adequacy assessment, risk-based gap evaluation, or something else?
- Which expectations come from formal policy/methodology versus specialist judgment?
- Where do repeated queries or waiting occur? Is it due to absent content, scattered content, ambiguity or frequent changes?
- How do you deal with incomplete documentation today? Can validation proceed subject to additional evidence?
- What tools or review checklists are already used?
- What improvement would matter most, and how could we measure it? Can we separate review **active effort**, **waiting time**, and end-to-end **cycle time**?
- What current evidence could define the baseline? If none exists, who can sample cases and by when?
- Which risk or quality outcome must not deteriorate even if time is reduced?
- Who owns the review methodology and who signs off the relevant decision?

### Example task split

| Task | Possible problem to verify | Evidence to request | Stage 3 outcome |
|---|---|---|---|
| Locate required documents | Evidence scattered across repositories | Sample submission index and validator walkthrough | Confirm source, retrieval friction and ownership |
| Check presence of required sections | Repetitive checking and late missing items | Checklist/template, sample gap requests | Capture deterministic requirements and exceptions |
| Assess adequacy and methodology | Specialist judgement and tacit knowledge | Two contrasting case decisions, applicable methodology | Capture judgement criteria and human accountability |
| Clarify gaps with model owner | Repeated correspondence / long waiting | Approved examples of queries, timestamps, response cycles | Establish handoff and baseline |
| Determine what can proceed | Different risk tolerances and workflow variants | Readiness/risk decisions, controls and owners | Define desired outcome and scope boundary |

### Example problem, task and KPI records (hypotheses only)

**Problem statement example — to verify:** “In [team/variant], validators may spend substantial manual time locating methodology evidence dispersed across versions of documentation. This may delay identification of relevant evidence gaps. The underlying cause and scale require confirmation from recent case records. The desired outcome is faster evidence identification **without reducing detection of material gaps**.”

**Symptom ≠ cause ≠ solution:** Multiple clarification emails are an observed *symptom* only if case records show them; fragmented evidence is a *root-cause hypothesis* until checked; a retrieval-based AI assistant is a *solution hypothesis*, not an approved requirement.

**Material task:** Input = submission and standard; Judgement = determine whether evidence supports the methodology requirement; Action = identify gap/request clarification; Output = cited gap list; Side effect = possible model-owner rework and validation delay; Owner = validator; Required control = human judgement under methodology.

**Suggested KPI record candidates** (do not invent values or targets):

| Metric | Definition for Stage 3 | Baseline status | Proposed target at Discovery | Guardrail / later assessment |
|---|---|---|---|---|
| `KPI-01` Active review effort | Human active minutes spent inspecting documentation per review, by agreed case type | Request existing time/case records; otherwise measurement plan | `TBD`, discuss after baseline | No unacceptable worsening of material-gap identification |
| `KPI-02` Rework cycles | Number of additional evidence/clarification cycles per review | Sample approved cases and correspondence timestamps | `TBD`, owner discussion | No bypassing required methodology or approvals |
| `KPI-03` Material gap detection | Relevant material evidence gaps identified against agreed expert-reviewed cases | Expert-reviewed baseline cases required | Preserve or improve agreed risk coverage | Validator retains responsibility for risk conclusions |

When evidence permits, the Process Owner can propose a concrete target. It remains a *proposal* pending Stage 4 evaluation/acceptance design. The first-wave Discovery Pack may record a measurement plan rather than a numeric result.

### Illustrative possible findings (must not be treated as confirmed)

**Trade Surveillance Validation:** A material problem *may* be missing required model design elements delaying the start of substantive validation. The opportunity may be an early completeness/consistency check.

**AI Independent Validation:** A material problem *may* be rapidly changing documentation and the need to decide which evidence gaps affect risk assessment or validation strategy. The opportunity may be risk-based evidence-gap support.

**Potential shared business requirements:** document ingestion, metadata identification, requirement mapping, cited evidence extraction, audit traceability. **Potential variant requirements:** methodology-specific adequacy criteria, risk decisions, timeliness requirements and review controls. Engineering reuse remains a Stage 4 question.

### Example Opportunity Register entries (hypotheses only)

| ID | Opportunity | Team variant | Value hypothesis | Reuse class | Stage 3 recommendation |
|---|---|---|---|---|---|
| OPP-01 | Earlier document-completeness checks | Trade Surveillance (to confirm) | Reduce rework and submission-query cycles | Potentially Common | Obtain evidence/measure baseline, then assess Stage 4 |
| OPP-02 | Risk-based evidence-gap analysis | AI IVT (to confirm) | Improve consistency and risk coverage despite changing documents | Local or Potentially Common | Discovery with Methodology Owner before Stage 4 |
| OPP-03 | Standardise submission guidance | Multiple teams (to confirm) | Prevent avoidable missing submissions | Unknown | Check methodology/process change before technical build |

### Example cross-team synthesis meeting (30 minutes)

Compare: (1) input and output meaning, (2) decision criteria and owners, (3) evidence and access, (4) exceptions and human controls, (5) value measures, (6) current tools. Do not call a requirement “Clearly Common” until differences have been investigated and documented.

## 12. Reuse classifications and Child Case rules

| Classification | Use when |
|---|---|
| Local | Observed and material to one team; not yet justified as common |
| Potentially Common | Similar needs or tasks exist elsewhere but criteria/controls/inputs may differ |
| Clearly Common | Equivalent business requirement evidenced in multiple teams with material differences understood |
| Unknown | Insufficient cross-team evidence; do not guess |

Recommend a **Child FDE Case** when the candidate outcome needs materially distinct ownership, outcome measures, delivery plan, significant risk profile or scope decision. **Do not** create a Child Case simply because two teams use different terminology or screens.

A follow-on **Discovery Wave** is appropriate when examining another team is necessary to validate reuse/variant hypotheses and is consistent with leadership-approved scope/capacity. FDE recommends; leadership retains priority decisions.

## 13. Common pitfalls and remedies

| Pitfall | Remedy |
|---|---|
| Process Owner requests “an AI agent” | Ask for a recent case, business problem and desired outcome first |
| Senior manager describes an idealised workflow | Interview real users and compare with observed artefacts |
| Discovery starts mapping every possible exception | Focus on material exceptions; mark less important ones for later |
| No baseline exists | Define metric and evidence source, owner, sampling method, timing and downstream milestone; mark targets TBD if unsupported |
| "30% efficiency gain" inserted without measurement | Treat as unconfirmed ambition; request baseline/owner agreement, not as a committed target |
| Tool feature entered as the problem | Separate business problem, observed symptom, root-cause hypothesis and proposed solution |
| FDE spends time drawing elaborate BPMN for simple workflows | Use process table/flowchart by default; swimlane or state model only when it clarifies a material decision |
| Task decomposition misses side effects | Record whether action only drafts/recommends or changes records, approvals or obligations |
| FDE assumes shared need means a single solution | Classify business commonality only; defer engineering design to Stage 4 |
| Agent creates polished but unsupported findings | Keep evidence IDs, source dates, confidence and human validation |
| A PoC used exported sample data | Flag live access and control requirements for Stage 4/5, do not assume production feasibility |
| Six Cards become six bureaucratic documents | Store as structured sections in one record, with a concise pack |
| FDE creates new initiatives outside SLT priority | Recommend further waves/Child Cases and obtain relevant leadership prioritisation |
| Existing research is ignored | Link existing evidence and perform only a lightweight alignment check |

## 14. Definition of Done

Stage 3 is complete for the **defined process variant / Discovery Wave** when the Process Owner and FDE Lead share a sufficiently evidence-supported understanding of the actual process, its consequential tasks and controls, the material evidence-backed business problems, their baseline or owned measurement plan, proposed measurable outcomes and required quality/risk guardrails, initial boundaries and constraints; each material opportunity has an owner and next recommendation; and the gate decision is recorded.

**Stage 3 principle:** *Discover the process before designing the solution; demonstrate the problem before investing in the technology.*

## 15. Copy-and-use session worksheets

### 15.1 Live Discovery Session Notes (one page)

**Parent FDE Case:** [ID / Stage 2 priority]  
**Discovery Wave / team / variant:** [ ]  
**Date and participants:** [ ]  
**Process Owner:** [ ]  **FDE Lead:** [ ]  **Methodology Owner (if relevant):** [ ]

**Business question (not requested feature):** [ ]

**Process boundary:**  
Starts when [ ]  
Genuinely completes when [ ]  
Explicitly out of scope [ ]

**Walkthrough case:** [Case ID or approved evidence link—not sensitive content]  
**Key steps/handoffs/decisions:** [P01…]  
**Controls or human approvals:** [ ]  
**Exceptions/rework:** [ ]

**Top three pain points:**

| Pain ID | Step | Observed problem | Evidence / confidence | Root cause hypothesis |
|---|---|---|---|---|
| PP-01 | P__ | [ ] | [ ] | [ ] |
| PP-02 | P__ | [ ] | [ ] | [ ] |
| PP-03 | P__ | [ ] | [ ] | [ ] |

**Current baseline / evidence confidence or measurement plan:** [measured/estimated/not available, source, owner, sample, method, due]  
**Desired business outcome and candidate KPI IDs:** [1–3 primary outcome metrics]  
**Proposed target / status:** [agreed/proposed/TBD with reason]  
**Required quality / risk guardrail:** [ ]  
**Problem, observed symptom, root-cause hypothesis and solution hypothesis kept separate?** [ ]  
**Existing tools/initiatives:** [ ]  
**Data, system and access restrictions:** [ ]  
**Open facts vs assumptions:** [ ]  
**Next people/cases to consult:** [ ]

| Action | Owner | Due / next session | Evidence or decision required |
|---|---|---|---|
| [ ] | [ ] | [ ] | [ ] |

### 15.2 Short post-call readback

> **Process discussed:** [team / variant]  
> **What we currently understand:** [2–4 sentences describing trigger, key decisions, handoffs and genuine completion]  
> **Main pain points:** [up to 3, each linked to case/evidence where possible]  
> **Proposed outcome / metric:** [business improvement and proposed KPI definition, not technology]  
> **Baseline / measurement plan and guardrail:** [status, evidence/owner/due; what must not worsen]  
> **Information still needed:** [missing case/owner/methodology/baseline]  
> **Action owners:** [names/roles and actions]  
> **Request for Process Owner:** Please confirm or correct the current-state description and identify any important omitted exceptions or controls.

### 15.3 Gate 3 decision record

**Case / team / variant:** [ ]  
**Process Owner confirmation:** [Name, date, accepted / accepted with corrections / disagreement]  
**FDE assessment:** [Evidence sufficient? Key outstanding constraints?]  
**Measurement readiness:** [KPI(s), measured/estimated/planned baseline, owner/source, proposed target or TBD, guardrail, Stage 4 condition]  
**Overall Wave Gate:** [Complete / Targeted Discovery / Revise / Refer or Stop]  

| Opportunity ID | Progression | Case routing | Linked KPI / baseline status | Decision rationale / conditions | Next owner/action |
|---|---|---|---|---|---|
| OPP-01 | [Stage 4 / Discovery / Existing / Defer / Stop] | [Parent / Child / TBD] | [KPI-__ / measured, estimated or plan] | [ ] | [ ] |

**Further Discovery Wave proposed?** [No / Yes: which process/team, why, subject to which priority decision]  
**Material changes requiring SLT review:** [ ]  
**Decision authority/date:** [ ]

## 16. Recommended practical starting approach

For the **first Model Documentation Review wave**, start with a single Process Owner and one or two operational validators. Reuse all existing documentation and PoC findings. Conduct one 60-minute real-case discovery call, review the emerging process map and pain points, then convene a targeted SME session **only for actual gaps**. Complete the Cards at a level proportionate to the case, validate the findings with the Process Owner, and record Opportunity Register entries and Gate 3 disposition. Define the first candidate outcomes and quality/risk guardrails, even if they initially require a baseline sampling plan. Use lessons from this first wave to improve the questions and templates before expanding to another MRO team.

Avoid announcing a universal agent architecture or a common-tooling build solely because the leadership priority is shared. Stage 3 should make the distinctive business needs visible first; Stage 4 determines the right combination of process change, conventional automation and AI, and the best reusable engineering assets.


## 17. Quick reference — Stage 3-to-Stage 4 handover contract (v1.1)

Before recommending any material opportunity for Stage 4, be able to answer **in one page**:

| Business question | Evidence / linked record | If not yet known |
|---|---|---|
| What work happens, who decides and what genuinely completes it? | C3-02 process/case map and C3-04 tasks | Named Process Owner/SME confirmation action |
| What is the real problem, distinct from symptoms and proposed features? | C3-03 Problem Statement + EV links | Specific validation action and hypothesis status |
| How large is the issue currently? | Baseline value, definition, period, source/confidence | Owned baseline measurement plan and milestone |
| What improvement and controls would count as success? | 1–3 candidate KPIs, proposed target, guardrail, acceptance owner | Proposed direction plus specific agreement/evaluation action |
| What would Stage 4 need to explore? | Opportunity Register, constraints and alternatives | Assumptions and owners, not a predetermined platform |
| Who agrees to move this opportunity forward? | Process Owner validation + Gate 3 authority record | Leadership review where prior priorities/scope would change |

**Transfer to Stage 4:** Provide the current-state reference, verified business problem, task/control boundaries, measurement definition and source, target/guardrail proposals, critical risks, existing initiatives and option hypotheses. **Do not claim a KPI improvement has already been achieved at Stage 3.**
