# MRO FDE — Stage 3 Practical Walkthrough
## Model Documentation Review | Process Owner Engagement, Discovery Canvas and Downstream Outputs

**Version:** 2.2 — Six Aligned Question / Canvas Sections + Stable Universal Questions  
**Companion:** *MRO FDE — Stage 3 Discovery & Operating Guide v1.2* and *Stage 3 Live Discovery Canvas*  
**Owner:** MRO FDE / AI Tech & Tooling  
**Audience:** FDE Leads, Process Owners, operational validators, Methodology Owners, and MRO SLT  
**Status:** Reusable operating example. **All populated process findings, opportunities and measures in this guide are illustrative, not actual findings.**

> **Operating principle:** Keep **U01–U08 unchanged** across MRO processes. Organise the questions into the **same six sections as the Live Discovery Canvas**, while facilitating them through four natural conversation phases. Select documentation-specific (`DOC`) and adaptive probes only when they fill a material information gap. Record evidence and uncertainty, validate findings with the Process Owner, then generate opportunity-specific Stage 4 Briefs and a consolidated SLT Update. **Discover the work before designing a solution.**

> **Call 1 etiquette:** This is a conversation, **not an interrogation or completion exercise**. Ask broad questions, listen, follow the representative case, skip questions already answered, and park specialist or technical unknowns for targeted follow-up. U01–U08 are **coverage anchors**, not eight mandatory verbatim prompts.

---

# Part A — Run the Discovery

## 1. The engagement at a glance

**Leadership priority (Stage 2):** Model Documentation Review.  
**Initial Discovery Wave:** One selected MRO team and its actual process variant, e.g. AI Independent Validation. Other teams follow where agreed.  
**What Stage 3 must establish:** How review operates; where significant effort, quality or risk issues arise; what evidence supports them; what would count as measurable improvement; and which opportunities justify further solution assessment. **It does not have to resolve implementation architecture, production operating procedures or detailed security approvals.**

| When | FDE action | Minimum output |
|---|---|---|
| **Before the call** | Review Stage 1/2, existing materials and tools; identify Process Owner and real user | Pre-populated Canvas header/§1; agenda; requested work-item evidence |
| **Call 1 (60 min)** | Use **U01–U08** in six Canvas-aligned sections; select `DOC` specialist and adaptive follow-up questions | Draft Canvas §§1–4, provisional §§5–6, actions and evidence references |
| **After the call** | Reconstruct meaningful tasks; verify claims; assess root causes, existing work, measures and constraints | Updated six-section Canvas, initial Opportunity Register, material unknowns |
| **Targeted follow-up (only if needed)** | Resolve consequential methodology, operational, technical or evidence gaps | Corrections, agreed baseline/measurement plan, revised opportunities |
| **Playback + Gate 3** | Process Owner validates findings; FDE recommends progression; authorised decision recorded | Validated Canvas, six gate checks, opportunity dispositions |
| **Outputs** | Generate brief(s) for authorised Stage 4 opportunities and one parent-priority SLT summary | **Stage 4 Opportunity Brief(s)** + **SLT Discovery Update** |

**Typical participation:** FDE Lead (facilitator), Process Owner (business accuracy/value), actual validator (walkthrough). Involve Methodology Owner for formal standards/judgement boundaries and technology/data/security SMEs only where needed. The decision authority for Stage 4 progression follows the delegated operating model; material reprioritisation remains with leadership.

**Effort rule:** One discovery call plus asynchronous Process Owner review may suffice for a narrow, well-evidenced problem. Do not schedule a second workshop by default. Stage 3 is not a request for a product design, AI agent selection or approval to process restricted evidence in an AI tool.

## 2. Prepare for the Process Owner call

### 2.1 FDE preparation checklist

- [ ] Read the **Stage 1 Candidate Brief** and **Stage 2 leadership priority/constraints**. Confirm the initial team and process variant.
- [ ] Identify Process Owner, one actual validator, and any relevant Methodology Owner.
- [ ] Locate existing MRO documentation standards, review checklists/SOPs, earlier process mapping, known prompts/tools/scripts/PoCs, and related initiatives. **Reuse, do not recreate.**
- [ ] Pre-populate Canvas metadata and likely scope; mark unconfirmed statements `To verify`.
- [ ] Request **one approved recent review** and, if readily available, one consequential exception or rework example. A controlled screen-share or redacted trace is preferable to copying sensitive records.
- [ ] Prepare the **eight universal coverage anchors** (U01–U08), select perhaps **three to five** likely `DOC` probes, and anticipate evidence gaps. Use all eight *areas of understanding* but ask only what is still unanswered. Do not send a 20+ question survey.
- [ ] Agree where interview notes and evidence links may be stored. Do not upload confidential model code, documentation or personal data into unapproved AI services or repositories.

### 2.2 Ready-to-send call agenda

**Subject:** MRO FDE Discovery — Model Documentation Review — [Team]

**Purpose:** Following the leadership priority on documentation review, understand how the process actually works in [Team], its most significant problems, and the business improvements worth exploring. This is business/process discovery, **not a decision on the technical solution**.

