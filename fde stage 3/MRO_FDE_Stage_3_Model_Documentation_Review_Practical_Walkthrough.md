# MRO FDE — Stage 3 Practical Walkthrough
## Model Documentation Review — Process Owner Engagement and End-to-End Outputs

**Companion to:** MRO FDE — Stage 3 Discovery & Operating Guide v1.2 and Stage 3 Live Discovery Canvas  
**Status:** Worked operational example. All filled findings are **hypothetical** until validated in an actual team engagement.  
**Audience:** FDE Lead, Process Owner, operational validators, Methodology Owner (where needed), MRO FDE steering/SLT.  
**Principle:** Discover the actual process, evidence and business problem before designing any agent or technical solution.

---

## 0. Objective, scope and successful outcome

**Stage 2 parent priority:** Improve Model Documentation Review across relevant MRO teams.  
**Stage 3 Discovery Wave 1:** Select **one specific team and process variant**, such as AI Independent Validation, to demonstrate the workflow. A second wave (e.g. Trade Surveillance Validation) may follow subject to priorities and availability.  
**Discovery objective:** Determine how that team reviews documentation, why and where effort/risks occur, which requirements and professional judgements matter, what improvement would be valuable, and what can proceed to Stage 4.

**Stage 3 is not:** a commitment to build an AI agent; a substitute for model-risk methodology approval; a technical design review; or permission to upload sensitive validation records to an LLM or repository.

**Sufficient exit:** A Process Owner-validated Canvas, evidence-linked material problem statements, a metric/baseline or owned measurement plan, an opportunity disposition, and a recorded Gate 3 decision.

---

## 1. Preparation — before Call 1

### 1.1 FDE preparation checklist

- [ ] Retrieve Stage 1 Candidate Brief and Stage 2 priority/decision: what exactly was prioritised, which initial team, any time/resource boundary.
- [ ] Identify **Process Owner**, one **actual validator**, FDE Lead, and Methodology Owner if methodology questions might arise.
- [ ] Read available review SOP, model documentation requirements/checklists, example issue logs, previous PoCs or tooling, **without recreating existing evidence**.
- [ ] Define the question to resolve: *Is this intake completeness, substantive adequacy, ongoing evidence-gap/risk assessment, or several distinct subprocesses?*
- [ ] Pre-populate Canvas metadata and §1 with known facts, marking each unverified item **To confirm**.
- [ ] Request a recent **approved representative work item** and, where useful, one material exception/rework example; ask for a live walkthrough rather than an unapproved copy.
- [ ] Send meeting agenda and 3–4 preparation prompts in advance. Do not send the full technical question bank as a mandatory form.

### 1.2 Example invitation / agenda

**Subject:** MRO FDE Discovery — Model Documentation Review — [Team]

**Purpose:** Following the MRO leadership priority on model documentation review, understand how the process works in [Team], which issues most affect efficiency or validation quality, and what outcomes would justify improvement. This is a process-discovery session rather than solution selection.

**Proposed 60-minute agenda:**
1. Process objective, ownership and scope (10 minutes)
2. Walkthrough of one recent documentation review (25 minutes)
3. Pain points, evidence, impact and desired outcomes (15 minutes)
4. Existing tools, constraints, actions and next steps (10 minutes)

**Helpful preparation:** A validator familiar with the activity; a recent permitted example and any existing checklist/procedure; an example of missing or changed documentation if available. Sensitive source material should stay in approved systems.

### 1.3 Attendees and roles

| Role | Needed for | Normal involvement |
|---|---|---|
| FDE Lead | Questions, synthesis, opportunity framing and downstream outputs | Every step |
| Process Owner | Purpose, boundaries, business value, acceptance and findings validation | Call 1 and playback |
| Actual validator/user | Real-case demonstration and professional judgement | Call 1; follow-up if needed |
| Methodology Owner | Standard interpretation, adequacy criteria, methodological change boundaries | Conditional |
| Data/platform/security SME | Material information access, integration, sensitive records or other blockers | Conditional |
| SLT/delegated priority owner | New waves, material priority changes or resource decisions | Escalation only |

---

## 2. Call 1 — facilitator's question guide (60 minutes)

**Facilitation rule:** Ask the bold primary questions first; select follow-ups based on the response. Do not try to fill every blank on the Canvas during the call.

### 2A. Frame the process (0–10 minutes) — Canvas §1

