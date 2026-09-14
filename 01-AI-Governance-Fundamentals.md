# 01 — AI Governance Fundamentals

> Written for someone who already understands IT General Controls, cybersecurity audit and technology risk, but has limited AI exposure.

---

# PART 1 — What an IT Auditor Needs to Know About AI

## 1.1 The one distinction that matters

🔴 **MUST-KNOW**

In traditional IT audit, you audit a system whose behaviour was **written down by a human**. You can read the specification, read the code, and determine what the system *should* do. The control question is: *does the system do what the specification says?*

In AI audit, the system's behaviour was **derived from data**, not written down. Nobody can point to a line of code that says "reject this loan application." The control question changes to: *was the process that produced this behaviour sound, and is the resulting behaviour still acceptable?*

That single shift explains nearly every AI-specific control you will ever test.

| | Traditional system | AI/ML system |
|---|---|---|
| Where behaviour comes from | Human-written logic | Learned from training data |
| Can you read the rules? | Yes | Often no |
| Testing | Expected result vs actual result | Statistical performance across a population |
| Does it change on its own? | No — only via change management | Yes — performance degrades as reality shifts |
| Same input, same output? | Always | Usually for ML; **often not** for Generative AI |
| Root cause of a defect | A bug in code | A flaw in data, objective, or assumptions |
| Key new evidence | Code, config, test scripts | Data lineage, training records, validation reports, monitoring dashboards |

---

## 1.2 The technology ladder — explained without mathematics

Think of these as five rungs. Each rung adds capability *and* removes a form of transparency you used to rely on.

### Rung 1 — Traditional software
Code does exactly what it was told. A CASA interest calculation. Deterministic, testable, auditable line-by-line.

### Rung 2 — Rule-based / expert systems
Still human-written, but the logic expresses expert judgement as explicit rules.

> *"IF transaction > RM25,000 AND counterparty country is high-risk AND customer is not a corporate → raise AML alert."*

**Important for auditors:** a legacy rules-based AML transaction monitoring engine is **not AI**. Many banks call it AI. It isn't. It is auditable exactly like any other application — you can read and test every rule. Watch for this mislabelling when you review the AI inventory; it inflates the inventory and distracts from real AI.

### Rung 3 — Machine Learning (ML)
The system is shown many historical examples and infers the pattern itself.

> Show a model 500,000 past loans, each labelled "defaulted / did not default." The model works out which combinations of attributes are associated with default, and scores new applicants.

Nobody wrote the rules. The model discovered statistical associations. Three consequences you must internalise:

- **It inherits the past.** If historical lending was biased, the model learns the bias and industrialises it.
- **It decays.** The world changes (interest rate cycle, a pandemic, a new product); the learned pattern goes stale. This is **model drift**.
- **It is probabilistic.** The output is a score or a likelihood, not a truth. "87% likely to be fraud" is not "this is fraud."

**Common ML types in a Malaysian bank:**
| Type | Plain meaning | Typical banking use |
|---|---|---|
| Classification | Sort into categories | Fraud / not fraud; approve / decline |
| Regression | Predict a number | Expected loss, customer lifetime value |
| Clustering | Group similar things | Customer segmentation |
| Anomaly detection | Flag the unusual | AML transaction monitoring, insider threat |
| Computer vision | Interpret images | e-KYC facial matching, cheque/document capture |
| NLP | Interpret language | Complaint categorisation, document extraction |

### Rung 4 — Artificial Intelligence (AI)
An umbrella term, not a technology. In practice, "AI" in a bank means *ML plus anything built on it*. **Do not let the umbrella term into your audit scope definition** — it is unauditably vague. Scope on *systems and use cases*, not on "AI."

### Rung 5 — Generative AI and Large Language Models (LLMs)
A **Large Language Model** is an ML model trained on enormous volumes of text to predict what text plausibly comes next. **Generative AI** is the broader category of models that produce new content — text, images, code, audio.

🔴 **MUST-KNOW — why GenAI breaks your existing audit assumptions:**