| Time | Agenda |
|---|---|
| 0–10 min | Purpose, scope, ownership and process variants |
| 10–35 min | Walkthrough of an actual review, decisions, controls and exceptions |
| 35–50 min | Problems, evidence, business value and success measures |
| 50–60 min | Constraints, existing tooling, potential opportunities and actions |

**Please bring, where available:** A validator who performs this work; an approved representative review and existing guidance/checklist; and an example of an evidence gap or revision. Restricted artefacts can be demonstrated in their authorised systems without being transferred to FDE.

## 3. Call 1 — Standard 60-minute facilitator script

**How to use this section:** The question subsections below mirror **Canvas §§1–6, one-to-one**. `U01–U08` are the **unchanged, universal primary questions** across MRO processes; `DOC01–DOC14` are optional documentation-review probes; adaptive questions respond to what the Process Owner says. The **four phases organise the conversation**, while the **six sections organise the findings**. Questions may be covered naturally and out of order. **Do not repeat a question if a previous answer already covered it.** Stop once an issue is sufficiently understood; record unresolved items for follow-up rather than pursuing every detail during Call 1.

### Call 1 question-to-Canvas map

| Meeting phase and time | Question section — identical to Canvas | Universal questions | Capture objective |
|---|---|---|---|
| **A. Frame (0–10 min)** | **§1 — Process and ownership** | **U01–U02** | Purpose, genuine completion, owner/authority, variant/boundary |
| **B. Actual work (10–35 min)** | **§2 — Actual work and decisions** | **U03–U04** | Representative work item, important tasks, evidence, judgement and controls |
| **C. Problems/value (35–43 min)** | **§3 — Problems and evidence** | **U05** | Material problems, impact, sources and root-cause hypotheses |
| **C. Problems/value (43–50 min)** | **§4 — Desired outcomes and measures** | **U06** | Business outcome, baseline/plan, primary KPI and guardrails |
| **D. Constraints/next steps (50–55 min)** | **§5 — Dependencies and existing capabilities** | **U07** | Sources, restrictions, quality, existing tools and material dependencies |
| **D. Constraints/next steps (55–58 min)** | **§6 — Opportunities and next steps** | **U08** | Opportunity hypotheses, evidence gaps, business acceptance and next owners |
| **Close (58–60 min)** | **Cross-section readback** | Not a new question | Correct material misunderstandings and confirm follow-up actions |

**Capture rule:** A response can populate multiple Canvas sections. For example, a U03 walkthrough may also reveal a §3 pain point and a §5 access restriction. Record each finding once in the right place; **the alignment is a primary mapping, not a rigid data-entry rule**. You may use the six-section mini-sheet in the Appendix rather than fill the full Canvas live.

**Four optional *universal* follow-up refinements (retained from v2.1):**

| Question | Use only when needed | Why it belongs in Stage 3 |
|---|---|---|
| **U03 — Work and handoffs** | “What happens before and after this activity, and where do handoffs, waiting or rework occur?” | Exposes upstream/downstream causes and actual workflow boundaries. |
| **U04 — Consequences and ownership** | “What happens if an important decision is wrong or the normal process cannot be completed? Who takes responsibility?” | Reveals business impact, escalation and human accountability, **not technical recovery design**. |
| **U07 — Usability of information** | “Is the information needed for this work sufficiently complete, reliable and accessible?” | Distinguishes information existence from business usability, **not a full data-quality audit**. |
| **U08 — Co-creation and adoption** | “Who would need to be involved in validating and adopting any improvement?” | Identifies actual users, decision owners and participation needed for later stages. |

**These are optional probes within U03/U04/U07/U08, not U09–U12 or four new mandatory questions.**

### Canvas §1 — Process and ownership (Phase A · 0–10 min)

#### U01 — Purpose and boundary

**Ask:** **“What is the purpose of this process, and what outcome is it intended to achieve?”**

**Documentation-review probes (choose as appropriate):**
- **DOC01 — Review outcome:** Is the objective submission completeness, substantive methodological adequacy, validation readiness, ongoing evidence-gap assessment, or a combination?
- **DOC02 — Start/finish:** What triggers the review, and what makes it genuinely complete? Is it one-off or iterative through validation?
- What happens downstream when review is finished, or when documentation remains incomplete?

#### U02 — Accountability and variants

**Ask:** **“Who performs, owns and makes the key decisions in this process?”**

**Probes:**
- **DOC03 — Authorities:** Who sets documentation standards? Who judges the adequacy of incomplete evidence? Who may approve continuation, escalation or exceptions?
- Who provides inputs, receives outputs, and resolves handoff failures?
- **DOC04 — Variants:** Does the workflow vary by model family (e.g. AI versus traditional), complexity, materiality, stage of validation, or frequency of model changes? Which differences matter?

**Canvas §1 — Capture check:** Purpose; trigger and genuine finish; scope and process variant; Process Owner; actual users; Methodology Owner/control authority where relevant; significant approval and downstream boundaries. **Do not assume the Process Owner sets methodology standards.** Mark unconfirmed responsibilities for follow-up.

**Facilitator transition:** “Could we now follow an actual review rather than the theoretical workflow?”

