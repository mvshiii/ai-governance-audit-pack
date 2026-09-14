# 05 — AI Governance Audit Domains & Linkage to Traditional IT Audit

---

# PART 7 — Eleven Consolidated Audit Domains

## Consolidation rationale

The eighteen candidate topics collapse into eleven testable domains. Consolidation matters because overlapping domains produce duplicated testing, duplicated findings and a report the audit committee cannot follow.

| Candidate topics | Consolidated into |
|---|---|
| Governance & Oversight + AI Strategy, Policy & Risk Appetite | **D1 Governance, Policy & Risk Appetite** |
| AI Inventory & Classification | **D2 AI Inventory & Risk Classification** |
| AI Risk Assessment (+ approval gates) | **D3 Risk Assessment & Approval** |
| Data Governance + Privacy | **D4 Data Governance & Privacy** |
| Development/Acquisition Lifecycle + Model Testing & Validation | **D5 Development, Acquisition & Validation** |
| Fairness & Explainability + Human Oversight | **D6 Fairness, Explainability & Human Oversight** |
| AI Security | **D7 AI Security** |
| Third-Party AI | **D8 Third-Party & Cloud AI** |
| Change Management + Monitoring/Drift + AI Incident Management | **D9 Change, Monitoring & Incident Management** |
| Generative AI | **D10 Generative AI** *(cross-cutting overlay, not a separate silo)* |
| Resilience + Record Keeping | **D11 Resilience & Record Keeping** |

> **On D10:** GenAI is deliberately treated as an *overlay* applied to D1–D9 for GenAI use cases, plus a small set of GenAI-only controls. Treating GenAI as a separate silo is the most common structural mistake in AI audit programmes — it causes teams to re-invent access, change and third-party testing they already do well.

---

## D1 — Governance, Policy & Risk Appetite

| | |
|---|---|
| **Key risk** | No accountable governance structure, no enforceable policy, and no articulated risk appetite — so AI risk decisions are made informally, inconsistently and without board visibility |
| **Expected controls** | Board-approved AI policy with mandatory requirements, defined roles across three lines, prohibited/restricted use list, and defined approval authorities · AI governance forum with board-approved ToR, quorum, 2nd line membership and escalation path to Board Risk Committee · Articulated AI risk appetite with measurable indicators · Periodic board and BRC reporting on AI risk · Policy review cycle and staff communication/training · Clear interface between the AI framework and existing MRM, technology, data and third-party frameworks |
| **Evidence** | AI policy with approval and review dates · Standards and procedures · Forum ToR, membership, 12 months of minutes and papers · Delegated authority matrix · Risk appetite statement and KRI reporting · Board/BRC packs · Training records and completion rates · RACI across three lines |
| **Example audit test** | Test the policy for **auditability**: does it contain "must" requirements, named accountabilities, and specific prohibited uses? Review 12 months of forum minutes for quorum, 2nd line attendance and **evidence of substantive challenge** (deferrals, conditions, refusals) — a 100% approval rate with no conditions indicates a rubber-stamp forum. Trace AI risk appetite metrics from the statement through to actual reporting: **an appetite statement with no measured indicator is not a control.** Test that the policy explicitly resolves whether AI models fall under the existing MRM framework — an unresolved boundary is where systems fall through |

---

## D2 — AI Inventory & Risk Classification

| | |
|---|---|
| **Key risk** | The institution does not know what AI it has, so a material portion of the estate sits outside every governance control |
| **Expected controls** | Central AI inventory with a defined data standard and named owner · Scope definition explicitly covering embedded and third-party AI · Mandatory registration at intake, enforced by the procurement and change gates · Documented risk classification methodology with defined criteria · Periodic completeness reconciliation against independent sources · Periodic owner re-attestation · Inventory registration as a prerequisite for production deployment |
| **Evidence** | Raw inventory extract · Inventory standard and scope definition · Classification methodology · Completed classifications · Reconciliation evidence and results · Attestation records · Change/procurement gate configuration requiring inventory reference |
| **Example audit test** | 🔴 **Independent completeness testing** using AP data, cloud billing, proxy logs, the vendor register and an embedded-AI sweep of the top 20 critical applications (see [04 Step 2](04-Audit-Methodology.md)). Report the reconciliation as a percentage. Test field completeness across the **whole** population — named individual owners, risk rating present, validation date present. **Re-rate 5 systems independently using the bank's own criteria and compare;** systematic under-rating by management is a high-grade finding because every downstream control is calibrated from the rating |