| Property | Audit consequence |
|---|---|
| **Non-deterministic** — same prompt can give different answers | You cannot test by re-running and comparing to an expected result |
| **Fluent but not factual** — it optimises for plausible text, not true text | "Hallucination" is a *design characteristic*, not a bug to be patched out |
| **No inherent knowledge boundary** — it will answer anything | Needs enforced guardrails, not trust |
| **The "code" is now natural language** — prompts and system instructions | Prompts are a **change-managed configuration item**. Most banks do not treat them that way. This is a reliable finding. |
| **Input is an attack surface** — user text can contain instructions | **Prompt injection**: untrusted input becomes executable instruction |
| **Usually third-party hosted** (Azure OpenAI, AWS Bedrock, Google Vertex, Microsoft 365 Copilot) | Every third-party, cloud and data-residency control you know already applies |

**RAG (Retrieval-Augmented Generation)** 🟡 — the standard bank pattern. The LLM is not asked to "know" anything; it is given relevant internal documents at query time and asked to answer *from those documents*. Audit-relevant because the access controls on the retrieved document store become the real control. If a staff member can retrieve a document through the chatbot that they could not open in SharePoint, you have an entitlement failure — and that is a classic IAM finding, not an AI finding.

**Agentic AI** 🟡 — an LLM permitted to take actions (call APIs, update records, send messages) rather than just produce text. Emerging in banks in 2026 for operations automation. The audit lens is **privileged access management**: what identity does the agent run as, what can it do, what is logged, and what requires human confirmation? Treat an AI agent as a *non-human privileged account*.

---

## 1.3 What is AI Governance?

🔴 **MUST-KNOW**

> **AI Governance** is the structure of accountability, policy, process and control through which an organisation decides *which* AI it will use, *how* it will build or buy it, *who* is answerable for its outcomes, and *how* it keeps those outcomes within its stated risk appetite across the full life of the system.

**In audit language:** AI Governance is the control environment and entity-level controls for a new asset class.

### Purpose

1. **Accountability** — a named human owns every AI outcome. BNM's Governor put this directly in July 2026: *"responsibility cannot be delegated to an algorithm."*
2. **Visibility** — the institution knows what AI it has. You cannot govern an inventory you do not possess.
3. **Proportionality** — a chatbot that answers branch opening hours should not face the same gate as a model that declines credit.
4. **Risk containment** — AI risk is kept inside board-approved appetite.
5. **Enablement** — a clear path to approval so business units stop building AI in the shadows.

### Why organisations need it
Because AI decisions are (a) made at scale, (b) hard to explain after the fact, (c) built on data of uncertain quality, and (d) degrade silently. Any one of those is manageable. Together they mean a single bad model can produce tens of thousands of defective outcomes before anyone notices.

### Why *banks* need it more

| Driver | Why it bites harder in a bank |
|---|---|
| Regulated outcomes | Credit, AML and market conduct outcomes are directly supervised by BNM |
| Customer detriment at scale | One biased scorecard can affect an entire segment of Malaysians |
| Fiduciary and secrecy duties | FSA 2013 s.134 customer information secrecy applies to data flowing into any AI tool |
| Capital and provisioning | Models feed IFRS 9 ECL and capital calculations |
| Systemic trust | Confidence in the banking system is the product |
| Existing model governance | Banks already have MRM for credit/market risk models — AI must plug into it, not bypass it |

---

## 1.4 AI Governance vs AI Risk Management vs Model Risk Management

🔴 **MUST-KNOW — this comes up constantly and people conflate all three.**

| | **AI Governance** | **AI Risk Management** | **Model Risk Management (MRM)** |
|---|---|---|---|
| Question answered | *Who decides, under what rules?* | *What could go wrong, and what are we doing about it?* | *Is this specific model fit for its stated purpose?* |
| Scope | Whole institution | Per use case / portfolio | Per model |
| Typical owner | Board / AI or Technology Committee; 1st + 2nd line | Risk Management function (2nd line) | Model Validation / Model Risk (independent 2nd line) |
| Output | Policy, standards, RACI, approval gates, inventory, risk appetite | Risk assessments, risk register, treatment plans, KRIs | Validation report, model approval, limitations, ongoing performance review |
| Audit lens | Entity-level / governance controls | Risk & control self-assessment quality | Independent challenge quality |
| IT audit analogy | Your Information Security Policy + Security Steering Committee | Your cyber risk assessment process | Independent penetration test of one application |