### Canvas §2 — Actual work and decisions (Phase B · 10–35 min)

#### U03 — Representative work item

**Ask:** **“Could you walk us through a recent representative piece of work, from start to finish?”**

For this process: **“Can a validator show us one recent documentation review, from receipt of the material to the recorded review outcome or next action?”**

**Documentation-review probes (select those that clarify material work):**
- **DOC05 — Inputs/versions:** Which model documents, design/code artefacts, versions and other evidence arrived? How was source authority/version determined?
- **DOC06 — Requirements:** How did the validator identify applicable documentation and methodology requirements?
- **DOC07 — Assessment:** How did they distinguish *information present*, *sufficient*, *inconsistent*, *missing* and *materially inadequate*?
- **DOC08 — Gap cycle:** How were questions raised, responses handled, updates reviewed and unresolved gaps recorded?
- What tool/system did they use at each meaningful stage? What did they produce for the next validator activity or report?
- **Optional universal U03 — Upstream/downstream:** What happens **before** the documentation reaches the validator, and **after** the review outcome is issued? Where are the real handoffs, queues, active effort and rework? Ask only if the walkthrough did not already clarify this.

#### U04 — Judgement, controls and exceptions

**Ask:** **“Which steps involve important professional judgement, controls, exceptions or dependencies?”**

**Documentation-review probes:**
- **DOC09 — Judgment and independence:** What is a rule-based requirement versus model-specific professional judgement? How are adequacy and risk implications reasoned, evidenced and independently challenged?
- **DOC10 — Exceptions:** What happens with changing models, conflicting versions, missing design information, urgent validation, or an unresolved material gap? Who escalates/approves?
- What legitimate review/control work must **not** be removed just to reduce elapsed time?
- **Optional universal U04 — Failure consequences:** If a material adequacy judgement is wrong, or the review cannot be completed, what happens to validation and who handles/escalates it? **Do not design a technical fallback or AI approval chain here.**

**Canvas §2 — Capture check:** Representative case/reference; approximately **five to eight meaningful tasks**, not clicks; input → decision/action → output; responsible person and tool; important handoffs, waiting and rework; judgement and required controls; key exception/failure consequences and escalation. Where a finding primarily concerns data/access or control authority, also record it in **§5**. **Do not classify professional challenge as waste or design system recovery at Stage 3.**

**If a case cannot be shown:** reconstruct the steps from an approved procedure plus a validator's recent recollection, flag the walkthrough **user-reported**, and assign a verification action. Do not fabricate a case reference.

### Canvas §3 — Problems and evidence (Phase C · 35–43 min)

#### U05 — Material problems and supporting evidence

**Ask:** **“Where are the most material problems, inefficiencies or risks in the current process?”**

**Probes:**
- **DOC11 — Documentation friction:** Is effort caused by incomplete submissions, evidence location, versioning, professional adequacy assessment, duplicated checking, or clarification loops?
- Can you point to an actual case, issue log, observation or comparable work-item measure?
- How frequent and consequential is it? What happens in cases where the process works well?
- Is the explanation a **verified root cause** or merely a **hypothesis**?

**Canvas §3 — Capture check:** Up to three material **business problems**; observed symptoms; affected users; evidence/source and its confidence; frequency or impact; possible root causes marked **verified versus hypothesis**. Keep any proposed technology as a **solution hypothesis**, not the business problem.

### Canvas §4 — Desired outcomes and measures (Phase C · 43–50 min)

#### U06 — Desired outcome and measurement

**Ask:** **“What improvement would be most valuable, and how could we demonstrate that it has been achieved?”**

**Probes:**
- **DOC12 — Outcome/quality:** Would the priority be lower **active review effort**, earlier identification of material gaps, fewer *unnecessary* clarification loops, better evidence traceability, or more effective risk-based review?
- What would you measure today? Is that an observed baseline, a Process Owner estimate, or unknown?
- What **one primary business metric** best captures the outcome? What **one or two quality/risk guardrails** must not worsen?
- If no baseline exists, who will collect comparable examples, using what method and before which later-stage decision?

**Canvas §4 — Capture check:** Desired outcome; **one primary business metric**; its baseline/source **or named owner and credible collection plan**; target direction (numeric target if defensible); **one or two risk/quality guardrails**; business acceptance owner. Distinguish **active effort, elapsed cycle time and waiting time**. Do not invent a target.

### Canvas §5 — Dependencies and existing capabilities (Phase D · 50–55 min)

#### U07 — Existing tools, information and constraints

**Ask:** **“What existing tools, information, constraints and dependencies should we consider?”**

**Probes:**
- **DOC13 — Source authority/restrictions:** Where are authoritative model documents, changes and validation findings held? Who owns access? What are the known restrictions on sharing, retention or AI processing?
- **DOC14 — Existing work:** Which documentation checklists, templates, scripts, Copilot prompts, Agent Builder solutions, Python tools, validation-platform components or PoCs already exist? What problem do they actually solve?
- Which methodological, independent judgement and operational approval boundaries must be preserved? What would be unacceptable if an aid produced an incorrect answer?
- **Optional universal U07 — Information usability:** Is the needed information **complete enough, reliable enough, up to date and accessible** for the current work? Where does its quality/availability break down? Record material issues; leave detailed remediation/technology design to Stage 4.

