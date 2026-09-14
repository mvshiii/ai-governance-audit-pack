# 10 — Linking AI Governance to Existing Cybersecurity Audit Experience

> The reassuring finding of this whole pack: you are not starting from zero. You are starting from roughly 85%.

---

## 10.1 The methodology is the same chain

**Your existing chain**
> Requirement → Risk → Control → Evidence → Test → Gap → Recommendation

**The AI governance chain**
> AI Governance Requirement / Principle → AI Risk → AI Control → Evidence → Test → Finding → Recommendation

**They are the same chain.** What changes is what sits in each box.

| Link | Cybersecurity audit | AI governance audit | Same or different? |
|---|---|---|---|
| **Requirement** | RMiT; NACSA Code of Practice; ISO 27001; internal security policy | RMiT (same document); PDPA + JPDP guidelines; AI Governance Framework; internal AI policy | **Same technique.** One real difference: the AI criteria set is less mature and more mixed in legal force, so criteria *tiering* matters far more (see [03 §3.3](03-Malaysian-Landscape.md)) |
| **Risk** | Unauthorised access; data breach; service disruption; malware | Bias; drift; hallucination; data leakage; over-reliance; provenance failure | **Different content, same discipline.** Risk identification, likelihood/impact, aggregation — all unchanged |
| **Control** | MFA; segregation of duties; patching; logging; encryption | Independent validation; fairness threshold; human oversight; drift monitoring; prompt version control | **Roughly 70% overlap.** The genuinely new controls are five (see [05 §8.3](05-Audit-Domains-and-IT-Audit-Linkage.md)) |
| **Evidence** | Access lists; config exports; logs; policies; test reports | Access lists; config exports; logs; policies; **validation reports; monitoring output; prompt version history; override statistics; decision records** | **Same evidence disciplines.** New artefact types, same standards for what constitutes sufficient and appropriate evidence |
| **Test** | Sampling; reperformance; observation; inspection | Sampling; reperformance; observation; inspection | **Identical.** The evidence hierarchy is unchanged |
| **Gap / Finding** | Control absent, inadequate, or not operating | Control absent, inadequate, or not operating | **Identical.** Plus more emphasis on *aggregation* — many small AI gaps combining into a governance weakness |
| **Recommendation** | Remediate, with owner and date | Remediate, with owner and date | **Identical.** One difference: AI recommendations more often need to address *root cause in the governance framework*, not the individual system |

---

## 10.2 The real differences — be honest about these

| Difference | Why it matters | How to handle it |
|---|---|---|
| **Criteria are less mature and mixed in legal force** | In cybersecurity you can point at RMiT or the NACSA Code of Practice. In AI, much of the best guidance is voluntary | Tier your criteria explicitly. Anchor hard findings on mandatory instruments; use AI-specific guidance for expected practice and recommendations |
| **Controls degrade without change** | Your change-driven mental model ("no change means no new risk") does not hold | Add time-based triggers to your thinking: periodic re-validation, drift monitoring, scheduled fairness re-testing |
| **Output correctness is probabilistic** | You cannot test by expected-result comparison | Assess the *governance of testing*: were acceptance thresholds set in advance, by whom, and were they met? |
| **The technical ceiling is real** | You genuinely cannot assess whether a fairness metric was well chosen | Say so. Scope your conclusion, and engage a specialist where the audit needs to opine on technical adequacy |
| **Documentation is thinner** | Data science teams document less than software engineering teams | Expect more observation and reperformance, less inspection of records. Push relentlessly up the evidence hierarchy |
| **Ownership is more contested** | AI sits across IT, data, risk, model risk, compliance and business — often with no one clearly accountable | Map accountability early in Phase 1. The "orphan zone" — AI that no existing process claims — is where the biggest findings live |
| **The estate changes faster** | An annual or biennial audit cycle cannot track an estate growing 100% a year | Build the continuous monitoring phase in from the start |

---

## 10.3 Transferable competencies — map your existing strengths