---

## D3 — Risk Assessment & Approval

| | |
|---|---|
| **Key risk** | AI is deployed without a proper assessment of what could go wrong, or is approved by someone without the authority or information to accept the risk |
| **Expected controls** | Mandatory standardised AI risk assessment before build/buy, covering model, data, privacy, security, conduct, third-party and resilience risk · Independent 2nd line review and challenge · Risk tier drives mandatory downstream requirements · Approval authority matrix tiered by risk · Standard approval package (risk assessment, validation report, limitations, monitoring plan, fallback) · Conditions and expiry attached to approvals · Register of approvals · Periodic re-approval |
| **Evidence** | Risk assessment methodology and templates · Completed assessments · Evidence of 2nd line challenge (comments, version history, sign-offs) · DPIAs · Authority matrix · Approval papers and minutes · Approval register with conditions and expiry dates |
| **Example audit test** | Test that **every** production AI system has a completed, current risk assessment — population-level, cheap, high-yield. For 5 sampled systems, trace the approval to the authority matrix and confirm the approver had authority. **Test whether the approval package actually contained the validation report** — approvals granted before validation completed are common and are evidenced simply by comparing dates. Look for at least one assessment that 2nd line challenged and changed; a challenge function with no record of ever disagreeing is not operating |

---

## D4 — Data Governance & Privacy

| | |
|---|---|
| **Key risk** | AI is built on data the institution does not understand, does not have the right to use, or cannot trace — producing biased outputs, privacy breaches and an inability to explain decisions |
| **Expected controls** | Documented data sourcing, provenance and lineage per model · Data quality assessment before use, against defined dimensions and thresholds · Data owner approval for the specific AI purpose · Lawful basis and purpose-limitation assessment (PDPA) · DPIA for high-risk processing, aligned to the JPDP DPIA Guideline · Data classification applied to AI datasets · Prohibited and proxy variable review · Representativeness assessment · Access control and logging on training data stores · Retention and disposal per schedule · Production input data quality monitoring |
| **Evidence** | Data dictionary and lineage documentation · Data quality reports with dates · Variable list including excluded variables and reasons · Data owner approvals · Lawful basis assessments and DPIAs · DPO review evidence · Dataset ACLs and access review evidence · Retention schedule covering AI artefacts |
| **Example audit test** | For a sampled model, reconcile the production variable list to the data dictionary — **undocumented variables are a lineage failure.** Confirm a documented proxy-variable review took place. Trace one dataset from original collection purpose to current AI use and test whether the purpose change was assessed. **Run a standard access review on the training data store** — who has write access, is it least privilege, is it in the UAR scope, when was it last reviewed? *This last test requires no AI knowledge and reliably produces findings* |

---

## D5 — Development, Acquisition & Validation

| | |
|---|---|
| **Key risk** | Models are built or bought without engineering discipline, and are put into production without credible independent challenge |
| **Expected controls** | Version control for code, model artefacts, prompts, configuration and training data references · Segregated dev/test/prod environments · SoD between build, validate, approve and deploy · Secure development and dependency/artefact scanning · Approved-source policy for external models and datasets · AI-specific vendor due diligence · Validation standard defining minimum scope by risk tier · Validator independence from the developer · Validation against hold-out data · Performance tested against pre-agreed thresholds · Documented limitations and conditions of use · Validation findings tracked to closure before go-live · UAT sign-off by the business owner |
| **Evidence** | Repository and commit history · Environment topology · SoD matrix and actual entitlements · Validation standard · Validation reports with named author and reporting line · Test data description · Results vs thresholds · Documented limitations · Validation finding tracker · UAT sign-offs · Vendor due diligence files |
| **Example audit test** | 🔴 **Test the governance of validation, not the statistics** — see [07](07-Specialist-Reliance.md). Four checks, all documentary: (1) was the validator independent of the developer, by name and reporting line; (2) was validation completed *before* approval, by date comparison; (3) were pre-agreed thresholds met, and if not, who accepted the exception and did they have authority; (4) were validation findings closed before deployment. Separately, run the **version reconciliation test**: take the model currently serving production, obtain its version identifier, and trace it to the validation report, the approval record and the change record. Any break in that chain is a strong finding |