**Canvas §5 — Capture check:** Authoritative sources and their owners, when known; data/content usability and material access/processing restrictions; significant methodology, independence and approval boundaries; existing capabilities/PoCs and remaining gaps; unresolved specialist dependencies with follow-up owners. **Do not turn the call into an IT/security audit.**

### Canvas §6 — Opportunities and next steps (Phase D · 55–58 min)

#### U08 — Opportunities and next actions

**Ask:** **“Which improvement opportunities appear worth exploring, and what do we need to confirm next?”**

**Probes:**
- Could it be solved by better business guidance, standardisation, an existing tool or a small non-AI automation?
- Are there distinct opportunities (e.g. completeness checking versus professional adequacy analysis) that should not be treated as one agent?
- Which missing evidence could change the recommendation? Who will supply it and by when?
- What appears local to this team versus potentially common across MRO? **Unknown** is a valid answer.
- **Optional universal U08 — Validation/adoption participation:** Who would need to help **test whether an improvement works in practice**, accept its business outputs and support any workflow change? Identify likely people/roles, **not a full training or rollout plan**.

**Canvas §6 — Capture check:** Each candidate opportunity linked to a §3 problem and evidence; desired outcome and indicative value; possible existing/process-improvement route; local/common status if supported; users/acceptance participants; unresolved proof points; **next action and owner**. Formal Stage 4 progression remains subject to Gate 3. **Do not ask the Process Owner to select RAG, LangGraph, Power Apps or a deployment architecture.**

### Cross-section closing readback (Phase D · 58–60 min)

> “Our current understanding is that **[process and completion]**. The main issues appear to be **[up to three, with uncertainty stated]**. The business outcome worth improving is **[outcome]**, while preserving **[professional judgement/control]**. We will check **[evidence/measurement/access questions]** and send a short summary for your correction. Is anything material wrong or missing?”

**Call 1 success:** It is not necessary to complete every Canvas field or ask every probe. The Process Owner should recognise the process description; the FDE Lead should be able to describe the actual work, the most material candidate problems, and a short list of evidence/ownership questions. No extra mandatory call or questionnaire is created by the four refinements.

---

## 4. Compact documentation-review specialist bank (reference)

Use this bank *inside* U01–U08; it is **not another mandatory interview**.

| ID | Specialist dimension | Linked universal question | Canvas |
|---|---|---|---|
| DOC01 | Completeness versus methodological adequacy / validation readiness | U01 | §1 |
| DOC02 | Trigger, genuine completion and iterative review | U01 | §1 |
| DOC03 | Process owner, validator, method/control decision authority | U02 | §1/§5 |
| DOC04 | Model/team/risk-specific variants | U02 | §1/§5 |
| DOC05 | Documentation package, authoritative source and versions | U03 | §2/§5 |
| DOC06 | Applicable requirements and their provenance | U03 | §2 |
| DOC07 | Present versus sufficient/inconsistent/missing evidence | U03 | §2 |
| DOC08 | Clarification, update, reassessment and handoff loops; upstream/downstream boundary if relevant | U03 | §2 |
| DOC09 | Professional judgement, risk significance and independence | U04 | §2/§5 |
| DOC10 | Exceptions, wrong-judgement consequences, unresolved gaps, escalation and approval | U04 | §2/§5 |
| DOC11 | High-impact review pain points and their causes | U05 | §3 |
| DOC12 | Value, baseline, target direction and guardrails | U06 | §4 |
| DOC13 | Source quality, completeness, accessibility, provenance and restrictions | U07 | §5 |
| DOC14 | Existing tools, templates, prompts and PoCs | U07 | §5 |

### Adaptive follow-up patterns for the facilitator or Discovery Grill

| Trigger | Follow-up type | Example |
|---|---|---|
| “It is manual and slow” | Clarify the task | “Which activity consumes active effort, and which time is waiting?” |
| A material claim without a case | Evidence | “Can you show one approved review where that occurred?” |
| “The model owner never sends enough information” | Root-cause/counterexample | “Which requirement was missing? What was different when submissions worked well?” |
| Linear description of an iterative review | Exception | “What happens on the second document version or after a material gap?” |
| “We want an AI review agent” | Problem/solution separation | “What business failure would the agent address, and what alternative might resolve it?” |
| “Save 50% of the time” | Measurement/guardrail | “Save active time or elapsed time? On comparable cases? What review quality must be maintained?” |
| “This is common for everyone” | Variant/confirmation | “Which other team has confirmed the same requirements and decision boundaries?” |
| “It goes to another team and comes back” | Upstream/downstream | “What causes the handoff or return, and how does it affect the review?” |
| “The review sometimes goes wrong” | Failure consequence | “What happens to the validation decision and who takes responsibility?” |
| “The documents exist somewhere” | Information usability | “Are those documents current, sufficiently complete and accessible to the validator?” |
| “Our team would use the tool” | Adoption/ownership | “Who would validate the result and help colleagues adopt a changed workflow?” |

