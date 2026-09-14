# 06 — Sample Audit Tests

Fourteen ready-to-use test cards. Each is written to be executable by an IT auditor **without data science skills**. Where specialist input is genuinely required, the card says so explicitly.

Standard structure: **Control Objective → Risk → Expected Control → Evidence → Audit Procedure → Possible Finding**

Finding wording is written the way it would appear in a report — adapt the numbers to your engagement.

---

## TEST 1 — AI Governance Structure and Policy

**Control Objective**
AI activities are governed by a board-approved policy and an authorised forum with the composition, mandate and evidence of challenge necessary to keep AI risk within appetite.

**Risk**
Without enforceable policy and an effective governance forum, AI decisions are made informally and inconsistently, AI risk is not visible to the board, and Internal Audit has no criteria against which to assert non-compliance.

**Expected Control**
Board-approved AI policy containing mandatory requirements, defined three-lines roles, a prohibited/restricted use list and approval authorities; an AI governance forum with board-approved ToR, quorum rules, mandatory 2nd line membership and escalation to the Board Risk Committee; an articulated AI risk appetite with measured indicators; periodic board reporting; annual policy review.

**Evidence**
AI policy with approval and next-review dates · supporting standards and procedures · forum ToR and membership list · 12 months of minutes with attendance · papers submitted to the forum · delegated authority matrix · risk appetite statement and the actual KRI reports produced · Board/BRC packs containing AI content · training records and completion rates.

**Audit Procedure**
1. Assess the policy for **auditability**: count the number of testable "must" requirements. Confirm it names accountable roles, specifies prohibited uses concretely, sets approval authorities, and covers GenAI and employee use.
2. Confirm board approval and that the document is within its review date.
3. Confirm the policy explicitly resolves the boundary with the existing Model Risk Management framework — which AI systems fall under MRM and which do not.
4. Review 12 months of forum minutes: test quorum at each meeting; test that 2nd line Risk/Compliance and Information Security actually **attended** (not merely were listed as members).
5. Count approvals, deferrals, conditions imposed and refusals. Calculate the approval rate.
6. Trace each stated risk appetite metric to an actual report showing measured values against limits.
7. Confirm AI risk was reported to the Board Risk Committee and inspect what the board received.
8. Sample 15 staff in AI-using functions; test training completion and ask each to state one requirement the policy imposes on them.

**Possible Finding**
> *The AI Policy approved by the Board in [month/year] sets out five principles but contains no mandatory requirements, does not specify approval authorities, and does not define prohibited uses. The AI Governance Forum has no approved terms of reference; across 12 meetings reviewed, Risk Management attended 4 and Information Security attended 2. All 31 papers submitted were approved, with no conditions imposed and no deferrals recorded. The stated AI risk appetite ("AI will be used responsibly and within risk tolerance") has no associated measurable indicator and has never been reported against. Consequently there is no enforceable standard against which AI activity can be assessed, and no evidence that the governance forum exercises independent challenge.*

---

## TEST 2 — AI Inventory Completeness

**Control Objective**
The institution maintains a complete and accurate inventory of all AI systems in use, including third-party and embedded AI, as the foundation for all downstream governance controls.

**Risk**
AI systems outside the inventory are outside every AI governance control — no risk assessment, no validation, no approval, no monitoring — and the institution cannot respond accurately to a regulatory request.

**Expected Control**
Central inventory with a defined data standard and a named owner; a scope definition that explicitly includes embedded and third-party AI; mandatory registration enforced at the procurement and change gates; periodic reconciliation against independent sources; periodic owner re-attestation.

**Evidence**
Raw inventory extract · inventory standard and scope definition · procurement and change gate configuration requiring an inventory reference · reconciliation evidence · attestation records · 12 months of AP and corporate card data · cloud billing detail · web proxy/CASB logs · vendor/contract register · top-20 critical application list.

**Audit Procedure**
1. Obtain the raw inventory extract (not a summary prepared for audit).
2. Test **field completeness across the entire population**: named individual business owner, named technology owner, risk rating, validation date, monitoring status.
3. Build independent populations:
   - 12 months of AP and corporate card spend filtered for AI vendors and terms ("AI", "ML", "copilot", "assistant", "GPT", "model")
   - Cloud billing line items for AI/ML services across **all** subscriptions
   - Proxy/CASB traffic to AI service domains, by department
   - Contract register entries containing AI/ML/algorithm/automation terms
   - For each of the **top 20 critical applications**, ask the vendor manager or review product documentation: does this product include AI/ML features?
