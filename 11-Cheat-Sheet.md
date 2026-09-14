# 11 — AI Governance Audit Cheat Sheet

*One page for quick revision. Print it.*

---

## 10 AI GOVERNANCE CONCEPTS

| # | Concept | One line |
|---|---|---|
| 1 | **AI Governance** | Accountability, policy, process and control over which AI is used, how, by whom, and within what risk appetite |
| 2 | **Responsible AI** | The outcome principles — transparency, accountability, fairness, privacy, robustness. Governance is the machinery that delivers them |
| 3 | **AI lifecycle** | Idea → Risk Assess → Design → Data → Build/Buy → Validate → Approve → Deploy → Monitor → Change → Retire |
| 4 | **AI inventory** | The register of every AI system, including embedded and third-party. You cannot govern what you have not listed |
| 5 | **Risk tiering** | Rating that drives proportionate validation, approval authority and monitoring. Without it, governance is either unusable or useless |
| 6 | **Human oversight** | In-the-loop (human decides) / on-the-loop (human supervises) / out-of-the-loop (fully automated) |
| 7 | **Model Risk Management** | Independent technical validation of a specific model. AI governance must extend it, not duplicate or bypass it |
| 8 | **Three lines for AI** | 1st: build and own · 2nd: challenge and validate · 3rd: independent assurance |
| 9 | **Shadow AI** | AI in use outside governance. The default state in most institutions in 2026 |
| 10 | **Proportionality** | Match control intensity to impact. Over-controlling low-risk AI drives the business underground |

---

## 10 KEY AI RISKS

| # | Risk | The one-sentence version |
|---|---|---|
| 1 | **Shadow AI** | AI in production that no governance control has ever touched |
| 2 | **Bias / unfair outcomes** | Systematically worse results for a group — often via a proxy like postcode, with nobody intending it |
| 3 | **Model drift** | Silent degradation as the world changes while the model does not |
| 4 | **Lack of explainability** | Cannot tell a customer, the Ombudsman or BNM why the decision was made |
| 5 | **Hallucination** | GenAI producing fluent, confident, wrong content into a regulated process |
| 6 | **Data leakage** | Customer or confidential information leaving via an AI tool — FSA s.134 and PDPA exposure |
| 7 | **Prompt injection** | Untrusted content (especially an uploaded document) carrying instructions the model obeys |
| 8 | **Over-reliance / automation bias** | The designed human control decaying into a click |
| 9 | **Third-party opacity** | Vendor trains on your data, changes the model without notice, and you cannot exit |
| 10 | **Data provenance failure** | Cannot say where training data came from, or whether you had the right to use it |

---

## 10 EXPECTED CONTROLS

| # | Control |
|---|---|
| 1 | **Board-approved AI policy** with mandatory requirements, named roles, prohibited uses and approval authorities |
| 2 | **Complete AI inventory** with named individual owners, covering embedded and third-party AI |
| 3 | **Mandatory risk assessment and tiering** before build or buy, with 2nd line challenge |
| 4 | **Independent validation** before approval, proportionate to tier, with documented limitations |
| 5 | **Approval by an authorised forum** with a complete package and documented conditions |
| 6 | **Data provenance, quality assessment, lawful basis and DPIA** before training data is used |
| 7 | **Fairness threshold defined in advance**, tested independently, monitored over time |
| 8 | **Effective human oversight** — information, authority, time, training; override rate monitored |
| 9 | **Ongoing monitoring with pre-set thresholds** and a documented response to every breach |
| 10 | **AI assets under change control** — including models, training data, **prompts**, thresholds and vendor model updates |

---

## 5 FRAMEWORKS / REGULATORY REFERENCES *(Malaysia, Sept 2026)*

| Reference | Status | Use it for |
|---|---|---|
| ⚖️ **BNM RMiT** (revised Nov 2025) | **Mandatory policy document** | Every hard finding on access, change, cloud, third party, resilience, incidents. *An AI system is a technology system* |
| ⚖️ **PDPA 2010 (as amended 2024)** + **JPDP guidelines on DPIA, Automated Decision-Making & Profiling, Data Protection by Design** (2026) | **Mandatory law + regulator guidelines** | Personal data use, DPIAs, profiling, automated decisions, transparency, human review |
| 🏛️ **AI Governance Framework** — AICB CRO Forum, BNM-supported, ABM-endorsed (2025) | **Industry framework — voluntary** | The expected-practice benchmark. Principles: transparency, accountability, fairness, privacy, robustness |
| 📘 **BNM Discussion Paper on AI in the Malaysian Financial Sector** (5 Aug 2025) | **Discussion paper — NOT binding** | Direction of travel. Recommendations only, never criteria |
| 📗 **NIST AI RMF** *or* **ISO/IEC 42001** — pick one | **Voluntary standard** | Structuring the audit programme. GOVERN/MAP/MEASURE/MANAGE, or a management-system structure |