1. **What is the purpose of documentation review in your team?** Is the intended outcome identifying missing documents, assessing methodological adequacy, deciding validation readiness, supporting continuing validation, or something else?
   - What risk or downstream activity does the review support?
2. **What event starts the review, and when is it genuinely completed?**
   - Is the process a one-off gate, an iterative activity throughout validation, or both?
   - What happens after the review outcome is communicated?
3. **Who performs, owns and approves the activity?**
   - Who sets formal documentation and validation standards?
   - Who decides if incomplete documentation is acceptable or whether work continues with residual evidence gaps?
4. **What part of this process is most relevant to the leadership priority?**
   - Which team/variant are we investigating first? What is excluded?

**Record:** Process objective, start/end, scope, Process Owner, users, methodology/control authority. Mark unresolved role definitions for follow-up.

### 2B. Walk through an actual review (10–35 minutes) — Canvas §2

5. **Could a validator walk us through one recent review, from receipt to the final review action?**
   - What was received (documentation versions, code or design artefacts, evidence packages)?
   - How were the applicable documentation requirements identified?
   - Where did the validator look for evidence and what tools were used?
   - How did they decide between *present*, *sufficient*, *inconsistent* and *missing* evidence?
   - What questions or requests went back to the model owner? How were answers handled?
   - Who assessed and approved the implications of unresolved gaps?
   - What evidence was recorded for audit and for the validation report?
6. **Where are the human judgement and control points?**
   - Which judgement follows a rule/checklist and which depends on model-specific expertise?
   - What requires independent challenge, escalation or approval?
7. **What happens in exceptions?**
   - Agile or revised models; multiple documentation versions; missing design information; contradictory records; time-sensitive validation decisions.
8. **Could we look at one example of material rework or an unresolved evidence gap?**
   - Distinguish time spent working from time awaiting a response.

**Record:** Around five to eight **meaningful** steps, not clicks; inputs/outputs, tool, judgement, control, exception and supporting evidence link. Use a short task table unless a diagram would clarify complexity.

### 2C. Diagnose problems and value (35–50 minutes) — Canvas §§3–4

9. **Which parts are most difficult, inefficient or risky, and why?**
   - Is friction due to incomplete submissions, finding evidence, interpreting adequacy, duplicated checking, repeated model-owner correspondence, or unclear standards?
10. **Can you point to evidence rather than just an impression?**
   - An approved recent case, issue log, elapsed turnaround, number of requests, observed manual work or validator estimate.
11. **What is the likely root cause? Are we sure, or is it still a hypothesis?**
   - Ask counterexample: When does the process work well, and what differs?
12. **If this improved, what outcome would be valuable?**
   - Reduced *active review effort*, earlier identification of material gaps, reduced unnecessary clarification loops, more consistent evidence traceability, or improved risk assessment support.
13. **How could we measure that improvement without weakening independent validation?**
   - Pick one main metric and one or two guardrails. What baseline exists? If none, who can collect comparable cases and by when?

**Record:** Separate `business problem`, `observed symptom`, `likely cause (confirmed/hypothesis)` and `solution hypothesis`. Do not record “build a RAG agent” as a business problem.

### 2D. Constraints, existing work and close (50–60 minutes) — Canvas §§5–6

14. **Which information sources are authoritative and who owns them?** What restrictions apply to access, storage, retention and AI processing?
15. **What tools, prompts, Python scripts, templates or PoCs are already being used?** What do they solve and what remains unsolved?
16. **What must stay under a validator or Methodology Owner's authority?** What would be unacceptable if an automated aid were wrong?
17. **Which improvement seems worth exploring first?** Could a business-process change or existing tool solve it without new AI development?
18. **What information is missing for us to make a sensible next-step recommendation?** Who will provide it?

**Closing readback:** “Our current understanding is [one-sentence process], the main problems appear to be [up to three], the outcome worth improving is [one], and we will check [unknowns]. Is anything material incorrect?”

---

## 3. Example live Discovery Canvas — ILLUSTRATIVE ONLY

> This is an example of what the **single working Canvas** might look like after the call and initial FDE synthesis. **Nothing below is a claim about the team's actual workflow or measurements.** Replace with actual findings and cited approved evidence references.

### Header