4. Reconcile each independent population to the inventory. Categorise every exception.
5. Verify named owners are current employees in the stated roles against HR data.
6. Interview 3 named owners and ask what their AI ownership responsibilities are.
7. Test whether inventory registration is actually enforced — attempt to trace a recently deployed AI system to its registration record and the gate that required it.

**Possible Finding**
> *Management's AI inventory listed 23 systems. Audit identified a further 18 through independent sources, comprising 9 AI capabilities embedded within purchased applications, 5 departmentally procured AI SaaS services, and 4 internally developed models. The inventory is therefore approximately 56% complete. Of the 23 recorded systems, 14 have no risk rating and 6 record a team name rather than a named individual as business owner; 3 named owners have left the institution. Two of three owners interviewed were unaware they were recorded as accountable. Because risk assessment, validation and monitoring requirements are triggered by inventory registration, 18 AI systems currently operate outside all AI governance controls.*

---

## TEST 3 — AI Risk Assessment and Classification

**Control Objective**
Every AI system is risk-assessed before deployment using a consistent methodology, subject to independent challenge, and the resulting rating drives proportionate control requirements.

**Risk**
Without a consistent, challenged risk assessment, high-risk AI receives low-risk treatment, and the proportionality on which the entire governance model depends fails silently.

**Expected Control**
Mandatory standardised risk assessment before build or buy, covering model, data, privacy, security, conduct, third-party and resilience risk; documented rating criteria; 2nd line review and challenge; rating tied to mandatory downstream requirements (validation depth, approval authority, monitoring frequency).

**Evidence**
Risk assessment methodology and template · completed assessments for the full population · evidence of 2nd line challenge (review comments, document versions, sign-offs) · DPIAs · the mapping of risk tier to required controls · approval records showing the tier applied.

**Audit Procedure**
1. Test **across the whole population** whether each production AI system has a completed, in-date risk assessment.
2. Confirm assessments were completed **before** deployment by comparing assessment date to go-live date.
3. **Independently re-rate 5 sampled systems using the institution's own criteria.** Compare to management's rating and document every divergence with the reason.
4. Test for evidence of 2nd line challenge: look for review comments, changed ratings between versions, and named reviewer sign-offs. Identify at least one assessment where challenge changed the outcome.
5. For 3 systems, test that the assigned tier actually triggered the required downstream controls — e.g. a High rating should have produced independent validation and monthly monitoring. Confirm it did.
6. Confirm a DPIA exists wherever personal data is processed at scale or a high-risk basis applies.

**Possible Finding**
> *Of 41 AI systems identified, 22 have no completed risk assessment. For 7 of the 19 assessed, the assessment was completed after production deployment. Audit independently re-rated 5 systems using management's own criteria: in 4 cases audit's rating was one band higher than management's, in each case because the "degree of automation" and "customer impact" dimensions had been scored on the intended future design rather than the deployed configuration. Across all 19 completed assessments there is no evidence that second line review changed any rating or raised any challenge. As risk rating determines validation depth, approval authority and monitoring frequency, systematic under-rating has resulted in [n] customer-impacting systems receiving Medium-risk controls.*

---

## TEST 4 — Data Quality and Provenance for AI

**Control Objective**
Data used to develop and operate AI systems is of assessed quality, of documented origin, lawfully used for the stated purpose, and traceable from source to decision.

**Risk**
Poor or unrepresentative data produces systematically wrong or biased outputs; undocumented provenance means the institution cannot demonstrate lawful use; absent lineage means decisions cannot be reconstructed or explained.

**Expected Control**
Documented data sourcing, provenance and lineage per model; data quality assessment before use against defined dimensions and thresholds; data owner approval for the specific AI purpose; lawful basis and purpose-limitation assessment; prohibited and proxy variable review; access control on training data stores; production input data quality monitoring.

**Evidence**
Data dictionary and lineage documentation · data quality reports with dates and thresholds · the model's production variable list · list of variables considered and excluded, with reasons · data owner approvals · lawful basis assessments and DPIAs · dataset ACLs and access review evidence · production data quality monitoring output.