---

## D6 — Fairness, Explainability & Human Oversight

| | |
|---|---|
| **Key risk** | AI produces systematically unfair outcomes, cannot be explained to those affected, and the human control designed to catch this has become a formality |
| **Expected controls** | Fairness requirement with a defined metric and threshold **set before testing** · Disparate-impact testing across defined segments, by an independent party · Ongoing fairness monitoring, not a one-off at launch · Explainability requirement defined at design stage, proportionate to impact · Reason codes generated and stored with each decision · Adverse-action explanation process for customer-facing decisions · Documented human oversight model (in-loop / on-loop / out-of-loop) approved at the right level · Reviewers given the information, authority, time and training to exercise oversight · Override rate monitored with expected ranges · QA sampling of human reviews · Documented route for customers to request human review of automated decisions |
| **Evidence** | Fairness requirement documentation with dates · Fairness test reports and segment definitions · Ongoing fairness monitoring output · Explainability assessment · Sample adverse-action communications sent to customers · Human oversight design documentation · Override statistics and trend · QA sampling results · Reviewer training records · Customer human-review request log |
| **Example audit test** | 🔴 **Three tests, none requiring statistics.** (1) **Fairness governance:** was a numeric fairness threshold defined *in advance*, by whom, and tested by whom? A bank that has never defined what "fair" means numerically cannot demonstrate it achieved it. (2) **Explainability in practice:** obtain a real adverse-action letter and ask a front-line officer to explain a specific decline — if they cannot, explainability does not exist operationally regardless of the technical documentation. (3) **Oversight effectiveness:** obtain and trend the override rate. Near 0% or near 100% both indicate failure. Sample 15 reviewed cases and check timestamps — seconds between presentation and approval is compelling evidence of rubber-stamping. Then **observe the control being performed** |

---

## D7 — AI Security

| | |
|---|---|
| **Key risk** | AI systems introduce new attack surfaces (prompt injection, model extraction, training data poisoning) while also frequently escaping the conventional security controls applied to other systems |
| **Expected controls** | AI platforms and endpoints in scope for IAM standard, UAR cycle, PAM, MFA and logging · AI endpoints registered in the API inventory and behind the API gateway with authentication, authorisation, rate limiting and TLS · AI systems in scope for vulnerability management and penetration testing · Adversarial / prompt-injection testing before go-live and after material change, covering *indirect* injection via documents and retrieved content · Input sanitisation and output validation · Least privilege for the AI's own downstream permissions (blast radius limitation) · Integrity controls on training data and model artefacts · Approved-source policy and integrity verification for external models · Encryption and key management for AI data stores · Prompt and output logging with protected storage · AI agent/service identities inventoried and governed as privileged non-human accounts |
| **Evidence** | User and privileged access lists for AI platforms, model registries and data stores · UAR evidence · API inventory and gateway configuration · Penetration test scope and reports · Adversarial test reports · DLP configuration for AI endpoints · Encryption and key management documentation · Log configuration and samples · Service account inventory |
| **Example audit test** | 🔴 **Most of this is your day job.** Confirm AI platforms are in the UAR scope — if they are not, that is the first finding. Extract the user list and test against HR leaver data. Test privileged accounts for justification and PAM coverage. Reconcile the AI inventory to the API inventory and the penetration test schedule — **AI endpoints absent from both is a clean finding.** Then the AI-specific tests: obtain the prompt-injection test report and check it covered indirect injection; and **enumerate the blast radius** — what API scopes and entitlements does the AI system's service identity hold, and what could it do if fully manipulated? |

---

## D8 — Third-Party & Cloud AI