**The relationship:** Governance is the *frame*. Risk management is the *process that runs inside the frame*. MRM is a *deep technical assurance activity for one category of asset within that process*.

🔴 **Critical nuance for a Malaysian bank:** MRM already exists for credit scorecards, IFRS 9 ECL, market risk VaR and capital models — it is mature and regulated. AI Governance must **extend** it, not duplicate it. Two failure modes you will see in practice:

- **Gap:** A GenAI chatbot is "not a model," so it escapes MRM entirely and nothing else picks it up.
- **Overreach:** A marketing propensity model is pushed through full IFRS 9-grade validation, the queue jams, and the business goes around the process.

A good AI governance framework routes each use case to proportionate assurance. **Test whether that routing rule exists and is applied** — it is one of the highest-value tests in this whole pack.

---

## 1.5 The analogy to remember

🔴 **Use this when explaining AI Governance to a board or a non-technical audit committee.**

> **Think of AI as a new category of driver on the bank's roads.**
>
> - **AI Governance** is **JPJ and the Highway Code** — who is licensed to drive what, on which roads, with what insurance, and who is legally responsible when something goes wrong. It is set once, applies to everyone, and does not depend on the vehicle.
> - **AI Risk Management** is **journey planning and defensive driving** — before this particular trip, what could go wrong on this route, in this weather, with this cargo, and what precautions do we take?
> - **Model Risk Management** is **Puspakom inspection** — a qualified inspector opens the bonnet on one specific vehicle and certifies it roadworthy for a defined period and purpose.
> - **Human oversight** is **keeping your hands near the wheel.** The car may be driving, but you are still the driver in the eyes of the law.
> - **Model drift** is **the tyres wearing down.** Nothing broke. Nobody changed anything. It is simply less safe than it was six months ago, and only periodic inspection will tell you.
> - **Shadow AI** is **unlicensed drivers using the company car park.**
>
> An accident is never excused by "the car decided to do that."

---

# PART 2 — The AI Lifecycle

🔴 **MUST-KNOW — this is your audit programme's backbone.**

The lifecycle is why AI audit is *not* a point-in-time application review. A model can pass every control at deployment and be unfit for purpose eleven months later without a single change being made to it.

```
Idea / Use Case → Risk Assessment → Design → Data Preparation →
Development / Procurement → Testing & Validation → Approval →
Deployment → Monitoring → Change / Retraining → Retirement
```

**Where it maps to what you already audit:**

| Lifecycle stage | Your existing equivalent |
|---|---|
| Idea → Design → Development → Testing → Approval → Deployment | SDLC audit |
| Data Preparation | Data governance / data quality audit |
| Testing & Validation | UAT + security testing + (new) independent model validation |
| Monitoring | Logging & monitoring audit + (new) performance/drift monitoring |
| Change / Retraining | Change management audit |
| Retirement | Decommissioning / records retention |

The three stages with **no** clean traditional equivalent — and therefore where new findings concentrate — are **Data Preparation**, **Validation (fairness/explainability)** and **Monitoring (drift)**.

---

## Stage 1 — Idea / Use Case Definition

**Purpose:** Decide whether the institution should build this at all.

| | |
|---|---|
| **Key risks** | AI applied where it is inappropriate (e.g. a probabilistic model driving a decision that must be deterministic and explainable); business problem not defined, so success cannot be measured; solution chosen before the problem; prohibited or reputationally unacceptable use case |
| **Key controls** | Documented use case intake form; defined prohibited-use list (e.g. no fully automated adverse credit decisions without human review; no AI-driven pricing on protected characteristics); business case with measurable success criteria; initial owner assignment at intake |
| **Stakeholders** | Business Owner, Head of Data/AI, Innovation, Risk (2nd line) |
| **Evidence to request** | Use case intake register; completed intake forms for sampled use cases; AI policy section listing prohibited/restricted uses; approval of business case |
| **Example audit test** | Select 10 AI systems from production. Trace each back to an intake record. **Any production AI system with no intake record is a governance bypass — report it.** Separately, confirm the prohibited-use list exists and is specific enough to be enforceable ("must be ethical" is not) |