**Audit Procedure**
1. For a sampled model, obtain the **production variable list** and reconcile it line by line to the data dictionary. List every variable that cannot be traced to a documented source.
2. Obtain the data quality assessment; confirm it was performed **before** development, covers defined dimensions, states thresholds, and that issues identified were remediated or explicitly accepted by a named approver.
3. Confirm a documented review for prohibited and proxy variables took place, and inspect what was excluded and why.
4. Trace one dataset from its original collection purpose to its current AI use; test whether the purpose change was formally assessed and approved.
5. Confirm the data owner approved use of that data **for this purpose**, not merely for the system it originated in.
6. **Run a standard access review on the training data store**: extract the ACL, test for least privilege, confirm the store is in the UAR population, and check the date of last review.
7. Test whether production inference input data quality is monitored — obtain a week of production input statistics and check null/default rates against what the model was built to handle.

**Possible Finding**
> *For the [model name], 11 of 63 production variables could not be traced to the data dictionary or to any documented source. No review for prohibited or proxy variables was performed; the model uses residential postcode with no documented credit-risk justification or disparate-impact analysis. The data quality assessment was completed three weeks after model development concluded and identified a 14% null rate in two variables, which was noted but not remediated or formally accepted. The training data store is not included in the quarterly user access review population; 19 users hold write access, of whom 3 have left the institution. Input data quality is not monitored in production.*

---

## TEST 5 — Access Management for AI Platforms

**Control Objective**
Access to AI platforms, model registries, training data, prompts and inference endpoints is restricted to authorised individuals on a least-privilege basis, and is periodically reviewed.

**Risk**
Excessive or unreviewed access permits unauthorised model or prompt changes, exposure of training data, and unattributable activity in systems that drive customer decisions.

**Expected Control**
AI platforms within the scope of the IAM standard and the user access review cycle; RBAC with least privilege; PAM for administrative roles; MFA; joiner/mover/leaver integration; service and AI-agent identities inventoried and governed; access logging and review.

**Evidence**
AI platform inventory · user and privileged access lists (extracted by audit, not supplied) · UAR scope document and most recent review evidence · PAM coverage report · MFA configuration · HR leaver data · JML tickets · service account inventory · access logs.

**Audit Procedure**
1. Confirm AI platforms, model registries and training data stores are in the **documented UAR scope**. If they are not, that is the finding — record it and continue.
2. Extract the full user list from each in-scope AI platform yourself.
3. Test against HR leaver data for accounts belonging to departed staff and contractors.
4. Identify all privileged/administrator accounts; test each for documented business justification, approval, and PAM coverage.
5. Test MFA enforcement on all accounts, and separately on privileged accounts.
6. Sample 10 joiners and 10 leavers; test timeliness of provisioning and revocation against the standard.
7. Identify **service accounts and AI agent identities**; test whether they are inventoried, have named owners, have scoped permissions, and whether their credentials are rotated.
8. Test that administrator activity is logged and that the log is reviewed by someone independent of the administrators.

**Possible Finding**
> *The enterprise AI platform and the model registry are not included in the quarterly user access review population and have never been subject to a formal access review since implementation in [date]. Audit extracted 147 active user accounts, of which 9 belong to individuals who have left the institution (the longest 11 months after exit date) and 4 to contractors whose engagements ended. 23 accounts hold administrator privileges; 18 have no documented business justification and none are managed through the privileged access management solution. MFA is not enforced for 31 accounts. Seven service accounts hold write access to the production model registry; none has a named owner and none has had credentials rotated since creation.*

---

## TEST 6 — Independent Model Validation

**Control Objective**
AI models are independently validated, proportionate to their risk rating, before approval and deployment, with documented limitations and findings closed before go-live.

**Risk**
Models are deployed without credible independent challenge, so flaws in design, data or performance are not identified until they cause loss or customer harm.

> 🔴 **This test assesses the *governance of validation*. It does not re-perform validation.** See [07 — Specialist Reliance](07-Specialist-Reliance.md).

**Expected Control**
Validation standard defining minimum scope by risk tier; validator independent of the developer, in a separate reporting line; validation against data the model has not seen; performance tested against pre-agreed thresholds; documented limitations and conditions of use; validation findings tracked to closure before deployment; periodic re-validation.

**Evidence**
Validation standard · validation reports with named author and reporting line · org charts · pre-agreed threshold documentation with dates · test data description · results against thresholds · documented limitations · validation finding tracker · approval records and dates · re-validation schedule and completion.