| | |
|---|---|
| **Key risk** | Critical AI capability sits outside the institution's control, with contracts that do not protect it, assurance that is filed but unread, and concentration that has never been assessed |
| **Expected controls** | AI-specific due diligence on the AI service, not just the parent vendor · Outsourcing determination documented and assessed against BNM outsourcing requirements and RMiT third-party provisions · Contractual terms covering data use and **explicit prohibition on training with bank data**, data location, sub-processors, retention and deletion, model change notification, performance SLAs, audit and regulator access rights, and exit assistance · Banking secrecy (FSA s.134) assessment before customer information is disclosed · Independent assurance reports obtained **and reviewed**, including exceptions and CUECs · Configuration verified to match contractual commitments · Concentration risk assessment across AI providers · Exit strategy and substitutability assessment · Ongoing vendor performance monitoring |
| **Evidence** | Vendor list with criticality and outsourcing determination · Due diligence files with dates · Executed contracts and schedules · Assurance reports and the bank's documented review of them · Tenant configuration evidence · Secrecy assessments · Concentration assessment and the forum that considered it · Exit plans · Vendor model change notifications and impact assessments |
| **Example audit test** | Review 5 AI vendor contracts against a clause checklist. **Flag every contract silent on vendor retraining using bank data** — this has direct FSA s.134 and PDPA implications. 🔴 **Test the CUECs** in the provider's SOC 2 report: these are the controls the provider says *you* must operate, and most institutions file the report without reading them. **Verify configuration against contract** — for an enterprise AI service with a "do not train" or retention setting, obtain the actual tenant configuration screenshot; do not accept the contract as evidence the setting is applied. Map AI systems to providers and to critical business services to test concentration |

---

## D9 — Change, Monitoring & Incident Management

| | |
|---|---|
| **Key risk** | Models change without control, degrade without detection, and fail without being recognised as incidents |
| **Expected controls** | **Change:** change policy explicitly covering models, training data, prompts, parameters, thresholds and configuration · Materiality criteria triggering re-validation and re-approval · Automated retraining requires human approval before production promotion · Prompts under version control with an approval workflow · SoD — developers cannot deploy to production · Vendor model change notification process and impact assessment. **Monitoring:** monitoring plan per model with metrics, thresholds, frequency, owner and escalation · Drift detection on inputs and outputs · Periodic performance reporting to a governance forum · Recurring fairness monitoring · Override rate tracking · Documented response to every threshold breach. **Incidents:** AI incident types defined in the taxonomy · Escalation criteria · RCA · Regulatory notification assessment (RMiT incident reporting; PDPA breach notification) · Post-incident review and trend analysis |
| **Evidence** | Change policy text covering AI assets · Change records for AI over the period · Prompt version history · Retraining logs and approvals · Re-validation reports · Vendor change notifications and assessments · Monitoring plans · 12 months of monitoring output · Threshold breach records and responses · Governance forum packs showing AI performance · Incident register filtered for AI · RCA documents |
| **Example audit test** | 🔴 **Four of the highest-yield tests in the whole programme.** (1) **Prompt change management:** request the system prompt change history for a GenAI use case and compare to formal change records. In most institutions prompts are edited in a console with no change record — an unauthorised change to a production control. (2) **Monitoring continuity and action:** obtain 12 months of monitoring output; test for gaps, for thresholds defined in advance, and trace **every** breach to a documented response. Breaches with no recorded response is the most common AI monitoring finding. (3) **Vendor model change:** obtain every provider model-version notification in 12 months and the bank's assessment of each. (4) **Incident classification:** an estate of 40 AI systems with zero recorded AI incidents means incidents are not being classified — corroborate by searching complaints and helpdesk tickets for AI issues that never became incidents |

---

## D10 — Generative AI *(cross-cutting overlay)*