---

## Stage 2 — Risk Assessment & Classification

**Purpose:** Route the use case to the right level of assurance.

| | |
|---|---|
| **Key risks** | No risk assessment performed; self-assessed by the business with no independent challenge; risk rating gamed downward to avoid governance; criteria so vague that ratings are inconsistent; GenAI treated as low-risk because "it only drafts text" |
| **Key controls** | Mandatory, standardised AI risk assessment before build/buy; defined rating criteria (customer impact, automation degree, data sensitivity, explainability, regulatory exposure, third-party dependence); 2nd line review and challenge of ratings; rating drives mandatory downstream requirements (validation depth, approval authority, monitoring frequency) |
| **Stakeholders** | Business Owner, Risk Management, Compliance, Data Protection Officer, Model Risk |
| **Evidence to request** | AI risk assessment methodology; completed assessments; evidence of 2nd line challenge (comments, versions, sign-off); DPIA where personal data is processed; mapping of risk tier → required controls |
| **Example audit test** | Independently re-rate 5 sampled use cases using the bank's own criteria. Compare to the bank's rating. **Systematic under-rating is a high-grade finding**, because every downstream control is calibrated off this rating. Also check that at least one assessment was challenged and changed — a 2nd line function that has never disagreed is not exercising challenge |

---

## Stage 3 — Design / Solution Architecture

**Purpose:** Decide how it will work, where it will run, and what a human's role will be.

| | |
|---|---|
| **Key risks** | Human oversight not designed in (bolted on later, or absent); no fallback if the AI is unavailable or wrong; architecture sends confidential data outside approved boundaries; explainability requirement identified only after the model is built (by which point it is usually too late); no defined performance threshold |
| **Key controls** | Solution design document with architecture review; defined human-in-the-loop / human-on-the-loop / human-out-of-the-loop decision, approved at the right level; defined fallback and degradation procedure; data flow diagram approved by Data Protection Officer and Information Security; explainability requirement set *before* model selection; documented acceptance thresholds (accuracy, false positive/negative tolerance) |
| **Stakeholders** | Solution Architect, Information Security, DPO, Business Owner, Operations |
| **Evidence to request** | Design documents; architecture review board minutes; data flow diagrams; security design review; documented human oversight model; agreed performance thresholds |
| **Example audit test** | For a credit scoring or fraud use case, obtain the design document and confirm the human oversight model is explicitly stated and *matches what actually happens in operations*. Walk the floor: interview two front-line users and check whether they can, and do, override. **A documented "human-in-the-loop" that operationally means clicking Accept on 100% of recommendations is an oversight failure in substance** |

---

## Stage 4 — Data Preparation

**Purpose:** Assemble the data the model learns from. 🔴 **This is where most AI failures are actually born.**

| | |
|---|---|
| **Key risks** | Training data not representative of the population the model will serve; poor quality/incomplete data; personal or sensitive data used without lawful basis or beyond stated purpose; no data lineage — cannot say where training data came from; proxy variables that encode protected characteristics (postcode as a proxy for ethnicity; name as a proxy for race); data leakage (information available at training that will not exist at decision time, producing a model that tests brilliantly and fails in production); customer information under FSA s.134 used without a permitted basis; third-party/scraped data of unknown provenance |
| **Key controls** | Documented data sourcing and lineage; data quality assessment against defined dimensions (completeness, accuracy, timeliness, consistency, validity); approved lawful basis and purpose-limitation check (PDPA); DPIA for high-risk processing; data classification applied before use; review for prohibited and proxy variables; representativeness analysis across relevant segments; access controls on training datasets; data retention and disposal rules |
| **Stakeholders** | Chief Data Officer / Data Governance, Data Owners, DPO, Compliance, Information Security |
| **Evidence to request** | Data dictionary and lineage documentation; data quality reports; DPIA; lawful basis assessment; list of variables used *and excluded, with reasons*; approval from data owner to use data for this purpose; dataset access control list |
| **Example audit test** | For a sampled model, obtain the variable list. Confirm (a) a documented review for prohibited/proxy variables took place and (b) the data owner approved use of that data for *this* purpose, not merely for the system it originated in. Reconcile the variable list to the data dictionary — **undocumented variables are a lineage failure**. Then test dataset access: pull the ACL and confirm it is restricted, reviewed and consistent with the data's classification. *This last test is a pure IAM test — you can run it today with no AI knowledge* |

