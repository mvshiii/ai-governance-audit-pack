# 03 — The Malaysian AI Governance Landscape

**Verified as at September 2026.** Re-verify every version and effective date before citing in an audit report — this space moved materially in the twelve months to mid-2026.

---

## 3.0 The single most important point for an auditor

🔴 **MUST-KNOW**

As at September 2026, **there is no AI-specific mandatory regulation for Malaysian financial institutions.** BNM has issued a *discussion paper*, not a policy document. The sector's AI Governance Framework is *industry-led*, not a BNM policy document.

This does **not** mean AI is unregulated. It means AI is regulated **through existing, already-mandatory instruments**:

| What is happening | Already-mandatory instrument that bites |
|---|---|
| An AI model runs on a cloud platform | ⚖️ RMiT (technology risk, cloud, access, change, resilience) |
| Customer data flows into an AI service | ⚖️ FSA 2013 s.134 banking secrecy; ⚖️ PDPA 2010 (as amended) |
| The AI service is provided by a vendor | ⚖️ BNM outsourcing requirements; ⚖️ RMiT third-party provisions |
| An AI model drives a credit decision | ⚖️ Capital adequacy / credit risk requirements including independent model validation where internal models are used |
| An AI decision affects a customer's outcome | ⚖️ Fair Treatment of Financial Consumers requirements |
| AI performs identity verification | ⚖️ BNM e-KYC Policy Document |
| AI supports transaction monitoring | ⚖️ AML/CFT requirements including system testing and validation |
| A customer is subject to a solely automated decision | ⚖️ PDPA + JPDP Automated Decision-Making & Profiling Guideline (2026) |

**Audit consequence:** You can raise **hard compliance findings today** without waiting for an AI regulation. Frame findings against the mandatory instrument, and use the AI-specific guidance to support the *recommendation*, not the *criterion*. This is the single most important framing decision in a Malaysian AI governance audit.

---

## 3.1 Framework assessment table

