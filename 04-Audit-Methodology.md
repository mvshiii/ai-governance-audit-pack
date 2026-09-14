# 04 — AI Governance Audit Methodology

A practical, risk-based methodology for a Malaysian financial institution, plus a step-by-step walkthrough.

---

## 4.0 Design principles

Before the phases, five decisions that shape everything:

1. **Audit the governance system first, the individual models second.** A one-off deep dive into three models tells the audit committee nothing about the other thirty-eight. Audit whether the *process* works, and use models as evidence of whether it works.
2. **Anchor on mandatory criteria.** See [03 §3.3](03-Malaysian-Landscape.md). RMiT and PDPA give you enforceable findings today.
3. **Scope on use cases, not on "AI."** "AI" is unauditably broad. A use case has an owner, a purpose, data, a decision and an impact.
4. **Separate governance assurance from technical validation.** You test that validation happened properly. You do not re-perform it. See [07](07-Specialist-Reliance.md).
5. **Budget for the inventory.** In a first-year AI audit, expect to spend 25–35% of the engagement establishing what AI actually exists. That is not a distraction — it is frequently the most valuable output of the whole audit.

---

## PHASE 0 — Position and Prepare
*(Pre-engagement; typically 1–2 weeks)*

| | |
|---|---|
| **Objective** | Establish audit criteria, define scope boundaries, and secure the specialist support the engagement will need — before fieldwork starts |
| **Activities** | Confirm the criteria tiers (mandatory / expected practice / good practice); obtain and read the current RMiT PD, the AI Governance Framework, the JPDP ADMP Guideline and any BNM AI publication issued since; agree the structuring reference (NIST AI RMF *or* ISO 42001); define what counts as "AI" for scoping purposes and write it down; identify specialist needs and book them; agree the engagement's position on relying on 2nd line work; draft the terms of reference |
| **Stakeholders** | Head of IT Audit, CAE, Model Risk/Validation, Compliance, Legal, external specialist if used |
| **Evidence required** | Current regulatory documents; prior audit reports touching AI; 2nd line AI risk assessments and their methodology; regulatory correspondence on technology and AI |
| **Audit procedures** | Criteria mapping exercise; review of prior coverage to avoid duplication and to identify unremediated related findings; **scope definition test** — write a one-paragraph definition of "in scope AI" and test it against five borderline examples (a rules engine, an Excel macro, a purchased CRM with a lead scorer, a GenAI copilot, an RPA bot). If your definition cannot classify all five consistently, rewrite it |
| **Expected output** | Approved terms of reference with an explicit scope definition and a criteria matrix labelled by tier |

> 🔴 **Write the scope definition down.** Suggested working definition: *"Any system, component or service whose behaviour is derived from data through machine learning, or which generates content or recommendations using a generative model, and whose output informs a business process, decision or customer interaction — whether developed internally, purchased as a product, embedded within a purchased product, or consumed as a service."* The phrase **"embedded within a purchased product"** is what catches the AI everyone forgets.

---

## PHASE 1 — Understand
*(2–3 weeks)*

| | |
|---|---|
| **Objective** | Build an accurate, independent picture of the institution's AI landscape, governance arrangements, technology environment and maturity — sufficient to scope intelligently |
| **Activities** | Walkthrough interviews across 1st, 2nd and 3rd line; obtain and challenge the AI inventory; map the AI technology estate (platforms, clouds, model registries, vendors); understand the governance structure and decision rights; understand how AI plugs into (or bypasses) existing IT, data, model risk and third-party processes; understand strategy and pipeline — what is coming next |
| **Stakeholders** | CIO/CTO, Chief Data Officer / Head of AI, CRO, Head of Model Risk, CISO, DPO, Head of Compliance, Head of Third-Party Risk, Head of Change Management, 3–5 business AI owners, Chief Architect |
| **Evidence required** | AI strategy and roadmap; AI policy and standards; AI inventory; governance forum ToR and 12 months of minutes; AI risk appetite statements; org charts for data science, model risk, IT; architecture diagrams for AI platforms; list of AI vendors; recent 2nd line assessments; regulatory correspondence; prior related findings |
| **Audit procedures** | Structured walkthroughs using a standard question set; **inventory triangulation** (see §4.2); technology estate mapping from cloud subscription data and architecture records; governance forum minute review; maturity assessment against the chosen structuring reference; identification of the "orphan zone" — AI that no existing process claims |
| **Expected output** | (a) Independently corroborated AI inventory with a completeness assessment; (b) governance map showing decision rights and gaps; (c) preliminary maturity view; (d) a documented list of scoping candidates |