---

## Stage 5 — Development / Procurement

**Purpose:** Build it, or buy it.

| | |
|---|---|
| **Key risks** | **Build:** no version control on model/code/data; development in production; no segregation of duties between developer and approver; undocumented experimentation. **Buy:** vendor due diligence not performed or not AI-specific; contract silent on data use, model changes, IP, audit rights and exit; vendor may retrain on the bank's data; unknown open-source model provenance and licensing; concentration risk on one cloud AI provider |
| **Key controls** | Source control for code, model artefacts, prompts and configuration; segregated dev/test/prod environments; SoD between build, approve and deploy; secure coding and dependency scanning (AI supply chain: models, libraries, datasets from public repositories); AI-specific vendor due diligence; contractual clauses on data use/retention/training, model change notification, performance SLAs, audit and regulator access rights, sub-processors, data location, exit assistance; outsourcing assessment where BNM's outsourcing requirements apply |
| **Stakeholders** | Data Science / Engineering, IT, Procurement, Legal, Third-Party Risk, Information Security, Compliance |
| **Evidence to request** | Repository access and commit history; environment topology; SoD matrix; vendor due diligence file; executed contract and schedules; model card / vendor documentation; software bill of materials; open-source licence review |
| **Example audit test** | Obtain the contract for a third-party AI service and test it against a clause checklist: does the vendor train on bank data? Where is data processed and stored? Must they notify model changes? Are there audit rights extending to BNM? What happens at exit? **A contract that is silent on vendor retraining using bank data is a finding with direct FSA s.134 and PDPA implications.** Second test: confirm model artefacts are version-controlled — ask to see the exact model binary currently in production and trace it to a repository version and an approval |

---

## Stage 6 — Testing & Validation

**Purpose:** Prove it works, safely, before anyone relies on it. 🔴 **This is where governance assurance and technical validation must be clearly separated.**

| | |
|---|---|
| **Key risks** | Validation performed by the model developer (no independence); testing only on data the model was trained on; no fairness testing across relevant segments; no adversarial/security testing; performance measured only in aggregate, hiding poor performance in specific segments; no stress or edge-case testing; for GenAI, no testing of guardrails, jailbreaks or hallucination rate; validation report has no stated limitations |
| **Key controls** | Independent validation by a party other than the developer, proportionate to risk tier; validation against a hold-out dataset the model has never seen; documented performance metrics vs pre-agreed thresholds; fairness/disparate-impact testing across relevant segments; explainability assessment; security testing (including prompt injection and data exfiltration testing for GenAI); documented limitations and conditions of use; UAT sign-off by the business owner |
| **Stakeholders** | Model Validation / Model Risk (independent), Business Owner, Information Security, Compliance, Internal Audit (as observer) |
| **Evidence to request** | Validation report with author and reporting line; test data description; performance results vs thresholds; fairness test results; explainability assessment; security test report; UAT sign-off; documented limitations; remediation of validation findings before go-live |
| **Example audit test** | 🔴 **The defining test of this whole discipline.** Do *not* re-perform the statistics. Instead test the **governance of validation**: (1) Was the validator independent of the developer? Check reporting lines and named individuals. (2) Was validation completed *before* approval? Compare dates — validation reports dated after go-live are common and are a clear finding. (3) Were the pre-agreed thresholds met, and if not, who accepted the exception and did they have authority? (4) Were validation findings closed before deployment or carried as open risk with approval? (5) Are limitations documented and communicated to users? See [07-Specialist-Reliance](07-Specialist-Reliance.md) |