**U08 business-participation follow-up has no new `DOC` ID** because it is already universal and can be applied to every MRO process. No need to force an individual documentation-specific question under every U question. **Standard question IDs are for FDE and the skill, not for reading aloud to Process Owners.** The FDE Lead follows the conversation and chooses only probes that address a material gap.

---

# Part B — Capture and Validate the Findings

**Use the same Canvas §§1–6 headings as in the call guide.** Populate from interview notes and approved evidence after the conversation, noting what is verified, user-reported, hypothesised or unknown. The worked example below remains illustrative.

## 5. Worked example: completed draft Canvas (illustrative, NOT verified)

These examples demonstrate **how answers become the six sections**. In an actual engagement, attach references to approved evidence and label status carefully (`verified`, `user-reported`, `hypothesis`, `unknown`). Never create fake metrics or references and pass them off as real.

### Header and Canvas §1 — Process and ownership

| Field | Illustrative draft entry | Status / action |
|---|---|---|
| Parent priority | Model Documentation Review — [Stage 2 decision ID] | Obtain reference |
| Team/variant | AI Independent Validation — evolving documentation variant | Scope to confirm |
| Process Owner | [Role/name] | Confirm |
| Actual user / Methodology Owner | [Validator] / [role if applicable] | Confirm |
| Purpose | Determine whether documentation and supporting evidence are sufficient to support independent validation, and identify consequential gaps | Hypothesis |
| Starts | Evidence/documentation is submitted or materially revised | Hypothesis |
| Genuinely completes | Review findings and next validation action are recorded; documentation might still change | Hypothesis |
| Boundary | Assessment, gap handling and follow-up; excludes autonomous approval or changing validation standards | To agree |

### Canvas §2 — Actual work and decisions

| Task / decision | Input → output | Actor / tool | Judgement / required control | Evidence / exception |
|---|---|---|---|---|
| Receive/version evidence | Submitted artefacts → identified review set | Validator / approved repository | Correct version and provenance | Source reference **TBD**; conflicting versions |
| Interpret requirements | Model context + standards → applicable checklist | Validator / method standards | Applicability and model-specific exceptions | Source reference **TBD** |
| Locate and assess evidence | Documents → completeness/adequacy observations | Validator / available search/tools | Evidence existence **≠** adequacy | Case reference **TBD** |
| Raise important gaps | Observation → targeted request | Validator/model owner | Materiality, priority and escalation | Request history **TBD** |
| Reassess revisions | Updated artefacts → revised observations | Validator / controlled records | Reassessment and version traceability | Rework example **TBD** |
| Record outcome | Gap assessment → next validation action | Validator / approved process | Human judgement and relevant approvals | Record **TBD** |

**Candidate flow (to validate):** upstream submission/ownership → applicable requirements → evidence assessment → issue/clarification loop → recorded next validation action → downstream use. Capture waiting/rework and the actor who takes responsibility for a stalled or erroneous outcome **only if material**. Use a concise task table first; a swimlane only if cross-team handoffs obscure control, and a state diagram only if iterative states are central.

### Canvas §3 — Problems and evidence

| ID | Business problem (candidate) | Symptom | Evidence status | Likely cause |
|---|---|---|---|---|
| PP-01 | Relevant evidence may be time-consuming to locate | Repeated searching across artefacts | **Unverified**; requires an approved case and/or observation | Fragmented sources / version handling **hypothesis** |
| PP-02 | Clarification loops may produce avoidable rework | Repeated requests and reassessment | **Unverified**; requires case/request history | Unclear submission expectations **hypothesis** |
| PP-03 | Assessment of incomplete evidence may be difficult to apply consistently | Differences in gap descriptions and next actions | **Unverified**; specialist case + methodology owner input needed | Criteria/judgement boundary **hypothesis** |

**Problem statement formulation:** `Affected user and process` + `current difficulty` + `impact` + `evidence/confidence` + `desired outcome` + `constraints`. Keep `solution hypothesis` separate from the problem.

### Canvas §4 — Desired outcomes and measures

| Desired outcome | Primary metric | Baseline/source or plan | Target | Guardrail | Business owner |
|---|---|---|---|---|---|
| Reduce effort spent locating relevant evidence | Active minutes locating/organising evidence per **comparable** review | Unknown; candidate plan: time log for approved sample reviews | Direction: decrease; numeric target **TBD** | No degradation in identifying material gaps; source/version traceability | Process Owner to confirm |
| Reduce *unnecessary* clarification loops | Avoidable repeat clarification requests per comparable review | Unknown; consider approved request history | Direction: decrease | Do not suppress necessary independent challenge | Process Owner/Methodology Owner to agree definition |

**Measurement note:** A review spanning three days does not imply three days of active effort. Distinguish elapsed time, waiting and actual reviewer work. Record estimates as estimates, never as observed baseline. Stage 3 should agree a credible plan when baseline data do not yet exist.

### Canvas §5 — Dependencies and existing capabilities