**The five questions that structure every Phase 1 interview:**
1. What AI does your area use, including anything embedded in a product you bought?
2. Who decides whether it can be used, and who signs it off?
3. What happens if it is wrong — who finds out, and how?
4. What would you do tomorrow if it stopped working?
5. What AI are people in your area using that isn't on the official list?

Question 5 asked without judgement, late in the interview, is remarkably productive.

---

## PHASE 2 — Scope and Risk Assess
*(1–2 weeks)*

| | |
|---|---|
| **Objective** | Convert the landscape into a defensible, risk-based scope: which domains, which use cases, at what depth |
| **Activities** | Apply an independent risk rating to every inventoried AI system; compare to the institution's own ratings and investigate divergence; select use cases for detailed testing; determine domain coverage; confirm specialist requirements; agree scope with the Head of IT Audit and communicate it to management |
| **Stakeholders** | Head of IT Audit, CAE, engagement team, Model Risk, business owners of selected use cases |
| **Evidence required** | Completed inventory; the institution's own AI risk assessments and rating methodology; criticality ratings from the BCM/critical business service register; customer volume data; regulatory exposure mapping |
| **Audit procedures** | Independent risk scoring (see §4.3); **rating divergence analysis** — where audit's rating exceeds management's, that is itself a preliminary finding about the risk assessment control; stratified sample selection (see §4.4); coverage matrix mapping selected use cases against the 10 audit domains to confirm no domain is untested |
| **Expected output** | Approved scope document containing: domains in scope, use cases selected with documented rationale, use cases excluded with rationale, specialist plan, and a coverage matrix |

> **Document why you excluded things.** Six months later, when an incident occurs in an area you did not cover, a documented, risk-based exclusion rationale is the difference between a defensible scoping decision and an audit failure.

---

## PHASE 3 — Assess Governance and Control Design
*(2–3 weeks)*

| | |
|---|---|
| **Objective** | Determine whether the controls, as designed, would achieve the control objectives if they operated as intended |
| **Activities** | Assess entity-level AI governance (policy, structure, risk appetite, roles, reporting); walk through the AI lifecycle end-to-end for one representative use case; assess design of controls in each in-scope domain; identify design gaps before spending effort testing operation |
| **Stakeholders** | Policy owners, control owners, 2nd line functions, process owners |
| **Evidence required** | AI policy, standards, procedures; risk assessment methodology; validation standard; approval authority matrix; monitoring standard; change policy coverage of AI assets; third-party AI due diligence standard; incident taxonomy |
| **Audit procedures** | Policy-to-practice gap analysis; **control design walkthrough** — for one use case, follow it from intake to production, meeting each control owner and seeing each control artefact; design adequacy assessment against the criteria matrix; identification of controls that exist on paper with no owner, no frequency or no evidence trail |
| **Expected output** | Design effectiveness conclusion per domain; a list of design gaps (reportable without further testing); a refined testing plan focused where design is adequate |

> 🔴 **Design gaps are reportable in their own right and cost far less to find.** If the change management policy does not mention models, prompts or training data, you do not need to sample change records to conclude that AI change is not controlled. Test design first; it will often halve your testing effort.

---

## PHASE 4 — Test Operating Effectiveness
*(3–4 weeks)*

| | |
|---|---|
| **Objective** | Determine whether controls operated as designed, consistently, throughout the period |
| **Activities** | Sample-based testing of each in-scope control; use-case deep dives; reperformance and observation where possible; specialist-supported testing where required; corroboration of management assertions against system data |
| **Stakeholders** | Control operators, AI/model owners, IT operations, security, vendor managers, specialists |
| **Evidence required** | Per test — see [06 — Sample Audit Tests](06-Sample-Audit-Tests.md) |
| **Audit procedures** | Attribute sampling on populations (change records, approvals, access reviews, risk assessments); **system-generated evidence in preference to management-prepared evidence** — extract the access list yourself rather than accepting a spreadsheet; observation of controls being performed (human oversight, output review); reperformance (re-rate a risk assessment, re-run an entitlement check); the reconstruction test; version reconciliation |
| **Expected output** | Working papers with conclusions per control; validated exceptions; draft findings with root cause |