**Audit Procedure**
1. **Independence:** identify by name the developer, the validator and the approver for each sampled model. Trace reporting lines on the org chart. Confirm the validator does not report to the developer's management chain.
2. **Sequencing:** compare the validation report date to the approval date and to the production go-live date. Validation completed after either is a finding, evidenced by dates alone.
3. **Completeness against the institution's own standard:** map the validation report section by section against the required scope for that risk tier. Report every omission.
4. **Thresholds:** confirm acceptance thresholds were documented **before** testing. Check the results against them. Where thresholds were not met, identify who accepted the exception and confirm they had authority under the delegated authority matrix.
5. **Limitations:** confirm the report states limitations and conditions of use, and test whether these were communicated to the users who rely on the model.
6. **Findings closure:** obtain the validation finding tracker; confirm findings were closed before deployment or carried forward with documented risk acceptance.
7. **Quality signal:** review all validation reports issued in the period and count how many raised findings. **A validation function that has never raised a finding is not validating.**
8. **Currency:** confirm re-validation is within the required interval for each High-risk model.

**Possible Finding**
> *For 3 of 5 models sampled, the validation report was authored by a member of the same team that developed the model, reporting to the same Head of Data Science. For the [model name], the validation report is dated 14 March and production deployment occurred on 2 March — validation was completed 12 days after the model began making customer decisions. Acceptance thresholds were not documented in advance for any of the 5 models; in each case the validation report presents observed performance without reference to a pre-agreed standard. None of the 5 validation reports documents model limitations or conditions of use. Across all 11 validation reports issued in the period, no validation finding was raised.*

---

## TEST 7 — Bias and Fairness Governance

**Control Objective**
For AI systems affecting customer outcomes, fairness is defined, measured against a pre-agreed threshold by an independent party before deployment, and monitored thereafter.

**Risk**
The model produces systematically worse outcomes for a group of customers, exposing the institution to conduct, reputational and regulatory consequences — and industrialising that outcome across every application it touches.

> 🔴 **Do not compute fairness statistics yourself.** Test whether the institution defined fairness, measured it independently, and acted on the result. Engage a specialist if you need to assess the adequacy of the *method*.

**Expected Control**
A defined fairness metric and numeric threshold, agreed before testing; disparate-impact testing across a defined and justified set of segments; testing performed by a party independent of the developer; documented acceptance or remediation of results; ongoing fairness monitoring at a defined frequency; escalation path on breach; conduct/Compliance function review of customer-impacting models.

**Evidence**
Fairness requirement documentation with dates · the defined metric and threshold · segment definitions and the rationale for choosing them · fairness test reports with named author · ongoing fairness monitoring output · escalation records · Compliance/Conduct review sign-off · prohibited variable list.

**Audit Procedure**
1. Confirm a fairness requirement exists for the model, with a **named metric and a numeric threshold**, and establish the date it was agreed relative to the date testing was performed.
2. Obtain the segment definitions used and ask who decided them and on what basis. Assess whether obvious relevant segments were omitted.
3. Confirm the test was performed by someone independent of the model developer.
4. Compare results to the threshold. Where the threshold was breached, trace the decision — who accepted it, on what rationale, with what authority?
5. Confirm whether fairness is re-tested on a defined cycle or was assessed only at launch. Obtain the most recent monitoring output and check its date.
6. Confirm the Compliance/Conduct function reviewed the model and that AI-driven outcomes feed the institution's conduct risk monitoring.
7. Confirm a prohibited-variable list exists and that the model's variables were checked against it.

**Possible Finding**
> *The institution has not defined what constitutes a fair outcome for any of its customer-impacting AI models. For the [model name], a disparate-impact analysis was performed by the model development team in [month] but no acceptance threshold had been agreed beforehand; the report presents approval rate differentials across three segments without stating whether these are acceptable. Segment definitions were selected by the development team with no documented rationale and no Compliance input. Fairness has not been re-assessed in the 19 months since deployment, and no fairness metric is included in the model's monitoring plan. Compliance has not reviewed any AI model for conduct implications.*

---

## TEST 8 — Explainability

**Control Objective**
The institution can explain individual AI-driven decisions to the customers affected, to its own staff, and to the regulator, proportionate to the decision's impact.

**Risk**
The institution cannot justify or defend a decision, cannot handle a complaint or Ombudsman referral, and cannot demonstrate to BNM that its decisioning is sound.

**Expected Control**
Explainability requirement defined at design stage, proportionate to impact, and used to constrain model selection; reason codes generated and stored with each decision; an adverse-action explanation process for customer-facing decisions; documented limitations disclosed to approvers and users; front-line staff trained to explain outcomes.

**Evidence**
Design documentation showing the explainability requirement and its date · explainability assessment · sample decision records including stored reason codes · **actual adverse-action communications sent to customers** · front-line procedures and training material · complaints relating to unexplained decisions · the model documentation given to approvers.