| Field | Illustrative entry |
|---|---|
| Parent priority | Model Documentation Review — [Stage 2 reference] |
| Team / variant | AI Independent Validation — evolving-model evidence review *(example; verify)* |
| Process Owner | [Name / role to confirm] |
| FDE Lead | [Assigned FDE] |
| Actual user / methodology authority | [Validator]; [Methodology Owner if needed] |
| Status | In Discovery / Awaiting Process Owner validation |

### Canvas §1 — Process & ownership

**Purpose (hypothesis):** Identify whether available documentation and supporting artefacts provide sufficient evidence for independent review, and document gaps and their risk implications.  
**Starts:** Documentation/evidence submitted or materially updated for validation.  
**Genuinely finishes:** Not necessarily “all documents complete”; may be when the validator has recorded the evidence-gap assessment and agreed the next validation action. **Ask Process Owner to confirm.**  
**In scope:** How available model documentation/evidence is assessed and clarification requests tracked.  
**Out of scope at this discovery stage:** Final solution design; authority to waive methodological requirements or approve changes in official risk records.

### Canvas §2 — Actual work & decisions

| Step | Input → output | Actor / tool | Judgement / control | Evidence / potential exception |
|---|---|---|---|---|
| 1. Receive submission | Documentation package → reviewable set | Validator / approved file system | Identify applicable version and provenance | EV-01 / differing versions |
| 2. Determine requirements | Model type + standards → applicable requirements | Validator / method checklist | Interpret applicable standards | EV-02 / model-specific requirements |
| 3. Locate and assess evidence | Documents + artefacts → completeness/adequacy notes | Validator / documents/tools | Present ≠ sufficient; professional judgement | EV-03 / dispersed material |
| 4. Raise material gaps | Findings → targeted evidence requests | Validator → model owner | Materiality, priority, approval boundaries | EV-04 / multiple clarification loops |
| 5. Review updates | Response/new version → updated gap assessment | Validator / tracked record | Reassess based on changed information | EV-05 / rework/version confusion |
| 6. Record next action | Assessment → continue, request or escalate | Validator / approved workflow | Independent judgement, escalation controls | EV-06 / unresolved material gap |

**As-is flow (candidate to validate):** Submission → requirements → evidence review → gap assessment → request/update loop → documented review decision. A flowchart is sufficient initially; use swimlanes for consequential handoffs or a state model for repeated version/status transitions.

### Canvas §3 — Problems & evidence

| ID | Business problem | Symptom | Evidence and confidence | Root cause |
|---|---|---|---|---|
| PP-01 | Locating evidence may consume substantial reviewer time | Repeated searches across artefacts and versions | **Unverified** until case walkthrough/time observations; EV-03 proposed | Fragmented sources/versioning *(hypothesis)* |
| PP-02 | Missing or inconsistent evidence may trigger repeated clarifications | Multiple model-owner requests and reassessments | **Unverified** pending approved request log/case; EV-04/05 proposed | Non-standard submission or evolving evidence *(hypothesis)* |
| PP-03 | Assessment of incomplete evidence may vary across cases | Different descriptions of gap significance | **Unverified** pending methodology review/sample; EV-02/06 proposed | Method criteria/decision support needs investigation |

**Do not promote these statements to “verified findings” based on the example alone.**

### Canvas §4 — Desired outcomes, KPIs and safeguards

| Desired business outcome | Metric | Baseline / source | Target / direction | Guardrail | Owner / plan |
|---|---|---|---|---|---|
| Reduce time spent locating relevant evidence | Validator **active minutes** per comparable review | Not established; sample approved cases or structured self-report | Downwards; target TBD with owner | Material evidence-gap detection not degraded | Process Owner + FDE agree metric/sampling before Stage 4 evaluation design |
| Reduce avoidable clarification/rework | Number of unnecessary clarification cycles per comparable review | Not established; inspect correspondence/issue logs if permitted | Downwards; TBD | No suppression of necessary risk-driven challenge | Process Owner validates what constitutes *avoidable* |

**Do not conflate:** elapsed calendar days, time spent working and time waiting for model-owner answers. Compare similar review scope/model complexity where feasible.

### Canvas §5 — Dependencies and existing capabilities