| Framework | Issuer | Status | Key Governance Areas | Relevance to Malaysian FIs |
|---|---|---|---|---|
| **Discussion Paper on Artificial Intelligence in the Malaysian Financial Sector** (issued 5 Aug 2025; consultation closed 17 Oct 2025; feedback statement indicated for 2026) | Bank Negara Malaysia (Financial Development and Innovation) | 📘 **Discussion paper — NOT binding.** Exploratory; sets out BNM's proposed approach and invites feedback | Scope of any future AI regulation; risks in AI adoption; adequacy of the existing regulatory framework; AI development approach. Notes >70% of FSPs have implemented at least one AI application | 🔴 **Very high as a signal of direction.** Use to anticipate future requirements and to justify getting ahead of them. **Do not cite as a requirement.** Read it to understand what BNM already thinks the existing framework covers |
| **AI Governance Framework** for the Malaysian financial services sector (launched late 2025) | AICB Chief Risk Officers' Forum, supported by BNM, endorsed by the Association of Banks in Malaysia (ABM) | 🏛️ **Industry framework — voluntary but strongly signalled.** BNM has publicly welcomed it and encouraged insurance/takaful to develop complementary guidance | High-level principles — **transparency, accountability, fairness, privacy, robustness** — plus best practices and illustrative Malaysian banking use cases (retail credit assessment, fraud detection, customer engagement analytics) | 🔴 **Highest practical relevance.** This is the sector's own benchmark, developed with BNM involvement. A bank that has not assessed itself against it is out of step with peers. **Best available "expected practice" criterion** for a Malaysian bank |
| **Risk Management in Technology (RMiT)** — revised Policy Document issued 28 Nov 2025, effective 28 Nov 2025 (with stated exceptions); FAQ updated 1 Jul 2026 | Bank Negara Malaysia (Risk Specialist and Technology Supervision) | ⚖️ **MANDATORY policy document.** Applies to licensed banks, Islamic banks, investment banks, insurers, takaful operators, MSBs, payment system operators; 2025 revision extended coverage to non-bank Merchant Acquirers and Intermediary Remittance Institutions above a 5% market-share threshold | Technology risk governance; access control; change management; cryptography; cloud and third-party technology; cyber resilience; incident management and reporting; technology operations and availability | 🔴 **Your primary enforceable criterion.** RMiT does not need an AI chapter to apply to AI: an AI system is a technology system. **Every AI platform, model endpoint, dataset and pipeline is in RMiT scope.** ⚠️ Read the current PD directly and map its clauses to your AI systems — do not rely on summaries |
| **National Guidelines on AI Governance & Ethics (AIGE)** (launched Sept 2024) | Ministry of Science, Technology and Innovation (MOSTI) | 📘 **Voluntary national guidelines.** Non-binding; addressed to three audiences — end users, policymakers/regulators, and developers/suppliers | Seven principles: fairness; reliability, safety and control; privacy and security; inclusiveness; transparency; accountability; and pursuit of human benefit/human-centricity | 🟡 **Moderate.** Useful for vocabulary and for demonstrating alignment with national policy. Superseded in practical terms for banks by the sector-specific AI Governance Framework. Cite as supporting context, not as criteria |
| **PDPA 2010, as amended by the Personal Data Protection (Amendment) Act 2024** — phased into force during 2025 | Parliament / Personal Data Protection Commissioner (JPDP), Ministry of Digital | ⚖️ **MANDATORY law.** Key changes in force: "data controller" terminology; **biometric data classified as sensitive personal data**; mandatory DPO appointment; mandatory breach notification (72-hour window for qualifying incidents); data portability; maximum fine raised to RM1,000,000 per offence | Lawful basis; purpose limitation; data minimisation; security; cross-border transfer; data subject rights; processor obligations | 🔴 **Very high and directly applicable.** Biometric data becoming *sensitive* personal data has immediate consequences for e-KYC facial recognition and voice biometrics |
| **JPDP Guidelines: Data Protection Impact Assessment (DPIA); Automated Decision-Making & Profiling (ADMP); Data Protection by Design (DPbD)** — finalised and released around 30 Apr – 8 May 2026 | Personal Data Protection Commissioner (JPDP) | ⚖️/📘 **Regulator-issued guidelines supplementing the PDPA.** Treat as authoritative supervisory expectation; assess their precise legal force with Legal before citing as a hard requirement | When a DPIA is required and what it must contain; governance of automated decision-making, profiling and scoring systems; privacy-by-design in system development | 🔴 **The most significant 2026 development for AI auditors in Malaysia.** The ADMP Guideline is the closest thing Malaysia has to direct AI decision-making regulation, and it applies across sectors. **Obtain it and map your AI inventory against it** |
| **ASEAN Guide on AI Governance and Ethics** (2024) and the **Expanded Guide on Generative AI** (2025) | ASEAN Digital Ministers | 📘 **Voluntary regional guide.** No legal force in Malaysia | National-level and organisational-level recommendations; risk assessment; internal governance structures; GenAI-specific guidance | 🟡 **Low-to-moderate for audit criteria; useful for regional groups.** Relevant if the institution operates across ASEAN and wants one consistent approach |
| **ISO/IEC 42001:2023** — AI Management System (AIMS) | ISO/IEC | 📗 **Voluntary international standard. Certifiable** | Management system structure: context, leadership, planning, support, operation, performance evaluation, improvement; AI-specific controls in Annex A; impact assessment | 🔴 **High value as a structuring backbone.** If the bank pursues certification, this becomes your audit criteria set. Also increasingly requested of AI *vendors* — asking a vendor for ISO 42001 certification is a concrete due diligence step |
| **ISO/IEC 23894:2023** — AI risk management guidance | ISO/IEC | 📗 **Voluntary international standard. Guidance only, not certifiable** | Applies ISO 31000 risk management to AI; risk sources specific to AI across the lifecycle | 🟡 **Useful for the 2nd line designing an AI risk assessment methodology.** Less directly useful as audit criteria |
| **NIST AI Risk Management Framework 1.0** (Jan 2023) | US NIST | 📗 **Voluntary framework.** No legal force in Malaysia | Four functions — **GOVERN, MAP, MEASURE, MANAGE** — plus characteristics of trustworthy AI (valid and reliable, safe, secure and resilient, accountable and transparent, explainable and interpretable, privacy-enhanced, fair with harmful bias managed) | 🔴 **High value as an audit programme structure.** Free, well-organised, widely understood. GOVERN/MAP/MEASURE/MANAGE maps cleanly onto audit domains. Use it to *organise* your work, not to assert compliance |
| **NIST AI 600-1 — Generative AI Profile** (Jul 2024) | US NIST | 📗 **Voluntary companion profile** | GenAI-specific risks (confabulation, dangerous content, data privacy, information integrity, IP, value chain) and suggested actions | 🟡 **Useful checklist when auditing GenAI specifically.** Best single free source for GenAI risk enumeration |