| Existing competency | Transfers to | Transfer strength |
|---|---|---|
| **Risk assessment** | AI risk classification; independently re-rating use cases; testing whether the institution's own rating methodology is applied consistently | 🟢 **Direct.** The dimensions differ; the discipline is identical |
| **Control assessment** | Design and operating effectiveness across all 11 AI audit domains | 🟢 **Direct** |
| **Evidence review** | Validation reports, monitoring output, approval packages, change records, contracts | 🟢 **Direct.** You already know how to spot a report that says everything is fine, states no limitations and identifies no issues |
| **Governance assessment** | Policy auditability, committee effectiveness, ToR, quorum, challenge evidence, board reporting, delegated authority | 🟢 **Direct.** Reviewing 12 months of minutes for evidence of challenge is the same skill regardless of subject |
| **Access control** | AI platforms, model registries, training data stores, prompt repositories, **AI agent identities**, RAG entitlement enforcement | 🟢 **Direct — and immediately your highest-yield area.** AI platforms are routinely outside the UAR population |
| **Change management** | Models, training data, prompts, thresholds, configuration, vendor model updates, version reconciliation | 🟢 **Direct — with one scope extension.** Once you accept that a prompt is a configuration item, your existing programme works unmodified |
| **Cybersecurity** | AI endpoint security, API controls, DLP, supply chain integrity, encryption and key management, blast radius enumeration, log protection | 🟢 **Direct.** Your strongest single advantage. Most AI security risk is conventional security risk with a new entry point |
| **Third-party risk** | AI vendor due diligence, contract clause review, CUEC testing, configuration-versus-contract verification, concentration, exit | 🟢 **Direct — with a new clause checklist.** Add no-training, model change notification, ISO 42001, sub-processor disclosure |
| **Regulatory mapping** | Mapping RMiT, PDPA, FSA s.134, outsourcing, e-KYC and the AI Governance Framework to AI systems | 🟢 **Direct.** Your NACSA Code of Practice experience is directly analogous — mapping a control framework to an environment |
| **Audit reporting** | Findings, root cause, rating, aggregation, management action tracking | 🟢 **Direct.** One addition: criteria tiering discipline |
| **Cybersecurity governance** | AI policy structure, three-lines model, risk appetite articulation, board reporting | 🟢 **Direct** |
| **Control design assessment** | Whether an AI control would achieve its objective if it operated | 🟢 **Direct — and underused.** Design gaps in AI are abundant and cheap to find. A change policy that does not mention models is a finding requiring no sampling at all |

> **Count the greens.** Every competency listed transfers directly. Not one requires replacement — only extension of scope.

---

## 10.4 New competencies to build

Realistic, in priority order. None requires a data science qualification.

| # | Competency | What "sufficient" looks like | How to build it | Effort |
|---|---|---|---|---|
| 1 | **AI vocabulary and mental model** | You can explain model, training data, drift, bias, explainability, hallucination, prompt injection, RAG, guardrail, hold-out set and the false positive/negative trade-off in plain English, and recognise when someone is using them loosely | Read [01](01-AI-Governance-Fundamentals.md); read the BNM Discussion Paper; read the NIST GenAI Profile risk list | 2–3 weeks |
| 2 | **The Malaysian AI criteria set** | You can state what is mandatory, what is industry practice and what is advisory, and cite the right instrument for a given finding | Read the current RMiT PD, the AI Governance Framework, the JPDP ADMP and DPIA guidelines, and the BNM Discussion Paper. Build a criteria matrix | 2 weeks |
| 3 | **Reading a validation report as a non-specialist** | You can assess scope, independence, sequencing, threshold pre-agreement, limitations and findings — without assessing the statistics | Obtain 3 real validation reports and assess each against [06 Test 6](06-Sample-Audit-Tests.md). Discuss with Model Risk | 1–2 weeks |
| 4 | **Lifecycle thinking** | You instinctively ask "and then what happened six months later?" rather than stopping at go-live | Walk one use case end to end in Phase 1 of your first engagement | One engagement |
| 5 | **AI-specific security testing awareness** | You know what prompt injection testing should cover, can recognise an inadequate test report, and can enumerate blast radius | Work alongside the security team on Tests 12 and 14; read the NIST GenAI Profile | 2 weeks |
| 6 | **Fairness and explainability governance** | You can test whether fairness was defined, measured independently and monitored — and know precisely where to stop and call a specialist | Practise [06 Tests 7 and 8](06-Sample-Audit-Tests.md); discuss with Compliance and Model Risk | 2–3 weeks |
| 7 | **Criteria tiering discipline** | You never present an advisory point as regulatory non-compliance, and can defend each tier in a closing meeting | Practise on your first report; have Legal review the tiering | One report |
| 8 | **Specialist scoping and reliance** | You can define what a specialist is being asked, ensure their independence, and reflect their opinion properly in the report | [07](07-Specialist-Reliance.md); one co-sourced engagement | One engagement |