**Audit Procedure**
1. Obtain the design document and confirm an explainability requirement was defined **before** model selection. Check whether it constrained the choice of model.
2. Obtain a sample of stored decision records and confirm reason codes are captured and retained with each decision.
3. **Obtain a real adverse-action letter sent to a customer** and assess whether it gives a meaningful, specific reason or only a generic outcome statement.
4. 🔴 **Ask a front-line officer to explain a specific decline to you, using the tools they have.** If they cannot, explanation does not exist operationally regardless of the technical documentation.
5. Review complaints data for cases where the customer challenged an unexplained decision, and assess how the institution responded.
6. Confirm documented model limitations were included in the package given to the approver.

**Possible Finding**
> *The [model name] was selected on predictive performance alone; no explainability requirement was defined at design stage and none appears in the solution design document. Reason codes are not generated or stored with decisions. Adverse-action communications reviewed state only "we are unable to approve your application at this time" with no reason. Two branch officers asked to explain specific declines were unable to do so and stated their practice is to advise customers to reapply after six months. Eleven complaints in the period related to unexplained credit declines; in each case the institution's response repeated the generic outcome statement. The institution would be unable to substantiate the basis of individual credit decisions to BNM or to the Ombudsman for Financial Services.*

---

## TEST 9 — Human Oversight Effectiveness

**Control Objective**
Where a human is designated as a control over AI output, that person has the information, authority, time and competence to exercise meaningful judgement — and does so.

**Risk**
Automation bias reduces the designed control to a formality; the institution believes a human control exists while in substance the AI decides.

**Expected Control**
Documented human oversight model approved at the appropriate level; reviewers presented with the model's output, confidence and known limitations; genuine authority to override without disproportionate friction; adequate time allocated; competence requirements and training; override rate monitored with expected ranges; QA sampling of human reviews.

**Evidence**
Design documentation stating the oversight model · reviewer screen/interface · override statistics with trend · system timestamps showing time between presentation and decision · reviewer training records · QA sampling results · escalation procedure · interviews and direct observation.

**Audit Procedure**
1. Confirm the human oversight model is explicitly documented and approved, and that it matches what happens operationally.
2. 🔴 **Obtain the override rate and trend it over 12 months.** A rate near 0% or near 100% both indicate the control is not functioning as designed.
3. Sample 15 reviewed cases and extract system timestamps for the interval between the recommendation being presented and the decision being recorded.
4. **Observe the control being performed.** Sit with a reviewer. Note what information they actually see — is the confidence score visible? Are the model's limitations available to them?
5. Interview 3 reviewers: do they know the model's known weaknesses? Have they ever overridden it? What happened when they did?
6. Test whether overriding carries friction or consequence — an escalation queue, a justification requirement, a performance metric that penalises it.
7. Confirm QA sampling of human reviews is performed and inspect the results.

**Possible Finding**
> *The [process] is documented as operating with a human-in-the-loop control, with credit officers required to review every model recommendation before decision. The override rate across 12 months is 0.3%. Timestamp analysis of 15 sampled cases shows a median interval of 4 seconds between the recommendation being displayed and the decision being recorded. The reviewer interface displays only the recommended outcome; the model's confidence score and documented limitations are not visible. None of the three officers interviewed was aware of any limitation of the model, and all three stated that overriding requires completion of a justification form and referral to a queue with a three-day turnaround. No quality assurance sampling of human reviews is performed. The designed human control is not operating effectively.*

---

## TEST 10 — Change Management for AI Assets

**Control Objective**
All changes to AI systems — including models, training data, prompts, parameters and thresholds — are authorised, tested, approved and recorded, and material changes trigger re-validation.

**Risk**
Uncontrolled change alters the institution's risk profile without approval or visibility; prompts and retraining routinely bypass change management entirely.

**Expected Control**
Change policy explicitly covering models, training data, prompts, hyperparameters, thresholds and guardrail configuration; materiality criteria triggering re-validation and re-approval; automated retraining requiring human approval before production promotion; prompts under version control with an approval workflow; SoD preventing developer deployment to production; vendor model change notification and impact assessment.

**Evidence**
Change policy text · change records for AI systems over the period · prompt version history from the platform · retraining logs and approval records · re-validation reports · production deployment access list · vendor change notifications received and the assessments performed · CAB minutes.

