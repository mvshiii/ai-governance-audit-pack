# 07 — The Role of Specialists

> The single most important professional judgement in AI audit: knowing where your competence ends, and saying so before fieldwork rather than in the closing meeting.

---

## 7.1 The core distinction

🔴 **MUST-KNOW. Learn this framing and use it verbatim when someone asks whether you are qualified to audit AI.**

| **Auditing whether appropriate validation occurred** | **Personally performing model validation** |
|---|---|
| *Was a validation performed?* | *Is the model's discriminatory power adequate?* |
| *Was the validator independent of the developer?* | *Is the chosen performance metric appropriate for this problem?* |
| *Was it completed before approval and deployment?* | *Is the hold-out sample statistically representative?* |
| *Did it cover the scope the institution's own standard requires?* | *Are the model's statistical assumptions violated?* |
| *Were acceptance thresholds set in advance and met?* | *What should the threshold be?* |
| *Were limitations documented and communicated?* | *Are the stated limitations complete and correct?* |
| *Were findings closed before go-live?* | *Was the remediation technically sufficient?* |
| **This is governance assurance. It is Internal Audit's work.** | **This is technical model validation. It is 2nd line's work, and reviewing its technical adequacy requires a specialist.** |

**The analogy that makes it stick:** when you audit patch management, you do not personally reverse-engineer the vulnerability. You test that scanning ran, that vulnerabilities were identified, prioritised, patched within SLA, and that exceptions were approved by someone with authority. You are auditing the *process*, using evidence the process produces. AI model validation is identical in structure.

**The corollary that protects you:** you can produce a complete, defensible, high-value AI governance audit report **without ever assessing whether a model is statistically sound** — provided you say clearly in the report what you did and did not opine on. See §7.5.

---

## 7.2 What an IT Auditor should confidently assess — alone

No specialist required. This is the majority of the engagement.

| Area | What you assess without help |
|---|---|
| **Governance** | Policy existence, approval, auditability, coverage; forum ToR, quorum, attendance, evidence of challenge; delegated authority; board reporting; risk appetite articulation and measurement |
| **Inventory** | Completeness via independent-source triangulation; field completeness; owner validity; embedded AI discovery |
| **Risk assessment process** | Whether assessments exist, were timely, followed the methodology, were challenged, and whether the rating drove the required downstream controls. **Including independently re-rating using the institution's own criteria** |
| **Approval** | Authority, completeness of the approval package, conditions, expiry, sequencing against validation |
| **Validation governance** | Independence (names and reporting lines), sequencing (dates), completeness against the institution's own standard, threshold pre-agreement, limitations documentation, findings closure, re-validation currency |
| **Access management** | Everything. UAR scope, entitlement extraction, leaver testing, privileged accounts, PAM coverage, MFA, JML, service accounts, RAG entitlement enforcement |
| **Change management** | Everything. Policy scope, change records, prompt version history, retraining approval, SoD, version reconciliation, vendor change assessment |
| **Monitoring governance** | Plan existence and scope, continuity, whether thresholds were pre-set, whether breaches received a response, whether results reached a governance forum |
| **Third-party** | Due diligence adequacy, contract clause review, outsourcing determination, CUEC testing, configuration-versus-contract verification, concentration mapping, exit planning |
| **Incident management** | Taxonomy coverage, incident identification, RCA quality, regulatory notification assessment, trend analysis |
| **Human oversight** | Override rates, timestamp analysis, observation, reviewer interviews, information sufficiency, authority and friction |
| **Explainability in practice** | Whether the requirement was set at design stage; whether reason codes are stored; **whether a front-line officer can actually explain a decision**; whether adverse-action letters give meaningful reasons |
| **Data governance process** | Variable-to-dictionary reconciliation, data owner approval, DPIA existence and DPO review, lineage documentation, retention, training data access controls |
| **Resilience** | Fallback existence and test currency, kill switch, BCP coverage, the reconstruction test |
| **GenAI operational controls** | Blocking effectiveness, tenant configuration, DLP coverage, RAG entitlement testing, prompt log storage and access, output sampling programme existence, permitted-use boundaries, customer disclosure |

> Count them: that is roughly **85% of the audit programme in [05](05-Audit-Domains-and-IT-Audit-Linkage.md) and [06](06-Sample-Audit-Tests.md)**. Do not let anyone — including yourself — tell you that you cannot audit AI without a data science background.

---

## 7.3 Where specialist support is appropriate