**Testing hierarchy — prefer evidence in this order:**
1. **Reperformance** — you do it yourself and compare (re-rate a risk assessment; query the model registry)
2. **System-extracted data** — you pull it from the source system
3. **Observation** — you watch the control being performed
4. **Inspection of records** — you examine documents produced in the normal course of business
5. **Management-prepared analysis** — accept only with corroboration
6. **Inquiry alone** — never sufficient on its own

🔴 AI audits generate an unusual amount of category 5 and 6 evidence because so much AI activity is undocumented. **Push relentlessly toward categories 1–3.** "The data science team confirmed they monitor the model" is not an audit conclusion.

---

## PHASE 5 — Report and Follow Up
*(2 weeks + ongoing)*

| | |
|---|---|
| **Objective** | Communicate risk clearly to a non-technical audience, drive remediation, and establish a baseline for future coverage |
| **Activities** | Validate facts with management; determine root cause (not just symptom); rate findings; agree management actions with owners and dates; report to the Audit Committee; track remediation; retest |
| **Stakeholders** | Management action owners, Head of IT Audit, CAE, Audit Committee, Board Risk Committee |
| **Evidence required** | Completed working papers; management responses; remediation evidence at follow-up |
| **Audit procedures** | Root cause analysis grouping symptoms into themes; finding rating against the institution's methodology with explicit consideration of *aggregation* — twelve small AI control gaps across the lifecycle may aggregate to a significant governance weakness; criteria tiering per [03 §3.3](03-Malaysian-Landscape.md); remediation adequacy review; retest on closure |
| **Expected output** | Audit report; agreed actions with owners and dates; an AI risk baseline for the audit universe; input to next year's audit plan; **a recommendation on continuous monitoring** |

**Reporting rules for an AI audit specifically:**
- **Lead with business consequence, not technical detail.** Not "the model exhibits distributional drift"; instead "the fraud model's performance has degraded and nobody would know — the bank may be missing fraud it previously caught."
- **Group by theme, not by system.** Eight instances of "no monitoring" across eight models is one finding with eight examples, not eight findings.
- **State the criteria tier explicitly** in every finding.
- **Distinguish "this control failed" from "this control does not exist."** The second is usually more serious and needs a different remediation owner.
- **Quantify where you can.** "14 of 41 AI systems" lands; "several systems" does not.

---

## PHASE 6 — Continuous Monitoring
*(Ongoing — this is the improvement to the standard five-phase model)*

| | |
|---|---|
| **Objective** | Maintain assurance between audits in an estate that is changing faster than an annual audit cycle can track |
| **Activities** | Agree a small set of AI risk indicators with 2nd line; obtain periodic data feeds; monitor for new AI systems appearing outside governance; attend (as observer) the AI governance forum; review AI incidents as they occur |
| **Stakeholders** | Head of IT Audit, 2nd line Risk, AI governance forum secretariat |
| **Evidence required** | Periodic inventory extracts; governance forum minutes; AI incident reports; monitoring threshold breach reports; new vendor onboarding data |
| **Audit procedures** | Quarterly inventory reconciliation against procurement and cloud billing data (cheap, automatable, high yield for shadow AI); trend analysis on override rates and threshold breaches; standing review of AI items in the incident register |
| **Expected output** | Quarterly AI assurance update to the Head of IT Audit; early identification of emerging risk; a continuously refreshed audit universe |

> **Why this phase matters:** an AI estate that grew from 18 to 41 systems in a year cannot be assured by a point-in-time audit performed once every two years. Even a lightweight quarterly reconciliation materially improves coverage.

---

# PART 6 — Practical Walkthrough

## Step 1 — Understand AI usage

### The seven questions

