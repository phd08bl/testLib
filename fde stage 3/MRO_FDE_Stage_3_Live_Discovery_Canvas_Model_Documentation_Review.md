# MRO FDE — Stage 3 Live Discovery Canvas
## Worked example: Model Documentation Review (AI Independent Validation variant)

> **ILLUSTRATIVE / NOT VALIDATED.** This is a realistic example of how to populate the Canvas after an initial Process Owner meeting. All findings, work items, baselines and ownership below are **hypotheses or proposed evidence**, not actual MRO observations. Do not treat this example as a completed discovery or a passed Gate 3. No actual restricted evidence has been accessed.

**Parent priority / case ID:** Model Documentation Review / `FDE-DOC-REVIEW` (example ID)  
**Team / process variant:** AI Independent Validation — illustrative first Discovery Wave  
**Call / last updated:** Example prepared 24 October 2026; actual interview **not held**  
**Process Owner:** To confirm with AI IVT lead  
**FDE Lead:** To assign  
**Operational users / Methodology Owner:** Validator who conducts the review; applicable Model Validation Methodology Owner — to confirm  
**Status:** **Illustrative draft — preparation; not validated**

## 1 — Process and ownership

**Purpose of the process:** Establish whether the available model documentation and supporting evidence are sufficiently clear and reliable to support independent validation and risk-based challenge; identify and follow up on material gaps.

**Starts when (hypothesis):** Model documentation or a material updated version is received for validation or assessment.  
**Genuinely finishes when (to verify):** The validator records the documentation/evidence assessment, outstanding gaps, their implications and the next validation action. In agile work this may recur throughout the engagement, rather than ending at a single sign-off.

**Initial in scope:** Reviewing submitted model design/methodology descriptions, tracing supporting evidence, recording gaps, asking questions, and evaluating updates.  
**Out of scope for this Discovery Wave:** Full validation of model performance, redevelopment of formal methodology, final technology selection, production controls design.

**Decisions, methodology, owners:** Validator exercises independent judgement about adequacy and risk significance; Process Owner owns the workflow and acceptance of improvements; Methodology Owner is consulted where formal validation requirements or interpretation change. Confirm actual decision and escalation rights.

**Interview validation questions:** What exactly triggers review? Is completeness checked separately from adequacy? Who determines readiness to proceed despite gaps? Does review recur after model changes?

## 2 — Actual work and decisions

**Representative work item:** Not yet provided. Request one **approved/redacted** recent AI model documentation review, including a document/version, relevant review comments, gap requests, and resulting validator decision. Store evidence in authorised repositories; link rather than copy it into this file.

**Proposed as-is sequence — to validate through case walkthrough:** Receive artefacts → determine applicable requirements → find evidence across documents/versions → assess completeness and adequacy → record material gaps → request additional evidence → reassess updates and record next action. Review may cycle when documentation or implementation changes.

| Key task / decision | Input → output | Actor and tool | Judgement / control | Evidence / exception |
|---|---|---|---|---|
| Identify relevant requirements | Model type + methodology → review criteria | Validator; methodology/checklist | Which requirements apply? | Link applicable standard; confirm variations |
| Locate and trace evidence | Documentation, technical artefacts → evidence references | Validator; approved document stores | Does evidence support the claim, and is it current? | Version conflicts or dispersed sources (hypothesis) |
| Assess gaps | Criteria + evidence → findings/gap record | Validator; review notes | Incomplete vs materially inadequate; risk significance | Link an approved reviewed example |
| Request clarification | Gap record → targeted request | Validator → model owner; email/workflow | What is essential now? Who can accept remaining uncertainty? | Response loops and waiting (to quantify) |
| Reassess / decide next action | Updated evidence → current assessment | Validator / reviewer as applicable | Continue testing, escalate or request further evidence | Repeat changes during agile work (hypothesis) |

**Important failure/escalation boundaries:** Missing authoritative version, misleading/inaccurate AI-supported gap identification, use of restricted model information, and any automatic change to formal risk conclusions. **Human validation decision must remain with authorised personnel.**

## 3 — Problems and evidence

| Problem | Observed symptom / affected user | Evidence and confidence | Impact | Likely cause (confirmed / assumed) |
|---|---|---|---|---|
| **PP-01** Effort locating and reconciling evidence | Repeated searching/version checking by validator | **Unverified.** Obtain real case walkthrough and time breakdown | Potential manual effort, slower review | Fragmented/versioned documentation — **hypothesis** |
| **PP-02** Repeated clarification/rework | Follow-up requests and re-review | **Unverified.** Examine approved clarification history | Potential waiting and duplicated work | Missing/unclear information or poorly targeted requests — **hypothesis** |
| **PP-03** Difficulty assessing significance of gaps in evolving documentation | Expert reassessment after updates | **Unverified.** Ask Methodology Owner and validators for examples | Potential inconsistency or delayed risk-based decisions | Inherent complexity and evolving artefacts, not necessarily a removable inefficiency — **hypothesis** |

**Problem versus solution:** “Build a RAG/agent” is **not** a validated problem. Possible solutions must remain open until Stage 4.  
**Root-cause test:** For each claimed delay distinguish searching, professional analysis, waiting for owners, and rework; legitimate analytical challenge should not be labelled waste.

## 4 — Desired outcomes and measures