**Audit Procedure**
1. Read the change policy and test whether its definition of a configuration item covers models, training data, **prompts**, parameters and thresholds. Absence here is a design gap reportable without further testing.
2. Obtain all AI-related change records for 12 months. Test a sample for authorisation, testing evidence, approval and back-out plan.
3. 🔴 **Prompt change test:** obtain the system prompt version history directly from the AI platform. Compare every change to formal change records. Quantify the gap.
4. **Retraining test:** obtain retraining logs. For each production model update, confirm human approval occurred before promotion, and confirm re-validation where materiality criteria were met.
5. **Version reconciliation:** identify the model version currently serving production. Trace it to the validation report, the approval record and the change record. Report any break in the chain.
6. **SoD:** obtain the list of accounts with production deployment rights for AI systems and confirm no model developer holds standing rights.
7. **Vendor change:** obtain every model-version notification received from AI providers in 12 months and the institution's impact assessment of each.

**Possible Finding**
> *The Change Management Policy defines configuration items by reference to application code and infrastructure; it does not address models, training data, prompts or decision thresholds. The system prompt for the [chatbot] has been modified 34 times in 12 months, as evidenced by platform version history. No corresponding change records exist; changes are made directly in the vendor console by four members of the development team, three of whom also hold production deployment rights. The customer-facing behaviour of the chatbot has therefore been altered 34 times without authorisation, testing or approval. Separately, the [model name] was retrained and promoted to production on three occasions with no human approval step, as the retraining pipeline is configured to promote automatically on meeting an accuracy threshold. No re-validation was performed. The institution received two model version change notifications from its AI provider during the period; neither was assessed.*

---

## TEST 11 — Monitoring and Model Drift

**Control Objective**
AI system performance is monitored against defined thresholds throughout its operational life, degradation is detected, and threshold breaches receive a documented response.

**Risk**
Model performance degrades silently as data and conditions change; the institution continues to rely on a model that no longer works, and would not know.

**Expected Control**
Monitoring plan per model specifying metrics, thresholds, frequency, owner and escalation path; drift detection on inputs and outputs; periodic performance reporting to a governance forum; recurring fairness monitoring for customer-impacting models; override rate tracking; defined retraining triggers; documented response to every breach.

**Evidence**
Monitoring plans · 12 months of monitoring output · threshold definitions with the date they were set · breach records and the response to each · governance forum packs containing AI performance reporting and the minutes discussing them · retraining trigger definitions · escalation records.

**Audit Procedure**
1. Confirm a monitoring plan exists for each sampled model and that it addresses **performance and drift**, not merely system availability.
2. Obtain 12 months of monitoring output and test **continuity** — identify any period where monitoring did not occur.
3. Confirm thresholds were defined **in advance** and are not being read off the chart retrospectively. Check the date the threshold document was created.
4. 🔴 **Identify every threshold breach in the period and trace each to a documented response.** Quantify breaches with no recorded response.
5. Confirm monitoring results were reported to a governance forum, and inspect the **minutes** — not just the existence of a dashboard — for evidence the forum discussed them.
6. For customer-impacting models, confirm fairness is included in ongoing monitoring, not assessed only at launch.
7. Confirm retraining triggers are defined and test whether any trigger was met and not acted upon.

**Possible Finding**
> *Of 10 production models sampled, 4 have no monitoring plan and no performance monitoring has been performed since deployment. For the 6 with monitoring, thresholds are documented for 2; in the remaining 4 the monitoring report presents metrics with no reference point. Monitoring output for the [model name] shows the alert-to-suspicious-report conversion rate falling from 6.1% to 1.8% over 11 months, crossing the documented threshold in month 7. No escalation, investigation or response is recorded for this breach, and monitoring reports for this model have not been presented to any governance forum. Fairness is not monitored for any model after deployment. The institution would not detect material degradation of models supporting credit, fraud and AML outcomes.*

---

## TEST 12 — AI Security (including Prompt Injection)

**Control Objective**
AI systems are subject to the institution's security control standards and are additionally tested against AI-specific attack vectors, with the AI's own privileges constrained to limit blast radius.

**Risk**
AI endpoints escape conventional security governance; untrusted input manipulates model behaviour; an AI system with broad permissions becomes a route to data or transactions.

**Expected Control**
AI endpoints registered in the API inventory and behind the API gateway with authentication, authorisation, rate limiting and TLS; AI systems in scope for vulnerability management and penetration testing; adversarial and prompt-injection testing before go-live and after material change, covering **indirect** injection via documents and retrieved content; input sanitisation and output validation; least privilege on the AI's downstream permissions; integrity controls on training data and model artefacts; approved-source policy for external models.