### Also mandatory, and often overlooked in AI scoping

| Instrument | Why it matters to AI |
|---|---|
| ⚖️ **FSA 2013 s.134 / IFSA 2013 s.145 — secrecy of customer information** | Sending customer information to an AI service — including a cloud-hosted LLM — is a disclosure. It needs a permitted basis. This is a *criminal* provision, not merely a policy matter |
| ⚖️ **BNM Policy Document on Outsourcing** | Third-party AI services frequently constitute outsourcing arrangements. Assess and document the determination |
| ⚖️ **BNM Policy Document on Electronic Know-Your-Customer (e-KYC)** — current version April 2024 | Directly governs an AI system already in every retail bank: facial recognition and liveness detection. Contains concrete, testable expectations about performance and controls. **The best existing example of BNM already regulating an AI application** |
| ⚖️ **Fair Treatment of Financial Consumers requirements** | The conduct lens on AI-driven customer outcomes. Bias in a scorecard is a fair treatment issue before it is a model issue |
| ⚖️ **AML/CFT requirements** | Transaction monitoring systems — including ML-based ones — are subject to testing, tuning and validation expectations |
| ⚖️ **Capital adequacy requirements for internal models** | Where AI feeds regulatory capital or IFRS 9 ECL, existing independent model validation requirements apply in full |

### Watch items (verify current status before relying on them)

- **BNM feedback statement / any subsequent exposure draft or policy document on AI.** BNM's Annual Report 2025 indicated a feedback statement in 2026. Check `bnm.gov.my` before every engagement — if an exposure draft has been issued, the compliance conversation changes.
- **BNM Financial Sector Blueprint / Master Plan 2027–2030.** In development during 2026; the Governor has publicly framed AI as a central theme.
- **BNM Discussion Paper on Operational Resilience.** Verify its current status and whether it has progressed; operational resilience expectations bear directly on AI fallback and concentration risk.
- **National AI legislation.** The National AI Office (NAIO), under the Ministry of Digital, has been developing dedicated AI legislation and an AI Technology Action Plan. Timelines have been discussed publicly but **do not assume enactment** — verify.
- **Insurance and takaful sector AI guidance.** BNM has encouraged the ITO sector to develop guidance complementary to the banking AI Governance Framework.

---

## 3.2 Recommended baseline — use these, not all ten

🔴 **MUST-KNOW.** A methodology built on ten frameworks is unusable. Four references, with clearly separated roles:

### 1. ⚖️ RMiT (current revised Policy Document) — **the enforceable technology criterion**
**Role:** Every hard finding about access, change, cloud, third party, resilience, incident management and logging on an AI system is written against RMiT.
**Why:** It is mandatory, BNM supervises against it, and it applies to AI systems without needing to say the word "AI."
**How to use:** Build an RMiT clause → AI system mapping. Where an AI platform is not covered by a control the FI applies to its other technology systems, that is an RMiT gap — state the clause.

### 2. ⚖️ PDPA (as amended) + JPDP DPIA / ADMP / DPbD Guidelines — **the enforceable data and decisioning criterion**
**Role:** Every finding about personal data use, DPIAs, profiling, automated decisions, transparency and human review.
**Why:** Mandatory law, recently strengthened, with 2026 guidelines that speak directly to AI-style decisioning. Penalties are real.
**How to use:** Map AI systems processing personal data → DPIA status → ADMP applicability. Compile the solely-automated-decision inventory.

### 3. 🏛️ AI Governance Framework (AICB CRO Forum / ABM, BNM-supported) — **the expected-practice criterion**
**Role:** The AI-specific governance benchmark. Where there is no mandatory rule, this is what "good" looks like for a Malaysian bank.
**Why:** Sector-specific, developed with BNM involvement and ABM endorsement, built around Malaysian banking use cases. Peers are using it.
**How to use:** Assess governance arrangements against its five principles (transparency, accountability, fairness, privacy, robustness). Report gaps as **"variance from industry expected practice"** — not as regulatory non-compliance.

### 4. 📘 BNM Discussion Paper on AI (Aug 2025) — **the direction-of-travel input**
**Role:** Shapes recommendations and gives the audit committee a forward view. Supports "you should fix this before it becomes a requirement."
**Why:** It is BNM's own statement of how it is thinking about AI risk and regulatory adequacy.
**How to use:** In the report's context section and in recommendations. **Never in the criteria column.**