| Question | Why it matters | Where to look |
|---|---|---|
| **What AI systems exist?** | Defines the audit universe | Inventory; procurement; cloud billing; architecture repository; vendor list |
| **Who owns them?** | Accountability; also tells you who to interview | Inventory; policy; interviews |
| **What business processes use them?** | Determines impact and criticality | Process maps; business owner interviews; critical business service register |
| **Internally developed or third party?** | Determines which control set applies | Inventory; contracts; architecture |
| **What data do they process?** | Determines privacy, secrecy and quality exposure | Data flow diagrams; DPIAs; data catalogue |
| **What decisions depend on them?** | The core risk question — decision impact drives everything | Business owner interviews; process walkthroughs |
| **Do they affect customers?** | Triggers conduct, fairness, transparency and ADMP considerations | Product and journey documentation; customer communications |

### Document and evidence request list

**Governance**
- [ ] AI policy, standards and procedures (with approval and review dates)
- [ ] AI strategy / roadmap and current project pipeline
- [ ] AI governance forum terms of reference, membership, 12 months of minutes and papers
- [ ] Delegated authority matrix for AI approvals
- [ ] AI risk appetite statement and how it is measured
- [ ] Board and Board Risk Committee reporting on AI (last 12 months)
- [ ] RACI for AI across the three lines

**Inventory and classification**
- [ ] Complete AI inventory extract (raw data, not a summary)
- [ ] AI risk classification methodology
- [ ] Completed risk assessments for all high-risk systems
- [ ] Register of solely-automated decisions affecting customers

**Lifecycle**
- [ ] AI intake / use case approval records
- [ ] Solution design documents for sampled systems
- [ ] Data sourcing, lineage and quality documentation; DPIAs
- [ ] Model validation standard and validation reports for sampled systems
- [ ] Approval records for sampled systems
- [ ] Monitoring plans and 12 months of monitoring output
- [ ] Change records for AI systems (including prompts and retraining)
- [ ] Decommissioning records

**Technology and security**
- [ ] AI platform architecture and hosting details
- [ ] User and privileged access lists for AI platforms, model registries, training data stores
- [ ] Most recent user access review evidence for AI platforms
- [ ] Penetration test and security assessment reports covering AI systems
- [ ] Logging configuration and sample logs (prompts, outputs, admin actions)
- [ ] Encryption and key management arrangements for AI data stores

**Third party**
- [ ] AI vendor list with criticality and outsourcing determination
- [ ] Due diligence files and contracts for sampled AI vendors
- [ ] Independent assurance reports (SOC 2 / ISO 27001 / ISO 42001) and the bank's review of them
- [ ] Vendor model change notifications received and impact assessments

**Operations and incidents**
- [ ] Incident register filtered for AI-related incidents
- [ ] Complaints data relating to AI-driven decisions or channels
- [ ] Fallback / BCP procedures for AI-dependent processes and evidence of testing
- [ ] Override / exception statistics for human-in-the-loop controls

**GenAI specifically**
- [ ] Acceptable use policy for GenAI and evidence of staff communication/training
- [ ] List of approved and blocked GenAI services; proxy/CASB configuration
- [ ] Tenant configuration evidence for enterprise AI services (data retention, training opt-out)
- [ ] Prompt and output logging configuration, retention and access controls
- [ ] Output quality sampling programme and results

---

## Step 2 — Establish the AI inventory

### Recommended inventory structure

| Field | Why it is there |
|---|---|
| AI System / Use Case ID and Name | Unique reference |
| Business Owner (named individual) | Accountability |
| Technology Owner (named individual) | Operational accountability |
| Purpose / business process supported | Impact assessment |
| AI Type (rules / classical ML / GenAI / computer vision / NLP / agentic) | Determines applicable controls |
| Build vs Buy vs Embedded-in-product | Determines control set |
| Third party / vendor and hosting location | Outsourcing, secrecy, cross-border |
| Data used, and whether it includes personal / sensitive / customer information | Privacy and secrecy exposure |
| Customer impact (none / indirect / direct / solely automated decision) | Conduct and ADMP trigger |
| Degree of automation (advisory / human-in-loop / human-on-loop / fully automated) | Oversight requirement |
| Supports a critical business service? (Y/N) | Resilience requirement |
| Risk rating and date rated | Drives assurance depth |
| Validation status and date | Assurance currency |
| Approval reference and expiry | Governance evidence |
| Monitoring in place (Y/N) and frequency | Ongoing control |
| Deployment status (pilot / production / retired) | Scope |
| Date added / last reviewed | Inventory hygiene |

> A useful sanity check: **if the inventory has no risk rating column, the institution has an asset list, not a governance tool.** An inventory that does not drive differentiated control requirements serves no governance purpose.