**Evidence**
API inventory and gateway configuration · penetration test scope and reports · adversarial/prompt-injection test reports · AI service identity permissions and API scopes · input validation and guardrail configuration · training data store ACLs and integrity controls · approved model source list and integrity verification records · vulnerability scan coverage.

**Audit Procedure**
1. Reconcile the AI inventory to the **API inventory** and to the **penetration test schedule**. Report AI endpoints absent from either.
2. For 3 AI endpoints, test authentication requirement, TLS configuration, rate limiting and API gateway coverage.
3. Obtain the prompt-injection/adversarial test report. Confirm it exists, was performed before go-live, and — critically — **check whether its scope covered indirect injection via uploaded documents and retrieved content**, not only direct user prompts.
4. 🔴 **Blast radius enumeration:** obtain the permissions, API scopes and entitlements held by the AI system's service identity. Document what it could do if fully manipulated. Assess against least privilege.
5. Confirm that AI-extracted values feeding a decision are subject to human or rules-based verification before being relied upon.
6. Test training data store integrity controls: who can write, is write access logged, is the log reviewed?
7. For externally sourced models and datasets, confirm source approval, licence review and integrity verification are documented. Test whether developers can pull directly from public model hubs into the build pipeline.

**Possible Finding**
> *Six of eleven AI inference endpoints are not recorded in the API inventory and are not covered by the API gateway; three of these accept requests without authentication from within the corporate network. No AI system has been included in the scope of a penetration test. Prompt injection testing was performed for the [chatbot] but covered direct user prompts only; the [document processing] system, which ingests customer-supplied PDFs and whose extracted values populate the credit application, has never been tested for indirect prompt injection. The service identity used by the document processing system holds read and write access to the full customer document repository and the loan origination API, substantially exceeding the access required for its function.*

---

## TEST 13 — Third-Party AI Governance

**Control Objective**
Third-party AI services are subject to due diligence, contractual protection and ongoing oversight commensurate with the institution's reliance on them, and contractual commitments are verified in the live configuration.

**Risk**
Vendors use bank data for their own purposes, change models without notice, process data in unapproved locations, or cannot be exited — with the institution unable to demonstrate control to BNM.

**Expected Control**
AI-specific due diligence on the service, not just the vendor; documented outsourcing determination assessed against BNM outsourcing requirements and RMiT; contract covering data use and explicit no-training commitment, data location, sub-processors, retention and deletion, model change notification, SLAs, audit and regulator access, and exit; FSA s.134 secrecy assessment where customer information is disclosed; assurance reports obtained **and reviewed including exceptions and CUECs**; configuration verified against contract; concentration assessment; tested exit plan.

**Evidence**
Vendor list with criticality and outsourcing determination · due diligence files with dates · executed contracts and schedules · assurance reports (SOC 2 / ISO 27001 / ISO 42001) and the institution's documented review · **tenant configuration evidence** · secrecy assessments · concentration assessment and the forum record · exit plans · vendor change notifications and assessments.

**Audit Procedure**
1. Review 5 AI vendor contracts against a clause checklist. Record the presence or absence of each required clause. **Flag every contract silent on the vendor training its models using bank data.**
2. Confirm an outsourcing determination was made and documented for each, with reference to the applicable BNM requirements.
3. Confirm a documented FSA s.134 / banking secrecy assessment exists wherever customer information is disclosed to the vendor.
4. 🔴 **Test the CUECs.** Obtain the vendor's SOC 2 report, extract the complementary user entity controls, and test whether the institution operates each one. Also read the exceptions section and confirm the institution assessed their relevance.
5. 🔴 **Verify configuration against contract.** For an enterprise AI service with a contractual no-training or retention commitment, obtain the **actual tenant configuration** (screenshot or export). Do not accept the contract as evidence that the setting is applied.
6. Map AI systems to providers and to critical business services. Confirm a concentration assessment exists and was considered by a risk forum.
7. For the most critical AI-dependent service, test whether a documented and **tested** exit or fallback exists.

**Possible Finding**
> *Of 5 AI vendor contracts reviewed, 4 contain no provision restricting the vendor's use of institution data for model training, and none requires notification of changes to the underlying model. The [vendor] service processes customer transaction data; no FSA s.134 permitted disclosure assessment was performed and the contract does not specify a processing location. The vendor's SOC 2 Type II report identifies 9 complementary user entity controls; the institution has not identified these and operates 3 of them. For the [enterprise AI service], the contract states that customer data will not be used for model training; audit inspection of the tenant configuration found the corresponding setting was not enabled. Four of the institution's five most significant AI use cases depend on a single model provider; no concentration risk assessment has been performed.*