| Specialist | Engage them when you need to assess... | Typical form of support | Could you skip them? |
|---|---|---|---|
| **Data Scientist / ML Engineer** | Whether the *method* of validation was technically appropriate; whether the chosen performance metric suits the problem; whether the fairness metric and segment selection were sound; whether a technical explanation of a model's behaviour is credible; whether a monitoring approach would actually detect drift | 2–5 days reviewing sampled validation reports and monitoring designs, producing a written technical opinion you cite in the report | Yes for a first-year governance audit. **No** if you intend to opine on the adequacy of validation quality |
| **Model Validator / Model Risk** | Whether the validation standard itself is fit for purpose; how AI models should map into the existing MRM framework; what constitutes proportionate validation by tier | Consultation during Phase 0 to set criteria; review of your validation-governance conclusions | Usually not — but note the independence issue below |
| **Cybersecurity Specialist** | Adversarial and prompt-injection testing; the technical adequacy of guardrails; model extraction exposure; AI supply chain integrity verification | Joint testing on Tests 12 and 14; or review of the institution's own adversarial test reports | Partially. You can test *whether* testing occurred; assessing *whether it was good enough* needs security specialism |
| **Legal** | Contract clause adequacy; the legal force of the JPDP guidelines; liability allocation with AI vendors; IP exposure from AI-generated content | Review of your contract clause checklist; opinion on criteria tiering where regulatory force is ambiguous | No — get Legal's view on criteria tiering before you write findings |
| **Compliance** | Whether an AI use case engages a specific regulatory obligation; BNM reporting and notification expectations; conduct implications | Consultation in Phase 0 and on specific use cases | No |
| **Privacy / DPO** | Lawful basis adequacy; DPIA sufficiency; ADMP guideline applicability; cross-border transfer assessment | Consultation; review of your privacy findings | No — but be alert to independence: the DPO may be the control owner you are auditing |
| **Business Owner / SME** | What the model actually does in the business process; what a wrong output means operationally; what the fallback looks like in practice | Walkthroughs and observation | No — this is core fieldwork, not specialist reliance |
| **External AI assurance provider** | A full technical model validation review, where the institution has no independent internal capability and Internal Audit needs to opine on validation quality | Co-sourced engagement | Depends on the audit's stated scope |

---

## 7.4 The independence trap

🔴 A specialist you rely on must be independent of the control you are testing.

| Situation | Problem | Resolution |
|---|---|---|
| You ask the bank's data science team to help you assess their own model's validation | They built it. This is not audit evidence | Use Model Validation (if independent) or an external specialist |
| You ask Model Validation to help you assess whether Model Validation is adequate | Self-assessment | Use an external specialist, or scope your conclusion to governance only |
| You ask the DPO to help you assess DPIA quality when the DPO signed the DPIAs | Control owner assessing own control | Use Legal, an external privacy specialist, or scope to existence and process only |
| You ask the CISO's team to perform prompt injection testing on a system their team signed off | Self-review | Use an external tester, or test only whether testing occurred and findings were closed |

**Practical resolution:** where you cannot get an independent specialist, **narrow the scope of your conclusion and say so in the report**. A narrower opinion that is defensible beats a broader one that is not.

---

## 7.5 The scope limitation paragraph

Every AI governance audit report should contain a paragraph along these lines. It protects the audit, sets management's expectations, and is completely standard practice.

> **Scope and limitations**
> *This audit assessed the design and operating effectiveness of the institution's governance and control framework for artificial intelligence. It evaluated whether AI systems were inventoried, risk-assessed, validated, approved, secured, monitored and controlled in accordance with [institution] policy, the Risk Management in Technology Policy Document, and the Personal Data Protection Act 2010 as amended.*
>
> *This audit did **not** constitute an independent technical validation of any AI or machine learning model. Internal Audit did not assess the statistical accuracy, predictive performance, mathematical soundness or algorithmic fairness of any model. Where this report refers to model validation, it addresses whether validation was performed by an appropriately independent party, at the required time, to the scope required by the institution's own validation standard, and whether the resulting findings were addressed — not whether the validation's technical conclusions were correct.*
>
> *[Where applicable:] Internal Audit engaged [specialist] to provide a technical opinion on [specific matter]. That opinion is reflected in finding(s) [n].*

---

## 7.6 Building the capability — a realistic sequence

You do not need to become a data scientist. You need enough fluency to ask the right question and recognise a non-answer.

| Stage | What to do | Time |
|---|---|---|
| **1. Vocabulary** | Be able to explain, in plain English: model, training data, drift, bias, explainability, hallucination, prompt injection, RAG, guardrail, hold-out set, false positive/negative trade-off | 2–3 weeks of reading |
| **2. Criteria** | Read the current RMiT PD, the AI Governance Framework, the JPDP ADMP and DPIA Guidelines, and the BNM AI Discussion Paper. Map them into a criteria matrix | 2 weeks |
| **3. Observation** | Attend the AI governance forum as an observer for two cycles. Read the papers. Note what is and is not challenged | 2–3 months, in parallel |
| **4. First engagement** | Run an AI inventory and governance audit — no model-level technical testing. This alone delivers high value and builds credibility | One cycle |
| **5. Deepening** | Add model-level lifecycle testing on 2–3 high-risk use cases, with a specialist reviewing validation quality | Second cycle |
| **6. Structural** | Establish continuous monitoring (Phase 6) and build AI into the audit universe permanently | Ongoing |

**What to read a validation report for, as a non-specialist:** Does it state what was tested? Does it state against what standard? Does it state limitations? Does it reach a clear conclusion? Does it identify anything wrong? **A report that says everything is fine, states no limitations and identifies no issues is a warning sign in any assurance discipline — you already know how to recognise that.**

---

*Next: [08 — Presentation Deck](08-Presentation-Deck.md)*