### How to assess inventory completeness

🔴 **MUST-KNOW — this is the highest-value technique in the whole audit.**

You cannot prove completeness by examining the inventory. You must find AI *outside* it. Use independent populations:

| Source | What to extract | What it catches |
|---|---|---|
| **Accounts payable / corporate cards** | 12 months of spend filtered for known AI vendors and generic terms ("AI", "ML", "copilot", "assistant", "analytics") | Shadow SaaS AI purchased departmentally |
| **Cloud billing** | Line items for AI/ML services (Azure OpenAI, Bedrock, Vertex, SageMaker, Databricks ML) across all subscriptions | AI built by teams outside central IT |
| **Web proxy / CASB logs** | Traffic to AI service domains; volume by department | Employee use of public GenAI tools |
| **Vendor / contract register** | All contracts containing AI, ML, model, algorithm, automation terms | Contracted AI capability |
| **Top 20 critical applications** | Product documentation review or a direct question to each vendor manager: *does this product include AI/ML features?* | 🔴 **Embedded AI — the most-missed category** |
| **Architecture repository / CMDB** | Components tagged as model serving, inference, ML pipeline | Internally built AI |
| **Job titles in HR data** | Data scientists, ML engineers — then ask what they have built | Undocumented internal models |
| **Project/change portfolio** | Initiatives with AI in scope over 24 months | Delivered-but-unregistered systems |
| **Department head attestation** | A short, non-punitive survey | Self-declared shadow AI |

**Report the result as a reconciliation:**

> *"Management's inventory listed 23 AI systems. Audit identified a further 18 through independent sources, including 9 AI features embedded within purchased applications. The inventory is approximately 56% complete. Because risk assessment, validation and monitoring requirements are all triggered by inventory registration, 18 systems are currently outside all AI governance controls."*

That single paragraph is often the most important sentence in the report — and no AI expertise was required to produce it.

---

## Step 3 — Risk classification

### A practical scoring model

Score each dimension 1–5, apply the weighting, and band the total. Adjust weights to the institution's risk appetite — but agree them with the Head of IT Audit *before* scoring, not after.

| # | Dimension | Weight | Score 1 (low) | Score 5 (high) |
|---|---|---|---|---|
| 1 | **Customer impact** | 20% | No customer effect (internal analytics) | Directly determines a customer outcome (credit decline, claim denial, account closure) |
| 2 | **Degree of automation** | 15% | Advisory only; human decides independently | Fully automated; no human in the decision |
| 3 | **Regulatory exposure** | 15% | No regulated process | Feeds a regulated outcome (credit, AML, capital, conduct, e-KYC) |
| 4 | **Financial impact** | 10% | Negligible | Material P&L, capital or provisioning effect |
| 5 | **Data sensitivity** | 10% | Public / aggregated internal data | Sensitive personal data (incl. biometric) or customer information under FSA s.134 |
| 6 | **Explainability** | 10% | Fully interpretable; reasons available | Opaque; cannot explain individual decisions |
| 7 | **Criticality / resilience** | 10% | Failure is an inconvenience | Supports a critical business service; failure stops customer service |
| 8 | **Third-party dependency** | 10% | Fully internal | Critical dependence on an external model with limited transparency or substitutability |

**Bands:** ≥3.5 = **High** · 2.0–3.49 = **Medium** · <2.0 = **Low**

### Mandatory escalation overrides
Regardless of the weighted score, rate **High** if any of the following is true — these are non-negotiable:
- It makes a **solely automated decision with a significant effect on a customer**
- It processes **biometric data** for identity verification
- It feeds **regulatory capital, IFRS 9 ECL, or AML/CFT suspicious activity detection**
- It supports a **critical business service** with no tested fallback
- It has **direct, unreviewed customer-facing output** (e.g. a public chatbot giving product information)

### What the rating drives

| | **High** | **Medium** | **Low** |
|---|---|---|---|
| Risk assessment | Full, with 2nd line challenge | Standard, 2nd line review | Self-assessment |
| Validation | Independent validation by a separate function | Independent review, proportionate scope | Peer review |
| Approval authority | AI/Model Risk Committee or Board committee | Senior management forum | Business owner + Technology owner |
| Monitoring | Monthly, with fairness monitoring | Quarterly | Annual review |
| Re-validation | Annual | Every 2 years | On material change |
| Audit coverage | Every cycle | Rotational | Population-level testing only |