- **Authoritative information:** model documentation, applicable methodology/standards, model-owner responses, validator findings and version history. **Verify actual systems, ownership, permissible access and provenance.**
- **Judgement and controls:** independent validator judgement; specific adequacy or exception approvals must be confirmed with relevant authority. No tool is assumed to approve documentation or risk status.
- **Information usability:** confirm whether the documents needed for the task are sufficiently complete, current, internally consistent and accessible. These are candidate business constraints, not a Stage 3 mandate to remediate data quality.
- **Processing restrictions:** establish whether sample/production evidence may be read, copied, stored or sent to approved AI services. Keep raw restricted artefacts within permitted systems; link rather than duplicate.
- **Existing capabilities:** check checklists and templates, Copilot prompts/Agent Builder, Python scripts, relevant validation-platform features and prior PoCs. Record actual maturity and overlap.
- **Cross-team classification:** `Unknown` until comparable requirements are confirmed with another MRO team.

### Canvas §6 — Opportunities and next steps

| ID / opportunity | Problem link | Indicative value | Recommendation (provisional) | Parent/child | Next action |
|---|---|---|---|---|---|
| OPP-01: Improve identification/organisation of supporting evidence | PP-01 | Potential review-effort saving; **not quantified** | Candidate for Stage 4 **after evidence confirmation** | Parent initially | Verify case, metric, control and existing solutions |
| OPP-02: Improve submission instructions/standards | PP-02 | Potential reduction in avoidable requests | Evaluate existing business/methodology route | Remain parent | Check applicable standards and method owner |
| OPP-03: Support risk-based assessment of evidence gaps | PP-03 | Potential quality/risk benefit; high judgement sensitivity | Targeted Discovery first | Child only if materially distinct ownership/scope | Review real case and decision standards with methodology SMEs |

**Adoption and acceptance participants:** `To confirm`: relevant validator(s), Process Owner, and Methodology Owner when review methodology is materially affected. No Stage 3 training/rollout plan is required.

**Process Owner confirmation:** `Pending` until documented.  
**Important unknowns:** Case evidence, true review boundary, baseline comparability, authoritative source usability, method/control authority, relevant users for later acceptance/adoption and existing solution coverage.

## 6. FDE synthesis: convert interview answers to credible findings

Complete this work **after** the call; do not ask the Process Owner to populate technical tables.

1. **Populate the six sections** with source-backed statements; link rather than copy source documents.
2. **Decompose only material tasks:** `input → judgement/decision → action → output → side effect → responsible role`.
3. **Separate:** business problem, symptom, possible root cause, solution hypothesis and existing solution.
4. **Test causality:** look for a good counterexample and distinguish active work, waiting, rework and necessary independent challenge.
5. **Assess value:** primary measure, baseline/source or owned collection plan, expected direction, relevant quality/risk guardrails.
6. **Map existing initiatives:** what is live, experimental, personally used, shared, approved or constrained; avoid duplicative new builds.
7. **Assign evidence status and action owner:** `Verified / User-reported / Hypothesis / Unknown` and date/source where available.
8. **Group opportunities**, but do not assume shared process names imply one shared solution.

### Lightweight evidence/action log (only when needed)

| ID | Finding / question | Status | Evidence location (approved) | Responsible owner | Due/next decision |
|---|---|---|---|---|---|
| EV-01 | Example of evidence-location friction | Not yet verified | [Approved source, once confirmed] | Validator / FDE | Before Gate 3 |
| ACT-01 | Confirm formal adequacy authority | Open | [Methodology reference] | Methodology Owner | Targeted follow-up |
| ACT-02 | Define active-time baseline approach | Open | [Measurement plan] | Process Owner + FDE | Before evaluation design |

### Conditional specialist follow-up (not a routine second workshop)

| SME | Ask only what is needed to resolve a consequential question |
|---|---|
| Experienced validator | Show a meaningful gap, version/rework loop and how significance was assessed |
| Methodology Owner | Confirm formal requirements, independent judgement, issue/risk significance, exceptions and authority for changes |
| Data/platform/security | Confirm authorised sources, processing and access restrictions, representative test data feasibility |
| Process Owner | Validate process, business value, baseline plan and ownership of outcome |

### Process Owner readback template

**Subject:** FDE Discovery Readback — Model Documentation Review — [Team]

> Thank you for the discussion. Our **draft** understanding is that [process, boundary and actual completion]. The main problems appear to be [up to three, indicating which are verified or still hypotheses]. We believe the improvement worth investigating is [outcome] and would measure it using [metric/baseline plan], while preserving [critical control or professional judgement]. We have recorded open points on [evidence, methodology, access]. Could you please correct anything materially inaccurate, particularly the workflow, decision ownership, root causes and success measures? We propose [targeted next actions] before the Stage 3 playback.

---

# Part C — Validate, Route and Communicate

## 7. Playback and Gate 3 (30 min; asynchronous where proportionate)

| Time | Playback discussion | Required confirmation |
|---|---|---|
| 0–10 min | One-page current state and key decision/control steps | Correct process boundary, owner, roles and actual work |
| 10–18 min | Up to three problems with evidence confidence, baseline and value hypothesis | Accuracy, materiality and necessary guardrails |
| 18–25 min | Opportunities; existing alternatives; remaining unknowns | Candidate opportunity routing |
| 25–30 min | Six gate criteria and next actions | Process Owner validation and appropriate recorded gate decision |