---

## TEST 14 — Generative AI Controls (Enterprise Deployment)

**Control Objective**
Generative AI is made available to staff and customers through approved channels with enforced data protection, entitlement enforcement, output quality controls and defined boundaries of permitted use.

**Risk**
Confidential and customer information leaves the institution through unapproved tools; the assistant surfaces information users are not entitled to see; inaccurate output enters regulated processes; customers rely on incorrect AI statements.

**Expected Control**
Approved enterprise GenAI service with contractual no-training and defined retention; public GenAI services blocked at the network/CASB layer; acceptable use policy with training and attestation; DLP covering AI endpoints; **retrieval enforces the individual user's existing document entitlements**; defined list of processes where GenAI output may and may not be used; mandatory human review with retained accountability for regulated outputs; customer-facing AI disclosure and human escalation; prompt and output logging with the log store itself classified and access-controlled; pre-deployment accuracy testing and ongoing output sampling.

**Evidence**
Approved/blocked service list and proxy configuration · tenant configuration evidence · acceptable use policy, communications and training completion rates · DLP rules and alert triage records · RAG architecture documentation and entitlement design · accuracy test methodology and results · output sampling programme and findings · permitted/prohibited process list · sample AI-assisted regulated outputs · customer-facing disclosure · prompt log configuration, retention period and ACL.

**Audit Procedure**
1. 🔴 **RAG entitlement test (with prior authorisation).** Using a test account with restricted permissions, query the enterprise assistant for information contained in a document that account cannot open directly. If the assistant returns it, entitlements are not enforced at retrieval.
2. 🔴 **Blocking test (with prior authorisation).** From a standard corporate device, attempt to reach three major public GenAI services. If they resolve, the preventive control is absent. Corroborate with proxy log volume to AI domains.
3. Obtain the tenant configuration for the approved enterprise service and confirm training opt-out and retention settings match the contract and policy.
4. Review DLP rules covering AI endpoints; sample alerts and confirm they were triaged.
5. Obtain the pre-deployment accuracy test: what question set, built by whom, what pass threshold, what results? Confirm **out-of-scope behaviour** was tested — does it refuse, or improvise?
6. Obtain the output sampling programme: what percentage of interactions are reviewed, by whom, against what criteria, and what happened to errors found?
7. Determine **where prompts and outputs are stored, who can access that store, and for how long it is retained.** Test the ACL.
8. Confirm the permitted/prohibited process list exists and was formally approved. For one regulated process where GenAI is permitted, sample outputs and test for evidence of human review before submission.
9. For customer-facing GenAI, confirm AI disclosure is present and walk through escalation to a human.
10. Test whether the institution can identify which outputs in a regulated process were AI-assisted.

**Possible Finding**
> *Public generative AI services are not blocked; proxy logs record 41,300 sessions to three major public AI services across 612 distinct users in the last quarter, including 2,140 file upload events. The acceptable use policy addressing generative AI was issued in [month] but training completion stands at 31%. DLP rules do not cover AI service endpoints. For the approved enterprise assistant, audit's restricted test account successfully retrieved content from three HR documents that the account could not open directly in the source repository, indicating that user entitlements are not enforced at retrieval. Prompts and responses are retained for 24 months in a store accessible to 38 platform administrators; the store is not classified and is not subject to access review. No pre-deployment accuracy testing was performed and no ongoing output sampling is in place. The institution is unable to identify which submissions in [regulated process] were AI-assisted.*

---

## Using these tests

**Sequencing advice:** run Tests 2 (Inventory), 5 (Access) and 10 (Change) early. They are cheap, they use techniques you already have, and they produce findings that reshape the rest of the engagement — particularly Test 2, which usually expands the audit universe.

**Evidence discipline:** for Tests 5, 10, 11 and 13, insist on **system-extracted evidence**. A spreadsheet prepared by the team you are auditing is not an access list; it is an assertion about an access list.

**Authorisation:** Tests 12 and 14 include active testing. Obtain written authorisation from the Head of IT Audit and notify the CISO before performing any test that touches production systems or attempts to access restricted content.

---

*Next: [07 — Role of Specialists](07-Specialist-Reliance.md)*