- **Authoritative sources:** model documents; model-risk standards; review notes; model-owner updates. Confirm actual approved systems, data owners and document provenance.
- **Restrictions:** model information may be confidential; confirm authorisation for reviewing, copying, processing and storage. Do not place raw evidence in an unapproved AI tool, repository or Canvas.
- **Human authority:** validator retains risk assessment and independent challenge; methodology changes require the relevant owner.
- **Existing tooling:** explicitly ask about documentation templates, checklists, Copilot prompts/Agent Builder, Python validation tooling, past PoCs and relevant platform capabilities. Record owner, maturity and actual limitations.
- **Common-vs-variant:** **Unknown** until another MRO team's workflow and requirements are examined. Do not assume one technical solution.

### Canvas §6 — Opportunities and next steps

| Opportunity | Problem link | Indicative value | Route (tentative) | Parent/Child | Next action |
|---|---|---|---|---|---|
| OPP-01: Improve discoverability and structured evidence-gap identification | PP-01, PP-02 | Potential reviewer effort and consistency benefit; **not quantified** | **Stage 4 candidate** if verified and valuable | Parent initially / child TBD | Validate real cases, metric and controls; FDE + Process Owner |
| OPP-02: Improve submission/checklist guidance | PP-02 | Could reduce missing information upstream | Existing business/methodology route to assess | Remain Parent | Confirm current standards and owner; Methodology Owner |
| OPP-03: Support risk-based assessment of incomplete evidence | PP-03 | Potential quality/risk benefit; high judgement sensitivity | Targeted discovery and method review | Child only if material scope/ownership difference | Methodology Owner + experienced validators |

**Process Owner confirmation:** Pending; date and corrections to be recorded.  
**Critical open questions:** which problems are materially evidenced; actual starting/finishing states; baseline comparability; required methodology approval; authorised evidence sources; existing PoC coverage.

---

## 4. Post-call FDE synthesis and conditional SME follow-up

### FDE tasks (normally immediately after Call 1)

1. **Translate notes into the Canvas:** §1 purpose/owner; §2 real-case workflow; §3 top problems; §4 metric and guardrail; §5 dependencies/existing tools; §6 opportunities.
2. **Check traceability:** Every important claimed problem needs an evidence reference or explicit `unverified/assumed` status. Keep evidence in approved systems.
3. **Analyse the real work:** `input → judgement/decision → action → output → side effect/control → responsible role` for material steps; do not atomise every click.
4. **Separate claims:** `business problem` vs `symptom` vs `cause hypothesis` vs `technical solution idea`.
5. **Distinguish output types:** completeness checking, substantive adequacy, version-change tracking and risk-based gap review may be different opportunities, not one vaguely defined agent.
6. **Propose KPI methodology:** Active work vs elapsed/waiting time; comparable cases; quality guardrail; owner for missing baseline.
7. **Map existing work:** Name, owner, whether in use or PoC, relevant task, true limitation; consider a no-build route.
8. **Identify only decisive unresolved questions:** SME follow-up if methodology, data permissions, baseline or control interpretation could change next-step recommendation.

### Optional targeted follow-up questions

**Methodology Owner:** Which review criteria are formal requirements? What is discretionary professional judgement? Is an evidence gap an issue, risk, limitation or approval blocker? Who authorises methodology changes?

**Actual validator:** Can you trace one evidence gap through document versions, clarifications and the final decision? Which steps require repeat reading? Why are some cases harder?

**Data/platform/security SME:** Where are controlled documents and revision histories stored? Which read-only access would a potential solution require? Are test environments or permitted datasets available? What processing and retention restrictions apply?

**Process Owner:** Which metric would make an improvement meaningful? Can we obtain a handful of comparable cases without exposing restricted information? Can you review the draft Canvas for factual accuracy?

### Post-call readback example (send for correction)

> **Subject:** FDE Discovery Readback — Model Documentation Review — [Team]
>
> Thank you for the discussion. Our provisional understanding is that [scope and genuine completion]. The main issues requiring validation are [up to three] and the improvement outcome is [outcome], subject to preserving [independence/quality/controls]. We have recorded [evidence references], with open points on [methodology, baseline, access and ownership]. Could you please correct any inaccuracies, particularly in the workflow, professional decision points and improvement measures? We propose [next targeted actions] before the discovery playback.

---

## 5. Playback and Gate 3 (30 minutes; asynchronous when appropriate)

### Suggested playback agenda