### Gate 3 — Six required checks

- [ ] **Process:** Purpose, start/end, ownership, meaningful tasks and professional judgement/control understood.
- [ ] **Evidence:** Material problems backed by approved evidence or explicitly qualified with owned proof actions; no unverified issue misrepresented as established.
- [ ] **Value:** Desired outcome and credible indicative business impact understood.
- [ ] **Measurement:** Primary KPI, baseline or agreed collection plan and guardrail specified.
- [ ] **Constraints:** Methodology, independence, information access/security, relevant existing tools and important dependencies considered.
- [ ] **Action:** Process Owner validates current-state findings; opportunities have recommended dispositions and owners.

**Gate decision choices:** `Ready / Conditional (named conditions and delegated approval) / More Discovery / Revise / Stop or escalate`. An unsupported opportunity should **not** be presented as authorised for Stage 4. A Process Owner validates business facts; FDE recommends readiness; the delegated authority records progression. SLT retains material reprioritisation decisions.

### Example opportunity-level decision record (still illustrative)

| Opportunity | Proposed progression | Case route | Condition / owner |
|---|---|---|---|
| OPP-01 | Candidate Stage 4, **not yet authorised** | Parent | Validate actual effort/evidence and guardrails; FDE + Process Owner |
| OPP-02 | Check existing business/methodology route | Parent | Verify guidance/standard owner; Methodology Owner |
| OPP-03 | Continue targeted Discovery | Child TBD | Establish separate risk-based need and independent authority; SME |

**Parent/child rule:** Recommend a Child Case only if outcome, ownership, risk or delivery boundary is materially different. A new Discovery Wave is a proposed extension to another team/variant, subject to leadership priorities and agreed capacity. One adequately evidenced and authorised opportunity can move to Stage 4 without awaiting every team's discovery.

## 8. Generate Output A — Stage 4 Opportunity Brief (1–2 pages each)

Create **one Brief per authorised opportunity**, linked back to the Canvas; do not force different problems into one agent proposal. The following is an **illustrative draft only**, not a formal approved handover.

### OPP-01 — Improve evidence identification in documentation review

| Field | Example from the draft Canvas |
|---|---|
| **Parent/team and owner** | Model Documentation Review / [AI IVT example]; Process Owner TBD |
| **Problem & evidence** | Potential manual effort locating evidence across documentation sources/versions; **unverified** pending case evidence |
| **Relevant business task** | Determine requirements → locate evidence → assess adequacy → record findings/clarifications; validator retains risk judgement |
| **Desired outcome** | Reduce time finding and organising evidence without degrading review quality |
| **Initial business scope** | Selected model/document type, bounded evidence-identification task; **to agree** |
| **KPI/baseline/target** | Active evidence-identification minutes per comparable review; baseline pending; target direction decrease |
| **Guardrails** | Material-gap coverage not degraded; references to authoritative source/version; independent validator retains decisions |
| **Constraints/dependencies** | Permitted data access/processing; document completeness/currency; methodology ownership; versioning; existing-tool overlap |
| **Existing solutions to compare** | Better guidance/templates, deterministic checks/search, available approved tools/prompts, earlier PoCs |
| **Stage 4 questions** | Which solution family is suitable, what can be reused, what test dataset/evaluation is authorised, how to validate measurable benefit and accuracy? |
| **Business acceptance participants** | Process Owner and one or more actual validators; Methodology Owner consulted if judgement/standards are affected — roles to confirm |
| **Gate/next action** | Draft only; do not release as formal Stage 4 until authorised |

**Boundary:** Stage 3 describes the *business problem and initial scope*. Stage 4 selects solution approach, designs MVP, assesses technical feasibility and produces a PoC/evaluation plan.

## 9. Generate Output B — SLT Discovery Update (one page per leadership priority)

This should be short, factual, decision-oriented and may be issued **during discovery** if marked preliminary. A separate slide for every team is usually unnecessary: consolidate under the Stage 2 parent priority.

### Example — Model Documentation Review (illustrative only)

**Priority / status:** Model Documentation Review — Wave 1 [Team]; Discovery **in progress**.  
**Coverage:** Process Owner engagement [planned/completed], representative item [pending/verified].  
**Emerging findings (not yet validated):** Potential effort locating/versioning relevant evidence; clarification/rework loops; separate requirements for completeness and professional adequacy.  
**Potential opportunities:** (1) Support evidence identification; (2) improve submission guidance through an existing business route; (3) explore risk-based evidence-gap support through targeted discovery.  
**Expected value / metrics:** Candidate active reviewer time and clarification-cycle metrics; **no established baseline or realised benefit** yet. Protect material gap detection, traceability and independent judgement.  
**Dependencies:** Approved case evidence, methodology authority, information completeness/access, validator involvement in later acceptance and existing-tool overlap.  
**FDE recommendation:** Verify case evidence and measurement plan; then assess opportunity-specific Gate 3 readiness.  
**SLT decision requested:** None unless a material priority, resource or new-wave change requires direction.  
**Next milestone/owners:** [Activity and owner; target date if agreed].