**Total realistic ramp-up to lead an AI governance audit: two to three months of part-time study alongside one engagement.** Not a career change.

---

## 10.5 What your cybersecurity background gives you that others lack

Worth stating explicitly, because it is easy to focus on the gap and miss the advantage.

1. **You already think in terms of attack surface and blast radius.** Most AI governance practitioners come from risk, compliance or data science and do not. The single best AI security test — enumerating what an AI system's service identity could do if fully manipulated — is a privileged access mindset applied to a new asset.

2. **You are comfortable with negative assurance.** Cybersecurity auditors are used to proving that something *cannot* happen and to testing controls actively. The RAG entitlement test, the blocking test, the reconstruction test — these are active tests, and auditors from a documentation-review background rarely think to run them.

3. **You know how to test completeness against independent populations.** Finding unmanaged assets is the core of any cybersecurity asset management audit. AI inventory completeness is exactly the same problem with different vendors.

4. **You are used to immature, mixed-force criteria.** The NACSA Code of Practice, ISO 27001 and internal standards already required you to distinguish mandatory from good practice. Most auditors trained purely on financial controls find AI criteria tiering genuinely difficult; you will not.

5. **You already audit third parties you cannot inspect.** Cloud security assurance taught you to work from SOC 2 reports, CUECs and configuration verification rather than direct testing. That is precisely the AI third-party audit problem.

6. **You understand that a control that exists on paper and a control that operates are different things.** Every cybersecurity auditor has found a policy requiring MFA on a system where MFA was not enforced. AI is full of the same pattern — "we have human oversight" with a 0.3% override rate.

---

## 10.6 A six-month personal development plan

| Month | Focus | Concrete output |
|---|---|---|
| **1** | Vocabulary and criteria. Read [01](01-AI-Governance-Fundamentals.md) and [03](03-Malaysian-Landscape.md). Obtain and read the current RMiT PD, the AI Governance Framework, the JPDP ADMP guideline and the BNM Discussion Paper | A one-page criteria matrix for your institution, tiered by legal force |
| **2** | Reconnaissance. Interview the Head of Data/AI, CISO, DPO and Head of Model Risk. Request the AI inventory. Attend the AI governance forum as an observer | A draft AI landscape map and an initial view of the "orphan zone" |
| **3** | Inventory. Run independent-source triangulation — AP data, cloud billing, proxy logs, contract register, embedded-AI sweep | An independently verified inventory with a completeness percentage. **This alone justifies the six months** |
| **4** | First testing. Run [06 Tests 2, 5 and 10](06-Sample-Audit-Tests.md) — inventory, access, change. All three use existing skills | Three tested control areas; likely three findings |
| **5** | Extend. Add Tests 11 (monitoring), 13 (third party) and 14 (GenAI). Engage the security team on Test 12 | A defensible draft report covering seven domains |
| **6** | Report and institutionalise. Tier the criteria, write the scope limitation paragraph, present to the Audit Committee. Propose continuous monitoring | Issued report; AI added to the audit universe; quarterly reconciliation established |

> **The shortcut, if you have less time:** do Month 3 first. An independently verified AI inventory is the highest-value single deliverable in this discipline, requires no AI knowledge, and reliably reshapes the institution's understanding of its own exposure.

---

*Next: [11 — Cheat Sheet](11-Cheat-Sheet.md)*