| | |
|---|---|
| **Key risk** | GenAI is adopted at enterprise scale, faster than governance, producing confident-but-wrong output into regulated processes and carrying confidential data out of the institution |
| **Expected controls** | **Enterprise deployment:** approved enterprise GenAI service with contractual no-training and defined retention · Public GenAI services blocked at the network/CASB layer · Acceptable use policy specifying what may never be entered, with training and attestation · DLP covering AI endpoints. **Grounding and accuracy:** RAG grounding on approved bank content · Topic scoping with refusal behaviour outside scope · Source citation · Pre-deployment accuracy testing against a curated question set with a pass threshold · Ongoing output sampling and quality review. **Entitlements:** retrieval enforces the *individual user's* existing document entitlements. **Use boundaries:** defined list of processes where GenAI output may and may not be used · Mandatory human review with retained human accountability for regulated outputs · Record of AI involvement in outputs. **Customer-facing:** disclosure that the counterparty is an AI · Escalation to a human · High-stakes topics routed to humans. **Logging:** prompt and output logging, with the log store itself classified and access-controlled |
| **Evidence** | Approved/blocked service list and proxy configuration · Enterprise tenant configuration (training opt-out, retention) · Acceptable use policy, communications and training completion · DLP rules and alert triage evidence · RAG architecture and entitlement enforcement design · Accuracy test methodology and results · Output sampling programme and findings · Permitted/prohibited process list · Sample AI-assisted regulated outputs showing human review · Customer-facing disclosure evidence · Prompt log configuration, retention and ACL |
| **Example audit test** | 🔴 **The RAG entitlement test — the single most important GenAI test.** With authorisation, use a restricted test account to query the enterprise assistant for content in a document that account cannot open directly. If the assistant returns it, entitlements are not enforced at retrieval — a severe finding, testable with pure access-control technique. Also: **attempt to reach three public GenAI services from a standard corporate device** (if they resolve, the preventive control is absent); obtain the pre-deployment accuracy test and check out-of-scope refusal behaviour was tested; determine **where prompts are stored, who can read them and for how long**; and test whether the bank can identify which regulated submissions were AI-assisted — if it cannot, it cannot remediate a systemic error |

---

## D11 — Resilience & Record Keeping

| | |
|---|---|
| **Key risk** | The institution cannot operate when AI fails, and cannot reconstruct or defend decisions AI made in the past |
| **Expected controls** | AI dependencies mapped to critical business services · Documented fallback for each AI supporting a customer or critical process · Retained manual capability with trained staff and capacity planning for fallback volumes · Tested kill switch with defined authority to invoke · AI included in BCP/DR scope and scenario testing · Availability monitoring and SLAs · **Retention of decision records, input data and model versions sufficient to reconstruct and explain historical decisions** across the complaint, dispute and regulatory look-back window · Immutable decision logging · Decommissioning procedure with dependency checks and disposal per retention schedule · Vendor exit with certified data deletion |
| **Evidence** | Critical business service mapping showing AI dependencies · Fallback procedures with evidence of testing within 12 months · Kill switch procedure and authority · BCP/DR test results covering AI scenarios · Availability reporting · Retention schedule covering AI artefacts · Decision log samples · Decommissioning records and disposal certificates · Vendor exit documentation |
| **Example audit test** | 🔴 **The reconstruction test:** pick a real customer decision made 6–12 months ago by a sampled model and ask the bank to reproduce the exact inputs, model version, score, threshold and reason codes. Time it. Inability to reconstruct is a significant finding with direct conduct and regulatory consequence. **Fallback testing:** obtain the fallback procedure for an AI supporting a critical business service and evidence it was tested within 12 months — report an untested procedure as *untested*, not as present. **Inventory vs telemetry:** compare systems marked "retired" against actual production API call logs; retired systems still receiving traffic is a strong finding |

---

## Domain priority — where to concentrate

| Priority | Domains | Rationale |
|---|---|---|
| **Tier 1 — always test** | D2 Inventory · D9 Change/Monitoring/Incidents · D7 AI Security | Highest finding yield; cheapest evidence; most transferable from existing IT audit skill |
| **Tier 2 — test for customer-impacting AI** | D3 Risk Assessment & Approval · D6 Fairness/Explainability/Oversight · D4 Data & Privacy | Highest consequence; direct regulatory and conduct exposure |
| **Tier 3 — test based on estate profile** | D8 Third-Party · D10 GenAI · D5 Development & Validation | Test D8 and D10 heavily if the estate is vendor- and GenAI-dominated (most Malaysian banks in 2026); test D5 heavily if models are built internally |
| **Tier 4 — test at least once per cycle** | D1 Governance · D11 Resilience | Entity-level; changes slowly; but D1 failures explain everything else |