| Minutes | What to show | Decision to confirm |
|---|---|---|
| 0–10 | One-screen current-state workflow and key decisions | Is the process accurately represented? |
| 10–18 | Top 1–3 problems, evidence confidence, baseline status and guardrail | Which are material and validated? |
| 18–25 | Opportunity Register and existing alternatives | Which route is justified for each? |
| 25–30 | Six Gate checks, open questions, accountable owners and next action | Ready, conditional or more discovery? |

### Gate 3 six criteria

- [ ] **Process:** Purpose, boundary, owners, significant work and required judgement/control are understood.
- [ ] **Evidence:** Material problems linked to approved evidence or transparently qualified, with owners for unresolved proof.
- [ ] **Value:** Credible improvement outcome and indicative materiality/value stated.
- [ ] **Measurement:** Primary KPI, baseline or owned collection plan, and quality/risk guardrail exist.
- [ ] **Constraints:** Significant methodology, independence, data, existing-tool and operational dependencies considered.
- [ ] **Action:** Process Owner validates findings and every material opportunity has a recorded next action.

**Important:** Do not claim the example's hypothetical problems pass an evidence gate. Progress a specific opportunity only when sufficient evidence and a credible measurement plan exist, or document precise conditions if authorised by the appropriate decision maker.

### Example Gate record — conditional (illustrative)

**Wave:** AI IVT / Model Documentation Review — [ID]  
**Process Owner confirmation:** [Pending/record date]  
**Overall disposition:** *Further targeted discovery* until actual evidence and owner validation; could become *Ready with conditions* after these are resolved.  

| Opportunity | Progression | Routing | Condition or next action | Owner |
|---|---|---|---|---|
| OPP-01 | Stage 4 **proposed**, subject to validation | Parent initially | Confirm observed friction, baseline collection, access and human control | Process Owner + FDE |
| OPP-02 | Use existing/process/methodology route | Parent | Check templates and formal standard owner | Methodology Owner |
| OPP-03 | More targeted discovery | Child TBD | Validate materially distinct risk assessment need/authority | Methodology Owner + validator |

**SLT escalation:** Only for material reprioritisation, resources or a new wave outside agreed delegation. A normal completed discovery does not require SLT to select technology.

---

## 6. Downstream Output A — Stage 4 Opportunity Brief (worked draft)

> Only release this as a formal Stage 4 input once Gate 3 authorises progression. This example is a **provisional draft**, not a validated specification.

**Opportunity ID/title:** OPP-01 — Improve evidence retrieval and structured documentation-gap identification.  
**Parent/team:** Model Documentation Review / AI Independent Validation.  
**Process Owner:** [To confirm].  
**Problem/evidence:** Candidate issue: manual evidence location across changing document versions and repeated review loops; cite EV-03/04/05 only after approved verification.  
**Actual work:** Determine applicable requirements → locate evidence → assess sufficiency → record gaps → seek updates → reassess. Human methodology judgement and independent risk assessment stay with the validator.  
**Minimum valuable outcome:** Reduce effort identifying relevant documentation/evidence gaps for an agreed model/document type, without authorising AI to approve model documentation or change official risk status.  
**Initial in scope:** Read-only evidence lookup and drafting structured gap observations for validator review (candidate scope only; Stage 4 will refine).  
**Out of scope:** Automated approval, autonomous escalation and amendment of official risk decisions; enterprise rollout before evidence.  
**Primary business metric:** Active minutes spent locating and organising evidence per comparable review; baseline to be established from authorised cases or structured reviewer observations.  
**Guardrails:** No reduction in detection of material missing/inconsistent evidence; traceability to authoritative document/version; validator retains decisions.  
**Constraints:** Approved access/processing to sensitive model data; methodology ownership; version control; evidence provenance; existing tool overlap.  
**Existing capabilities to examine:** Current documentation checklists, existing scripts, Copilot prompts, Agent Builder and validation platform assets; non-AI template/process simplification.  
**Stage 4 design questions:** Is the problem mainly data structure, process, document comparison, retrieval or reasoning? How to evaluate relevance, traceability, quality and cost? Can a controlled, simpler non-agent solution suffice? Should functions be reused across process variants?  
**Gate status:** Provisional; release after evidence and owner validation.  
**Stage 4 owner and next action:** FDE + business owner to assess options, constraints and evaluation plan.

---

## 7. Downstream Output B — One-page SLT Discovery Update (worked draft)

> This is an **illustrative status update**, not a claim of findings or benefits.