### Why risk-based scoping is non-negotiable

- **Resources.** 40–50 use cases cannot all be deep-dived. Attempting it produces thin, low-value coverage everywhere.
- **Proportionality.** Applying credit-model rigour to a meeting-notes summariser destroys the credibility of the governance process and pushes business teams into the shadows.
- **Defensibility.** If something goes wrong in a system you did not audit, a documented risk-based rationale is your professional protection. "We didn't get to it" is not.
- **It tests the institution's own thinking.** Comparing your independent ratings to management's is itself one of the most informative tests in the audit. Systematic divergence tells you the risk assessment control does not work — and that finding affects all 50 systems, not the 8 you tested.

---

## Step 4 — Sampling from 40–50 use cases

Select **8–10** for detailed testing. Not random — **stratified and judgemental**, with documented rationale.

### Selection framework

| Layer | Selection basis | Count |
|---|---|---|
| **1. Mandatory inclusion** | Every system meeting an escalation override (automated customer decision, biometric, capital/AML, critical service). If there are more than 4, pick the highest-impact 4 | 3–4 |
| **2. Risk coverage** | Highest-scoring remaining High-risk systems not already selected | 1–2 |
| **3. Type coverage** | Ensure at least one of each: classical ML, GenAI, third-party/vendor AI, embedded AI, internally developed | 2–3 |
| **4. Governance-path coverage** | At least one that went through governance cleanly, and **at least one that did not** (found through shadow AI discovery). The contrast is highly informative | 1–2 |
| **5. Judgemental / wildcard** | One selected on auditor judgement: a system with a recent incident, high complaint volume, a recent change, a new vendor, or an owner who was evasive in interview | 1 |

### Worked example — a bank with 47 use cases

| # | Use case | Layer | Rationale |
|---|---|---|---|
| 1 | Retail credit scoring model | 1 | Direct customer decision, regulated outcome, high volume |
| 2 | AML transaction monitoring (ML component) | 1 | Regulatory exposure; supervisory interest |
| 3 | e-KYC facial recognition | 1 | Biometric (sensitive personal data); existing BNM e-KYC requirements; third-party |
| 4 | Card fraud detection model | 1 | Critical business service; financial impact; customer friction |
| 5 | Customer service chatbot | 2/3 | Direct customer-facing GenAI output; conduct risk; hallucination |
| 6 | Microsoft 365 Copilot (enterprise-wide) | 3 | GenAI at scale across all staff; data leakage; RAG entitlement risk |
| 7 | Trade finance document processing | 3 | Embedded/third-party AI; prompt injection via documents; operational reliance |
| 8 | Collections prioritisation model | 3 | Internally developed; customer impact; fairness exposure |
| 9 | CRM lead-scoring feature (embedded) | 4 | Found via shadow AI discovery; never went through governance |
| 10 | Insurance claims triage model | 5 | Judgemental — selected due to a spike in complaints in the last quarter |

**Coverage check:** Does every one of the 10 audit domains get tested by at least two of these use cases? If a domain is only covered once, either add a use case or test that domain at population level instead.

### Testing depth by layer
Not every selected use case needs equal depth.
- **Layers 1–2 (4–6 cases):** full lifecycle walkthrough, all domains, specialist support where needed
- **Layers 3–4 (3–4 cases):** targeted testing of the 3–4 domains that use case is best placed to evidence
- **Layer 5 (1 case):** focused on the specific concern that drove selection

### Population-level testing — do this alongside sampling
Some controls should be tested across the **entire** population, not a sample, because the data is cheap to obtain:
- Inventory field completeness (named owners, risk ratings, validation dates) — test all 47
- Risk assessments completed — test all 47 for existence
- Approval records — test all High-risk systems
- Access to AI platforms — test the full user population, not a sample

Combining full-population testing of cheap attributes with deep sampling of expensive ones gives far better coverage than either alone. **Say so in the report** — "47 of 47 systems tested for X" is a much stronger statement than "10 systems sampled."

---

*Next: [05 — Audit Domains & IT Audit Linkage](05-Audit-Domains-and-IT-Audit-Linkage.md)*