**Also mandatory and often missed:** FSA 2013 s.134 (customer secrecy) · BNM Outsourcing · BNM e-KYC PD (Apr 2024) · Fair treatment of financial consumers · AML/CFT · capital adequacy model validation.

---

## 5-STEP AUDIT METHODOLOGY

> **0. Position** — tier the criteria, define what counts as AI
> **1. Understand** — map the landscape, build an independent inventory *(⅓ of the effort)*
> **2. Scope & Risk Assess** — rate the population, select 8–10 for depth
> **3. Assess Design** — would the controls work if they operated?
> **4. Test Operation** — sample, observe, reperform
> **5. Report & Follow Up** — consequence-led, themed, criteria-tiered, quantified
> **6. Continuous Monitoring** — quarterly inventory reconciliation; observer seat at the AI forum

---

## 5 PRINCIPLES FOR AUDITING AI

1. **Audit the governance system, not just individual models.** Three deep dives tell the Board nothing about the other forty-four.
2. **Audit whether validation happened — do not perform validation.** State this boundary explicitly in the report.
3. **Anchor hard findings on mandatory criteria.** RMiT and the PDPA apply to AI today. Label every finding by tier.
4. **Lifecycle, not go-live.** A model can pass every control at launch and be unfit eleven months later with nothing changed.
5. **Push up the evidence hierarchy.** Extract it yourself, observe it, reperform it. "The team confirmed they monitor it" is not a conclusion.

---

## COMMON MISTAKES NEW AI AUDITORS MAKE

| ❌ Mistake | ✅ Instead |
|---|---|
| Trying to become a data scientist first | 85% of the programme is access, change, third-party and governance testing you already do |
| Citing voluntary guidance as a regulatory requirement | Tier every criterion. You will lose the closing meeting otherwise |
| Auditing three models deeply and ignoring the other forty-four | Test cheap attributes across the whole population; deep-dive 8–10 |
| Accepting the AI inventory as complete | Triangulate against AP, cloud billing, proxy logs, contracts, and an embedded-AI sweep |
| Forgetting embedded AI in purchased products | The CRM lead scorer, the HR CV screener, the contact centre sentiment engine — consistently the most-missed category |
| Treating GenAI as a separate audit silo | GenAI is an overlay on access, change and third-party audit — plus a few specific controls |
| Ignoring prompts as configuration items | Prompt change history vs change records is one of the highest-yield tests available |
| Concluding "human-in-the-loop exists" from documentation | Pull the override rate and the decision timestamps. 0.3% and four seconds tells the real story |
| Accepting a contract as evidence a setting is enabled | Get the tenant configuration screenshot |
| Filing a SOC 2 report without reading the CUECs | Those are the controls the vendor says *you* must operate |
| Writing findings in technical language | "The model exhibits distributional drift" is useless. "We may be missing fraud and nobody would know" gets a decision |
| Raising eight separate findings for one systemic gap | Group by theme; report root cause, not symptoms |
| Only recommending "strengthen the policy" for shadow AI | Block the unapproved path **and** provide a convenient sanctioned alternative |
| Omitting the scope limitation paragraph | It is what makes the rest of the report defensible |
| Waiting for BNM to issue AI regulation before starting | The estate is growing faster than the audit cycle, and the PDPA guidelines are already in force |

---

## THE FIVE THINGS THAT ARE GENUINELY NEW

Everything else is IT audit you already know.

> **Fairness** · **Explainability** · **Drift detection** · **Training-data provenance** · **Human oversight effectiveness**

---

## IF YOU ONLY DO FIVE TESTS

1. **Inventory triangulation** — AP, cloud billing, proxy, contracts, embedded-AI sweep
2. **Prompt change history** vs formal change records
3. **Monitoring breaches** traced to documented responses
4. **RAG entitlement test** — restricted account, restricted document
5. **Override rate + decision timestamps** on a human-in-the-loop control

None requires a data scientist. All five reliably produce findings.

---

*Next: [12 — Critical Review](12-Critical-Review.md)*
