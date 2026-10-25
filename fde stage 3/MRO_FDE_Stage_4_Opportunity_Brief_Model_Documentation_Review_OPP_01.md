# MRO FDE — Stage 4 Opportunity Brief
## OPP-01: Evidence Identification & Traceability in Model Documentation Review

> **ILLUSTRATIVE PROVISIONAL HANDOVER — NOT GATE-APPROVED.** Derived solely from the hypothetical Stage 3 Canvas; no actual Process Owner interview, evidence review, baseline measurement or Stage 3 approval has occurred. The brief demonstrates the desired handover format, **not** a build instruction.

| Metadata | Value |
|---|---|
| Parent priority | Model Documentation Review (`FDE-DOC-REVIEW`, example ID) |
| Discovery variant | AI Independent Validation (illustrative) |
| Opportunity ID | **OPP-01**; linked pain point **PP-01** |
| Process Owner / FDE Lead | Both to confirm / assign |
| Status | **Draft / Stage 3 validation pending** |
| Recommended routing | **Conditional candidate for Stage 4 assessment only**; requires Gate 3 decision |

## 1. Problem and evidence

**Provisional business problem:** Validators may spend avoidable effort finding, reconciling and citing relevant model evidence across evolving model documentation. The **extent and underlying cause are unverified**.

**Current workflow (hypothesis):** Receive model artefacts → identify applicable methodology requirements → find current evidence → assess adequacy/gaps → request clarifications → reassess versions and record findings.

**Evidence needed before confirming the problem:**

- One approved/redacted representative review (including document versions, references, gap record and review outcome).
- A walkthrough by a validator distinguishing time spent locating evidence from time spent exercising necessary professional judgement.
- Sample review/clarification history and authoritative methodology references.
- Process Owner confirmation that PP-01 is material and not already adequately solved.

**Stage 3 reference:** `MRO_FDE_Stage_3_Live_Discovery_Canvas_Model_Documentation_Review.md`, §§2–5; E-01–E-03.

## 2. Desired business outcome and measures

**Outcome:** Make relevant, current documentary evidence easier to locate and trace while preserving independent validator assessment.

| Measure | Proposed definition / status |
|---|---|
| Primary benefit metric | Active evidence-location minutes per comparable review; **baseline not established** |
| Baseline plan | Identify comparable approved cases, reconstruct/observe search versus substantive assessment time; Process Owner to agree practicality |
| Directional target | Reduce unnecessary search time; numerical threshold **to be agreed**, not assumed |
| Quality guardrail | Maintain or improve identification of material evidence gaps and accurate source/version references |
| Risk guardrail | No unsupported adequacy/materiality decisions; validator remains accountable |
| Acceptance owner | Process Owner, with methodology input on quality and controls |

## 3. Initial business scope

**In scope for assessment:** Assistance with locating, organising and citing model documentation evidence related to selected review requirements; bounded document sets and selected validation users to be agreed.

**Out of scope for initial option assessment:** Automatic final approval of documentation, autonomous model risk classification, editing authoritative model documents, replacing independent validator judgement and wider validation workflow redesign.

**Users:** Independent validators and potentially reviewers; confirm roles and workflow entry point.

## 4. Requirements and constraints for Stage 4

1. **Evidence fidelity:** Trace retrieved evidence to authoritative source, document version and relevant passage.
2. **Methodology alignment:** Use only approved requirement sets; changes governed by the Methodology Owner where applicable.
3. **Human control:** Results assist review; the validator makes formal adequacy and risk decisions.
4. **Data permissions:** Determine approved document sources, allowed processing environments, confidentiality/retention controls and whether AI access is permitted.
5. **Existing capability check:** Evaluate current templates, search functions, Copilot prompts and other existing tools before bespoke development.
6. **Failure transparency:** Missing, inaccessible or conflicting evidence must be indicated rather than fabricated or concealed.
7. **Business adoption:** Identify who maintains knowledge sources and accepts continued business fitness for purpose.

## 5. Stage 4 assessment requested

Assess a small number of **technology-neutral options**: improved document structure and submission process, conventional search/indexing, deterministic requirements matching, approved Copilot assistance and, only if justified, more tailored retrieval/AI support.

For each option evaluate feasibility, available data, expected value, engineering effort, control needs, maintainability and reuse. Decide whether a minimal PoC is necessary, and design it around representative approved cases and agreed measures.

**Do not preselect RAG, agent frameworks, Copilot Studio, Power Apps or a hosted runtime.** Solution route, technical architecture, detailed MVP, ADR and formal test plan belong in Stage 4.

## 6. Open questions and actions

| Question/action | Suggested owner | Needed for |
|---|---|---|
| Validate PP-01 and process boundary using a real case | Process Owner + validator + FDE | Gate 3 / confidence |
| Confirm authoritative documents, versions and allowed access | Data/document owner + security SME | Feasibility |
| Agree baseline plan and quality rubric | Process + Methodology Owners | Stage 4 evaluation design |
| Inventory current prompts/templates/tools/PoCs | FDE + business users | Avoid duplication |
| Compare with other MRO variants before claiming shared capability | FDE + other Process Owners | Reuse decision |

## 7. Gate / decision record

**Stage 3:** Not held. **No authorisation to proceed is recorded.**  
**Proposed decision once evidence is available:** Proceed to Stage 4 option assessment; alternatively continue targeted discovery, route to an existing solution, defer or stop.  
**Parent/child case:** Remain in parent initially; create a child only if distinct accountability or delivery warrants it.  
**Approvals required:** Business findings confirmed by Process Owner, methodology/control questions consulted as required, and formal progression by the relevant delegated decision authority.

**Version:** Illustrative draft, 24 October 2026.