---

## Stage 7 — Approval

**Purpose:** A named, authorised human accepts the risk.

| | |
|---|---|
| **Key risks** | Approved by someone without delegated authority; approval based on incomplete information (validation not seen, risks not disclosed); no conditions attached to approval; approval implicit ("nobody objected"); no re-approval requirement or expiry |
| **Key controls** | Defined approval authority matrix tiered by risk rating; approval forum with documented terms of reference, quorum and minutes; approval package standard (risk assessment, validation report, limitations, monitoring plan, fallback); conditions and expiry/re-approval date attached; register of approvals |
| **Stakeholders** | AI/Technology Governance Committee, Model Risk Committee, Board or delegated committee for high-risk cases, CRO, CIO |
| **Evidence to request** | Authority matrix; committee ToR and minutes; approval papers; register of approved AI systems with conditions and expiry |
| **Example audit test** | Select 5 high-risk AI systems. For each, trace to the approval record and confirm: approver had authority per the matrix; the approval package contained the validation report and documented limitations; conditions (if any) were subsequently met. **Check the committee minutes for evidence of challenge** — minutes recording only "noted and approved" across every paper indicate a rubber-stamp forum, which is an entity-level control weakness |

---

## Stage 8 — Deployment

**Purpose:** Move it into production safely.

| | |
|---|---|
| **Key risks** | Deployed version differs from the validated version; no rollback plan; excessive production access for data scientists; deployment bypassing standard change management ("it's just a model refresh"); secrets/API keys mishandled; no phased rollout for a high-impact model |
| **Key controls** | Standard change management applies to AI deployments; deployed artefact hash/version reconciled to the approved version; automated deployment pipeline with approval gates; SoD — developers cannot deploy to production; rollback procedure tested; phased/canary rollout for high-risk changes; production access restricted and logged |
| **Stakeholders** | IT Operations, Change Management, Data Science, Information Security |
| **Evidence to request** | Change records for AI deployments; CAB minutes; deployment pipeline configuration; production access list for AI platforms; rollback procedure and evidence of test |
| **Example audit test** | 🔴 **Version reconciliation — a simple, powerful test.** Take the model currently serving production decisions. Obtain its version identifier. Trace it to (a) the validation report, (b) the approval record, (c) the change record. **Any break in that chain is a strong finding.** Second test: obtain the list of users with write access to the AI production environment and confirm no data scientist has standing production deployment rights. *This is classic SoD testing — nothing AI-specific required* |

---

## Stage 9 — Monitoring

**Purpose:** Detect degradation before it causes harm. 🔴 **The most commonly weak stage in practice.**

| | |
|---|---|
| **Key risks** | No ongoing performance monitoring — "we validated it at launch"; drift undetected (data drift: inputs change; concept drift: the relationship being predicted changes); thresholds defined but nobody acts on breaches; no monitoring of fairness over time, only at launch; alerts routed to a mailbox nobody reads; GenAI outputs not sampled for quality; no monitoring of usage volume or unexpected use patterns; no override tracking |
| **Key controls** | Defined monitoring plan per model: metrics, thresholds, frequency, owner, escalation; drift detection with defined triggers; periodic performance reporting to a governance forum; recurring fairness monitoring for customer-impacting models; override rate tracking (a spiking override rate is the business telling you the model is failing); GenAI output sampling and quality review; user feedback channel; documented escalation and response |
| **Stakeholders** | Model Owner, Data Science, Risk Management, Operations, IT Operations |
| **Evidence to request** | Monitoring plan; actual monitoring reports for the last 12 months; threshold breach records and what was done; committee packs showing AI performance reporting; override/exception statistics; retraining triggers |
| **Example audit test** | Obtain 12 months of monitoring output for a sampled model. Test for: (a) **existence and continuity** — are there gaps where monitoring simply stopped? (b) **thresholds** — are they defined in advance, or read off the chart after the fact? (c) **action** — select every threshold breach and trace it to a documented response. **Breaches with no recorded response is the single most common AI monitoring finding.** (d) **reporting** — did the governance forum actually receive and discuss this? Check minutes, not just the existence of a dashboard |