### Optional structuring layer — pick exactly one
- 📗 **NIST AI RMF** — if you want a free, well-understood structure for the audit programme. *Default recommendation for an internal audit function.*
- 📗 **ISO/IEC 42001** — if the institution intends to certify, or if you want a management-system audit structure familiar from ISO 27001 work.

**Do not use both.** Choose one, state it in the audit terms of reference as the structuring reference, and be explicit that it is voluntary.

---

## 3.3 How to write the criteria section of your report

🔴 This is where new AI auditors most often get into trouble with management. Use three distinct tiers and label them:

| Tier | Label in the report | Example wording | Management can argue? |
|---|---|---|---|
| 1 | **Regulatory requirement** | "RMiT paragraph X requires... The AI platform is not subject to the periodic user access review, contrary to this requirement." | No — this is non-compliance |
| 2 | **Expected industry practice** | "The AI Governance Framework endorsed by ABM sets out an accountability principle requiring a named owner for each AI system. 14 of 41 registered systems have no named owner." | Only on materiality, not on validity |
| 3 | **Good practice / forward-looking** | "BNM's 2025 Discussion Paper signals an expectation of institution-wide AI inventories. Establishing this now would position the bank ahead of any future requirement." | Yes — this is advisory, and should be presented as such |

**If you label Tier 2 or Tier 3 as Tier 1, you will lose the argument in the closing meeting and damage the credibility of the entire report.** Conversely, if you present everything as advisory, nothing gets fixed. Get the tiering right and the report largely writes itself.

---

## 3.4 Sources

- [BNM — Discussion Paper on Artificial Intelligence in the Malaysian Financial Sector](https://www.bnm.gov.my/-/dp-aifs25)
- [BNM — Revised Policy Document on Risk Management in Technology (RMiT), 28 Nov 2025](https://www.bnm.gov.my/-/pd-rmit-nov25)
- [BNM Annual Report 2025 — Promoting a Progressive & Inclusive Financial System](https://www.bnm.gov.my/publications/ar2025/ch1c)
- [BNM Governor's Opening Address, AICB Nexus 2026 (8 July 2026)](https://www.bnm.gov.my/-/g-spch-aicb-nexus)
- [BNM — Policy Document on Electronic Know-Your-Customer (e-KYC)](https://www.bnm.gov.my/-/pd-ekyc-en)
- [AICB — Driving Responsible AI Adoption: Introducing the AI Governance Framework](https://www.aicb.org.my/announcement/driving-responsible-ai-adoption)
- [JPDP — Public Consultation Paper No. 3/2025: Automated Decision Making and Profiling Guideline](https://www.pdp.gov.my/ppdpv1/en/akta/public-consultation-paper-no-3-2025-automated-decision-making-and-profiling-guideline/)
- [National Guidelines on AI Governance and Ethics (AIGE) — MyGovernment portal](https://www.malaysia.gov.my/en/my-initiative/whole-government-digital-services/tadbir-urus/national-guidelines-on-artificial-intelligence-governance-and-ethics-aige)
- [Malaysia National AI Office (NAIO) — AI Governance and Ethics](https://www.ai.gov.my/faq/ai-governance-and-ethics/)
- [Rajah & Tann Asia — News Alert: BNM Issues Discussion Paper on AI in the Financial Sector](https://www.rajahtannasia.com/viewpoints/bank-negara-malaysia-issues-discussion-paper-on-artificial-intelligence-in-the-financial-sector-for-public-feedback/)
- [Rahmat Lim & Partners — BNM revises policy document on Risk Management in Technology](https://www.rahmatlim.com/publication/articles/32031/bank-negara-malaysia-revises-policy-document-on-risk-management-in-technology)
- [Future of Privacy Forum — Malaysia Charts Its Digital Course: New Frameworks for Data Protection and AI Ethics](https://fpf.org/blog/malaysia-charts-its-digital-course-a-guide-to-the-new-frameworks-for-data-protection-and-ai-ethics/)
- [UNESCO Global AI Ethics and Governance Observatory — Malaysia](https://www.unesco.org/ethics-ai/en/malaysia)

---

*Next: [04 — Audit Methodology](04-Audit-Methodology.md)*