**Leadership priority:** Model Documentation Review  
**Status:** Discovery in progress — Wave 1 [Team]; other team waves subject to prioritisation.  
**Coverage:** Process Owner engagement [planned/completed]; representative item [not yet verified / reviewed on date].  

**What we are investigating:** Whether documentation review friction arises mainly from finding/versioning evidence, completeness checks, specialist adequacy/risk judgements or follow-up loops. This distinction matters because the appropriate interventions can differ by MRO team.

**Findings to confirm (not validated):**
1. Potential manual effort locating and reconciling evidence across documents and versions.
2. Potential repeated requests for incomplete/inconsistent information.
3. Possible distinction between completeness requirements and professional risk-based adequacy judgement.

**Potential improvement opportunities:**
- Structured documentation/evidence-gap identification — candidate for Stage 4 if evidence confirms material value.
- Submission guidance/standards — check existing business/methodology route before new build.
- Specialist risk-based gap assistance — further targeted discovery before case splitting or technical commitment.

**Value and measurement:** Candidate measure is validator active time spent locating and organising evidence; baseline not established. Quality guardrails include material-gap coverage, traceability and independent professional judgement. No realised benefit claimed.

**Dependencies:** Process Owner validation, permitted sample case evidence, methodology/control clarification and existing-tool assessment.  
**Requested SLT decision:** None at this stage unless a new wave, priority or resource allocation is needed.  
**Next action:** Complete the Process Owner playback, confirm evidence and metrics, then submit Gate 3 dispositions for the appropriate opportunities.  
**Accountable lead:** [FDE Lead], with [Process Owner].

---

## 8. Extending from one MRO team to other teams

1. Complete one Canvas **per material process variant**, linked to the parent Model Documentation Review priority.
2. For the next team, ask the **same core questions** but adapt the real-case walkthrough to its actual methodology and timing.
3. Compare: `business purpose | start/end | required evidence | material decisions | controls | top problems | KPI | existing tools | opportunities`.
4. Classify the **business requirement** as `Local / Potentially Common / Clearly Common / Unknown`, with supporting evidence. This is **not** a decision that one software agent must serve all teams.
5. If a materially different outcome, owner, risk or delivery boundary exists, **recommend** a Child FDE Case; otherwise keep the opportunity under the parent.
6. Update the **one-page parent-priority SLT summary**, rather than generating a separate leadership deck for each team.
7. An adequately understood and authorised team-specific opportunity may proceed to Stage 4 without waiting for every other team's discovery.

### Compact cross-team synthesis template

| Question | Team/variant A | Team/variant B | Common/variant implication |
|---|---|---|---|
| What makes review complete? | [ ] | [ ] | [ ] |
| What evidence is authoritative? | [ ] | [ ] | [ ] |
| Where is human judgement critical? | [ ] | [ ] | [ ] |
| Where is effort or rework concentrated? | [ ] | [ ] | [ ] |
| How would value be measured? | [ ] | [ ] | [ ] |
| What existing tools work? | [ ] | [ ] | [ ] |
| What opportunity proceeds? | [ ] | [ ] | [ ] |

---

## 9. Final practical deliverables checklist

| When | Deliverable | Format | Audience |
|---|---|---|---|
| Before Call 1 | Prioritised scope, agenda, pre-populated Canvas §1 | Email + one working Canvas | Process Owner, validator, FDE |
| Immediately after Call 1 | Draft Canvas §§1–6, evidence/assumption/action links | Updated Canvas; short readback | FDE and Process Owner |
| Following targeted validation | Verified problem statements, process/task map where helpful, KPI/measurement plan, opportunities | Updated same Canvas (supporting links only) | FDE + relevant SME |
| At playback/Gate | Process Owner correction/confirmation, six checks, opportunity route, unresolved conditions | Gate section of Canvas / small Jira decision | Process Owner and FDE; appropriate decision owner |
| After authorised progression | One Stage 4 Brief **per progressing opportunity** | 1–2 pages/brief | Stage 4 solution design team |
| For steering | One parent-priority SLT Discovery Update | One page or a single steering slide | SLT |

**Definition of done:** Validated process and important decisions; evidence-backed or explicitly qualified problems; credible business outcomes and metrics; known constraints and reuse opportunities; opportunity dispositions with accountable next steps; documented Gate 3 decision.