---

## Stage 10 — Change / Retraining

**Purpose:** Update the model without silently changing the bank's risk profile.

| | |
|---|---|
| **Key risks** | Retraining treated as "business as usual," escaping change control; automatic retraining pipelines that update production models with no human approval; prompt or system-instruction changes made without any change record; new data introduced without quality or bias assessment; no re-validation after material change; cumulative small changes materially altering behaviour with no single trigger for re-assessment; **vendor changes the underlying model with no notice** |
| **Key controls** | Change policy explicitly covering models, training data, prompts, parameters, thresholds and configuration; materiality criteria defining what triggers re-validation and re-approval; approval required before automated retraining promotes to production; prompts held in version control with approval workflow; re-run of fairness and performance tests after material change; vendor model change notification clause plus a process to assess notified changes; periodic re-validation regardless of change (e.g. annually for high-risk) |
| **Stakeholders** | Change Management, Model Owner, Model Validation, Vendor Management |
| **Evidence to request** | Change policy covering AI assets; change records for AI over the period; prompt version history; retraining logs; re-validation reports; vendor change notifications received and the assessments performed |
| **Example audit test** | 🔴 **Two high-yield tests.** (1) **Prompt change management:** for a GenAI use case, request the change history of the system prompt. Compare to formal change records. **In most institutions in 2026, prompts are edited directly in a console with no change record. This is a reliable, defensible finding — it is unauthorised change to a production control.** (2) **Vendor model change:** ask the vendor manager to produce every model-version change notification from the provider in the last 12 months and the bank's impact assessment of each. **"We weren't notified" and "we didn't assess it" are both findings** — the first is a contract gap, the second a process gap |

---

## Stage 11 — Retirement

**Purpose:** Stop using it, cleanly.

| | |
|---|---|
| **Key risks** | Model decommissioned but still called by a forgotten integration; training data and model artefacts retained beyond the retention period (PDPA); records not retained long enough to reconstruct past decisions when a customer complains or a regulator asks; inventory not updated; vendor retains bank data after contract exit |
| **Key controls** | Decommissioning procedure including dependency check; data and artefact disposal per retention schedule; **retention of decision records and model versions sufficient to explain historical decisions for the statutory/complaint period**; inventory updated; vendor exit — certificate of data deletion, return of data, transition plan |
| **Stakeholders** | Model Owner, IT Operations, Records Management, DPO, Vendor Management |
| **Evidence to request** | Decommissioning records; disposal certificates; updated inventory; vendor exit documentation; retention schedule covering AI artefacts |
| **Example audit test** | Compare the AI inventory to actual production API call logs / platform telemetry. **Systems marked "retired" that are still receiving traffic is a strong finding.** Conversely, test that for a retired customer-impacting model, the bank can still reconstruct and explain a decision it made 18 months ago — if the model version and input data were deleted, the bank cannot answer a complaint or an Ombudsman referral |

---

## 2.1 Lifecycle summary — where findings cluster

From an audit-planning perspective, if your resources are limited, weight your effort here:

| Rank | Stage | Why |
|---|---|---|
| 1 | **Monitoring** | Almost universally weakest; degradation is invisible without it; easy to evidence |
| 2 | **Change / Retraining** | Prompts and retraining routinely bypass change control |
| 3 | **Risk Assessment & Classification** | Miscalibration here breaks every downstream control |
| 4 | **Data Preparation** | Root cause of bias, quality and privacy failures; lineage usually incomplete |
| 5 | **Validation & Approval** | Independence and sequencing failures are easy to prove with dates and names |
| 6 | **Inventory / Intake** | Shadow AI; you cannot govern what you have not listed |

---

*Next: [02 — AI Risk Register](02-AI-Risk-Register.md)*