**For SLT, always answer:** What did we discover? What is the possible value? What happens next? What is blocking progress? Is leadership action required? Avoid premature technology/design detail.

## 10. Extend across MRO teams without repeating work unnecessarily

1. Keep one **parent** priority record for Model Documentation Review; create a linked Canvas per meaningful team/process variant.
2. Use the **same U01–U08 questions** in every team; choose process-specific probes for the actual workflow and model types.
3. Compare process purpose, completion, applicable standards, substantive judgement, evidence sources, pain points, success metrics, existing tools and opportunities.
4. Classify requirements as `Local / Potentially Common / Clearly Common / Unknown` **based on process evidence**, not a superficial similar label.
5. Carry forward existing evidence and already-validated requirements; ask only questions needed to confirm differences.
6. Stage 4 determines actual technical reuse; Stage 3's commonality judgement does **not** prescribe a shared RAG or agent architecture.
7. SLT receives one aggregated parent-priority update, with process-variant distinctions and material decisions highlighted.

| Comparison dimension | Team / variant A | Team / variant B | Implication |
|---|---|---|---|
| Genuine review completion | [ ] | [ ] | [ ] |
| Requirements/methodology ownership | [ ] | [ ] | [ ] |
| Critical human judgement/control | [ ] | [ ] | [ ] |
| Evidence/data/version constraints | [ ] | [ ] | [ ] |
| Material problems and supporting evidence | [ ] | [ ] | [ ] |
| Primary success metric and guardrail | [ ] | [ ] | [ ] |
| Existing tools or initiatives | [ ] | [ ] | [ ] |
| Opportunities and next route | [ ] | [ ] | [ ] |

## 11. Final deliverables and definition of done

### What the four refinements add to outputs — without creating new deliverables

| Optional probe | Canvas location | What Stage 4 or SLT gains |
|---|---|---|
| U03 — upstream/downstream handoffs | §2 | Correct improvement boundary and cross-team dependency; only material handoffs summarised for SLT. |
| U04 — consequences/owner of failure | §§2/5 | Business risk and human-control requirements; material risks or escalation shown to SLT. |
| U07 — information usability | §5 | Data/content suitability question for option assessment; blockers and owners for SLT when material. |
| U08 — acceptance/adoption participants | §6 (or §1 for owners) | Who can validate the future business outcome; adoption dependency/decision if material. |

| Deliverable | Required when | Owner / receiver |
|---|---|---|
| **Discovery Canvas** — six sections, evidence/uncertainty, process owner confirmation | Every Discovery Wave | FDE Lead / Process Owner |
| **Gate 3 Record** — six checks, decision authority, per-opportunity progression, conditions | Before formal progression | FDE + relevant delegated decision owner |
| **Stage 4 Opportunity Brief** — one per opportunity **approved** for Stage 4 | On authorised progression | FDE / Stage 4 engineering |
| **SLT Discovery Update** — consolidated parent-priority one-pager | For steering rhythm and material decisions; may be preliminary | FDE Lead / SLT |
| **Expanded evidence or process analysis** — specialised diagrams, risk reviews, detailed metrics | **Only where material and justified** | Relevant SMEs / FDE |

**Definition of done:** A Process Owner-validated and evidence-aware understanding of the selected workflow; meaningful task/decision decomposition; an identifiable business problem and success measure (or owned measurement plan); critical constraints and existing solutions considered; actionable opportunities with explicit dispositions; and a Gate 3 record that can support credible Stage 4 handover and concise SLT updates.

---

# Appendix — Live call note-taking mini-sheet (six-section alignment)

Use this **during** the call as a light six-section Canvas. Add evidence/status inline and transfer only if notes were kept separately. A single answer can be referenced in more than one section; **do not ask it twice**.

| Canvas / question anchors | Short live notes: finding; evidence/source; verified / reported / hypothesis / unknown; next owner |
|---|---|
| **§1 Process and ownership** — U01–U02 | [Purpose; start/end; owner; methodology; scope/variant] |
| **§2 Actual work and decisions** — U03–U04 | [Real work item; meaningful tasks; handoffs; judgement; controls; exceptions] |
| **§3 Problems and evidence** — U05 | [Top pain points; impact; evidence; root-cause hypothesis] |
| **§4 Desired outcomes and measures** — U06 | [Outcome; primary metric; baseline/plan; guardrails; business owner] |
| **§5 Dependencies and existing capabilities** — U07 | [Authoritative information; quality/access; restrictions; tools/PoCs; SMEs] |
| **§6 Opportunities and next steps** — U08 | [Opportunity → problem; existing/process route; unknowns; acceptance participants; owner/action] |

**Call close:** Process Owner corrections: [ ] · Evidence actions: [ ] · Next playback/review: [ ]

**Question framework extensibility:** Keep **U01–U08 unchanged** across all MRO work. The four extra probes are optional **within** U03/U04/U07/U08. Extend with modules like `CODE`, `TEST`, `BENCH`, `REPORT-GEN` and `REPORT-REV`. Specialist questions add depth but **never** create another mandatory interrogation, another Canvas, or different downstream output types.