---

# PART 8 — Connecting AI Audit to Traditional IT Audit

## 8.1 The concept, validated

> **"AI Audit does not replace traditional IT Audit. Existing technology controls remain relevant, while AI introduces additional risks such as bias, explainability, model drift, data provenance and human oversight."**

🔴 **This statement is correct, and it is the right framing to present to a Chief Internal Auditor.** Three reasons it holds:

1. **An AI system is a technology system.** It runs on infrastructure, is accessed by identities, is changed through a pipeline, calls APIs, stores data and can fail. Every existing ITGC applies without modification. RMiT does not need an AI chapter to apply to AI.
2. **The majority of realised AI incidents are conventional failures.** Data leaked because entitlements were wrong. A model broke because an upstream feed changed. An endpoint was exposed because it never went through the API gateway. These are IAM, change and architecture failures wearing AI clothing.
3. **The genuinely new risks are additive, not substitutive.** Bias, explainability, drift, provenance and oversight sit *on top of* the existing control set. Nothing is removed.

**One refinement worth making when you present this:** the statement is true but slightly understates the change. AI does not only *add* risks — it **changes the nature of assurance for some existing controls**. Change management is the clearest case: the *control* is unchanged, but the *configuration items* now include model weights, training data and natural-language prompts, and the *trigger* for change now includes the passage of time (drift) and a third party silently updating a model. An auditor who tests AI change management using an unmodified traditional change programme will conclude "adequate" and be wrong.

So the precise formulation is:

> **Existing IT controls remain necessary but are no longer sufficient. AI extends the scope of existing controls to new asset types, and adds a small number of genuinely new control objectives.**

---

## 8.2 Traditional IT audit area → additional AI considerations