| Desired outcome | Primary business metric | Baseline / source or measurement plan | Proposed target / direction | Quality / risk guardrail | Owner |
|---|---|---|---|---|---|
| **O1 / PP-01:** Reduce unnecessary evidence-location effort | Active evidence-location minutes per comparable review | **Not available.** Sample approved cases; validator reconstructs time across searching vs substantive assessment | Reduce against validated baseline; **no numeric target agreed** | Material evidence-gap identification and traceability must not deteriorate | Process Owner to agree; FDE to support measurement |
| **O2 / PP-02:** Reduce avoidable clarification loops | Repeat clarification requests per review (classified avoidable vs justified) | **Not available.** Review approved comment histories | Fewer avoidable loops; do not suppress legitimate challenge | Required clarifications and escalation preserved | Process Owner |
| **O3 / PP-03:** Support consistent risk-based gap handling | Methodology-led qualitative review of gap-assessment quality | **No validated rubric yet.** Methodology Owner to define examples | Improved consistency while retaining expert judgement | Independent validator remains accountable; no unsupported risk conclusions | Process + Methodology Owners |

**Measurement dependency:** Before PoC effectiveness claims, agree comparable review categories, time/effort definitions, source of historical cases, permitted data handling, and who records baseline. Stage 4 can refine evaluation design. **No realised benefits claimed.**

## 5 — Dependencies and existing capabilities

**Authoritative data / artefacts:** Model documentation, applicable methodology and standards, technical design/evidence artefacts, review comments and version history. Owners, sensitivity, storage and permitted AI processing **to verify**. Use controlled redacted/synthetic examples if approved access is unavailable.

**Methodology and independence:** AI should not silently decide documentation adequacy, materiality or formal risk status. Record evidence provenance and version used. Methodology changes require the relevant authority.

**Existing tools / PoCs:** Check approved documentation templates, checklists, Copilot prompts, code/document-analysis utilities and any existing review assistant or PoC. **None asserted to exist for this process without owner confirmation.**

**Important unknowns:** Authoritative document source; access rights; whether versions can be traced; baseline; scope of user permissions; whether outputs can be stored; ability to measure material gap recall against expert reference cases.

**Common vs variant:** **Unknown / potentially common (hypothesis).** Documentation completeness could be shared with other validation teams, but adequacy, professional judgement and evidence practices may vary. Compare another team before assigning “Clearly Common.”

## 6 — Opportunities and next steps

| Opportunity / linked problem | Indicative value and why | Existing route / constraint | Recommended progression | Parent / Child / TBD | Next action and owner |
|---|---|---|---|---|---|
| **OPP-01 / PP-01** Evidence identification and traceability assistance | **Potential medium** efficiency benefit; magnitude **unverified** | Check templates/search/prompt capability and approved data access | **Conditional candidate for Stage 4**, after Process Owner validation and feasible measurement plan | Remain in parent initially | FDE: validate one work item; owner: confirm acceptable evidence and KPI |
| **OPP-02 / PP-02** Improve submission requirements and gap-request clarity | **Unknown–potential medium** rework reduction | Could be methodology/process improvement rather than software | **Check existing process initiative / targeted discovery** | Parent | Process/Methodology Owner: review current instructions and request patterns |
| **OPP-03 / PP-03** Risk-based evidence-gap assessment support | Potential risk/quality value, **unquantified** | High dependence on methodology, representative reference cases and human judgement | **Targeted methodology discovery first**; Stage 4 only if sufficiently defined | Child case **TBD** if distinct ownership/scope | Methodology Owner + validators: test feasibility of assessment rubric |

**Process Owner corrections / confirmation / date:** **Pending — no meeting or acceptance recorded.**  
**Open questions:** Which pain points are real and material? Can approved cases be inspected? Which review metrics are feasible? Are related tools already in use? How do teams differ?

## Gate 3 — six checks

- [ ] Process and owners understood **and validated**
- [ ] Material problems evidenced or uncertainties explicitly assigned and appropriately bounded
- [ ] Credible business outcomes and indicative impact
- [ ] KPI, baseline or owned measurement plan, and guardrail
- [ ] Critical controls, data, independence and existing initiatives considered
- [ ] Process Owner validation; opportunities have next actions

**Overall Gate:** **NOT HELD — not approved for unconditional Stage 4 delivery.**  
**Decision authority / date:** Pending actual review.  
**Stage 4 Brief(s) required for:** Draft **OPP-01**, expressly provisional until Gate 3 decision.  
**SLT Update needed:** Yes — factual status as an illustrative or future-work update; no validated benefits or recommendations implied.

### Evidence / action mini-log

| ID | Evidence or action | Owner | Status |
|---|---|---|---|
| E-01 | Approved representative documentation review and findings | Process Owner / validator | Requested, not supplied |
| E-02 | Review methodology and applicable checklist | Methodology Owner | To identify |
| E-03 | Historical effort and clarification records | Process Owner | Availability unknown |
| A-01 | Confirm current-state process and actual boundary | FDE + Process Owner | Open |
| A-02 | Check existing initiatives and security constraints | FDE + technical/data SMEs | Open |
| A-03 | Agree candidate metrics and guardrails | Process + Methodology Owners | Open |

**Evidence rule:** References to hypothetical examples in this document are not evidence. Do not copy restricted documents, model code or sensitive datasets into an unapproved repository, chat or LLM service.