| Traditional IT Audit Area | Additional AI Considerations |
|---|---|
| **Identity & Access Management** | Extend scope to: AI/ML platforms, model registries and artefact stores, **training and feature datasets**, prompt and system-instruction repositories, model configuration and threshold settings, inference endpoints, vector/embedding stores, and AI notebooks/workspaces. New identity type: **AI agents and service accounts acting autonomously** — inventory and govern them as privileged non-human accounts with defined scopes. New entitlement question: does the AI system enforce the *end user's* entitlements when retrieving data (RAG), or does it run with a single broad service identity? Verify AI platforms are in the UAR population — they are routinely omitted because they were procured outside core IT |
| **Change Management** | Extend the definition of a change to include: **model version/weights, training dataset, prompts and system instructions, hyperparameters, decision thresholds and cut-offs, guardrail and content-filter configuration, embedding/index refreshes, and third-party model version updates.** New triggers: automated retraining pipelines that can promote to production without human approval; **vendor-initiated model changes the bank did not request and may not be told about.** New requirement: materiality criteria determining when a change triggers re-validation and re-approval. New emergent risk: cumulative small changes that individually fall below the materiality threshold but collectively alter behaviour — requires periodic re-validation independent of change |
| **SDLC** | Extend to the data-centric lifecycle: data sourcing, quality assessment, lineage and labelling precede development and carry equal weight. Add **independent model validation** as a distinct gate separate from UAT — UAT confirms it does what the business asked; validation confirms it works and states its limitations. Add **fairness testing** and **adversarial/prompt-injection testing** to the pre-production test set. Explainability must be a *design-stage requirement*, not a post-build assessment. Testing cannot rely on expected-result comparison for probabilistic systems — expect statistical acceptance criteria and, for GenAI, curated evaluation sets. **Environments:** data science experimentation often happens outside standard environments — test whether production data is used in experimentation and under what controls |
| **Logging & Monitoring** | Extend to: **model input and output logging** sufficient to reconstruct a decision; **prompt and response logging** for GenAI (and recognise this log store as sensitive data in its own right — classify and control it); model version in every decision record; administrator actions on AI platforms; **model performance and drift metrics** as a first-class monitored signal alongside availability; fairness metrics over time; override and exception rates; unusual query patterns indicating model extraction attempts; AI service consumption volume by user and department (shadow AI detection). New control objective: monitoring must detect **silent degradation**, not just outage — a model that is up and wrong looks healthy on every traditional dashboard |
| **Infrastructure & Cloud** | Largely unchanged in principle, extended in scope: GPU/compute environments and their access controls; **data residency for AI processing and for prompt/output storage** (many AI services process in a different region from the primary tenant); encryption at rest for training data, model artefacts, embeddings and prompt logs; key management where a vendor holds keys; API gateway coverage for inference endpoints; network segmentation between AI environments and production data; egress controls preventing model artefact or bulk data exfiltration; availability and capacity for inference workloads. **New:** third-party model hosting may place bank data in an architecture the bank has never reviewed — test the actual data flow, not the marketing diagram |
| **Third-Party Risk** | Extend due diligence to the **AI service specifically**, not just the parent vendor. New contractual requirements: prohibition on training with bank data; model change notification; disclosure of sub-processors and model providers (**the vendor's own AI supply chain** — many SaaS AI vendors are reselling a hyperscaler model); performance SLAs expressed in AI-relevant terms; audit and regulator access. New assurance question: does the vendor hold **ISO/IEC 42001** certification, and what does its scope cover? New risks: concentration on a single model provider across multiple use cases; substitutability and exit where the bank's prompts, fine-tuning and evaluation sets are provider-specific. Verify contractual commitments against **actual tenant configuration** |
| **Resilience** | Extend to: AI dependency mapping for critical business services; **fallback to a non-AI process, with retained manual capability and trained staff** — efficiency programmes frequently decommission the manual path; a tested kill switch with defined invocation authority; capacity planning for fallback volumes (if AI handled 70% of chat volume, the contact centre must be able to absorb it); scenario testing that includes *degradation* as well as outage — "the model is available but performing poorly" is the harder and more likely scenario; provider concentration in scenario design. **New record-keeping dimension:** resilience includes the ability to reconstruct and explain past decisions, which depends on retention of model versions and decision-time inputs |
| **Data Management** | Extend to: provenance and lawful basis for training data; purpose limitation when data collected for one system is reused for AI; proxy-variable analysis; representativeness across segments; data quality monitoring on *production inference inputs*, not only on the build dataset; retention of training data and model artefacts under the PDPA; the **DPIA and Data Protection by Design** requirements now set out in the 2026 JPDP guidelines |
| **Incident Management** | Extend the taxonomy to AI-specific incident types: incorrect/harmful AI output, bias detected in production, drift threshold breach, prompt injection, data leakage via an AI tool, provider model change causing behavioural shift, AI service outage. New detection challenge: **many AI failures surface first as customer complaints, not system alerts** — ensure the complaint channel routes AI issues to the model owner. New assessment: does an AI failure trigger RMiT incident reporting or PDPA breach notification? |

---

## 8.3 What is genuinely new — the honest list

Strip away everything that is existing IT audit in new clothing, and **five** control objectives remain that have no traditional equivalent:

| # | New control objective | Why it has no traditional equivalent |
|---|---|---|
| 1 | **Fairness / non-discrimination** | Traditional systems apply rules uniformly by construction. A learned model can discriminate without anyone intending it or writing it down |
| 2 | **Explainability** | Traditional systems are explainable by reading the code. Explainability is a property you must deliberately engineer into an AI system, and it is often traded against accuracy |
| 3 | **Drift detection** | Traditional systems do not degrade without a change. AI degrades because the world changes. This inverts the change-management assumption that *no change means no risk* |
| 4 | **Data provenance for training** | Traditional systems have no training data. The origin, rights and integrity of training data are a wholly new evidence category |
| 5 | **Human oversight effectiveness** | Traditional automation either ran or did not. AI recommends, and humans defer. Automation bias means the designed control decays in operation without anything visibly changing |

**Everything else on your AI audit programme is IT audit you already know how to do.** That is the reassuring and accurate message to give both yourself and your Chief Internal Auditor.

---

*Next: [06 — Sample Audit Tests](06-Sample-Audit-Tests.md)*
