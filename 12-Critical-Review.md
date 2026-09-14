# 12 — Critical Review

> **Reviewer's position:** Head of IT Audit, reviewing this proposed AI Governance Audit methodology before committing resource to it. My job here is to find what will fail in practice, not to endorse it.

---

## 1. What is strong about the approach?

**It is anchored on enforceable criteria.** The decision to hang hard findings on RMiT and the PDPA rather than on voluntary AI guidance is the single best judgement in this methodology. It means the audit can issue findings management cannot dismiss, in a domain where most audit functions are still writing advisory observations nobody actions. The three-tier criteria labelling in [03 §3.3](03-Malaysian-Landscape.md) should be adopted as standard practice across the function, not just for AI.

**The scope boundary is stated honestly.** "We audit whether validation happened; we do not perform validation" — with a scope limitation paragraph drafted in advance — is professionally correct and protects the function. I have seen AI audit reports that imply model assurance the team never performed. That is a reputational exposure for Internal Audit, not just a methodological weakness.

**Inventory completeness is treated as a testable assertion rather than a given.** The independent-source triangulation technique is genuinely good and transfers directly from asset management audit. It will produce the most important finding of the first engagement.

**The tests are executable.** [06](06-Sample-Audit-Tests.md) contains tests my current team could perform on Monday. Prompt version history versus change records; override rate and decision timestamps; validation date versus go-live date; CUEC testing; tenant configuration versus contract. These are concrete, evidence-based and defensible. That is rarer in AI audit material than it should be.

**The GenAI-as-overlay decision is correct.** Treating GenAI as a twelfth silo would have caused the team to rebuild access and change testing badly. Framing Copilot as a third-party cloud service fed by document repositories is right, and the RAG entitlement test that follows from it is the highest-value GenAI test available.

---

## 2. What is overly theoretical?

**The eight-dimension weighted risk scoring model.** Scoring eight dimensions 1–5 with percentage weights to two decimal places produces false precision. In practice, two or three auditors scoring the same system will diverge, and the 3.49/3.50 boundary will be argued rather than the underlying risk. **Recommendation: keep the dimensions as a structured discussion checklist, drop the weights and the arithmetic, and rely on the mandatory escalation overrides — which are the part that actually works — plus documented auditor judgement.** The overrides do 80% of the job on their own.

**The eleven-domain structure.** Eleven domains is one or two too many for a first engagement and will fragment the report. D1 (Governance) and D3 (Risk Assessment & Approval) overlap substantially in evidence. D11 (Resilience & Record Keeping) is two different things stapled together — resilience belongs with the operational resilience audit, record keeping belongs with D4. **Recommendation: run the first engagement on eight domains and let the structure earn its complexity.**

**The six-phase timeline.** Twelve weeks assumes cooperative stakeholders, an existing inventory to challenge, and no competing priorities. For a first AI audit in an institution with no AI policy and a contested inventory, sixteen to eighteen weeks is realistic. **Budget the honest number or the engagement will be reported as overrunning when it is in fact performing normally.**

**The six-month personal development plan.** Month-by-month development plans rarely survive contact with an audit plan. The useful version is the shortcut already noted in [10 §10.6](10-Transferable-Skills.md): do the inventory first. I would delete the rest and keep that sentence.

**"85% is existing IT audit."** This is broadly true and rhetorically useful, but it is a comfort claim and should not be repeated to the Audit Committee without qualification. The 15% that is new — fairness, explainability, drift, provenance, oversight effectiveness — is precisely where the customer harm and the regulatory attention sit. **We would be judged on the 15%, not the 85%.** See §7.

---

## 3. What is missing?

**Auditing the second line, specifically.** The methodology audits AI systems and the governance around them, but does not explicitly assess whether the second line AI risk function is adequately resourced, competent and independent. In most institutions this is a one- or two-person function with no authority and a queue. **If second line cannot challenge, no amount of first line process will help — and that is a finding about the control environment that should be reached deliberately, not incidentally.**

**Internal Audit's own use of AI.** The pack says nothing about AI used within the audit function itself — analytics tools, GenAI-assisted working paper drafting, automated testing. If we are auditing shadow AI while using unapproved GenAI ourselves, that will be raised, and rightly. **We need our own position documented before we start.**

**Independence where Internal Audit has advised.** If this function has been consulted on the design of the AI governance framework — which is likely, given how new this is — we cannot then provide assurance over what we helped design without addressing it. **The methodology should require an independence assessment in Phase 0 and disclosure in the report.**

**Agentic AI.** The pack mentions it briefly in [01](01-AI-Governance-Fundamentals.md) as nice-to-know. Given the direction of adoption in 2026, an AI system permitted to take actions — call APIs, update records, initiate payments — is a materially different risk from one that produces text. **The privileged access framing is right, but this needs to be a first-class part of the risk register and the audit programme, not a footnote.** I would expect us to face this within one audit cycle.

**Model risk aggregation.** The methodology assesses individual systems and the governance around them, but does not address whether the institution understands its **aggregate** AI exposure — how many decisions across the bank depend on models, what correlated failure looks like, whether the same provider or the same underlying model sits behind multiple critical processes. Concentration risk is touched on in D8 but only at provider level.

**Cost of remediation.** Findings without a realistic view of remediation effort produce agreed actions with dates nobody can meet. Retrofitting explainability into a deployed model is not a policy update; it may mean rebuilding it. **The methodology should require an effort assessment before an action date is agreed.**

**What happens when BNM issues something.** The methodology is well positioned for the current state but has no trigger for reassessment. **Add an explicit criteria review at the start of every engagement and on publication of any BNM AI instrument.**

---

## 4. Which areas need specialist support?

[07](07-Specialist-Reliance.md) covers this well, but I would sharpen three points.

**Five days of data science input is optimistic if we intend to opine on validation quality.** Five days buys a review of two or three validation reports and a written opinion. It does not buy an assessment of whether the institution's validation *standard* is fit for purpose, which is the more important question. **Either scope the conclusion to "validation occurred and followed the institution's standard" — and say nothing about whether the standard is adequate — or budget properly.** I would rather we said less, credibly.

**Fairness is the genuine capability gap, and the methodology understates it.** Testing whether a fairness threshold was defined in advance is necessary but not sufficient. An institution can define a metric, test against it, pass, and still produce discriminatory outcomes — if the metric was the wrong one, or the segments tested were chosen to avoid the problem. **Our governance-only test would conclude "process followed" in that scenario.** That is a real limitation and it must be disclosed, not glossed. If the Audit Committee wants assurance on fairness outcomes rather than fairness process, that is a co-sourced engagement.

**Legal input on criteria tiering is not optional.** The legal force of the 2026 JPDP guidelines determines whether privacy findings are Tier 1 or Tier 2. Getting that wrong in either direction damages us. **Obtain a written Legal view in Phase 0 and keep it on file.**

---

## 5. Which parts are most relevant to system / application audit?

Directly reusable within existing application audit work, with no separate AI engagement required:

| Domain | Application audit relevance |
|---|---|
| **D5 Development, Acquisition & Validation** | Extends the SDLC audit programme: add independent validation as a gate distinct from UAT, add fairness and adversarial testing to the pre-production test set, add version reconciliation between the deployed artefact and the approved one |
| **D9 Change Management** | Extends the change audit programme: add models, training data, prompts, thresholds and vendor model updates to the configuration item definition. **This is the single highest-value extension to existing application audit work** |
| **D6 Fairness, Explainability & Human Oversight** | Belongs in the audit of the *business application* that embeds the model — the loan origination system, the claims system. Override rates, reviewer interfaces and adverse-action letters are application-level artefacts |
| **D4 Data Governance** | Variable-to-dictionary reconciliation, data owner approval, input data quality monitoring — all application-layer |
| **D2 Inventory** | Should be folded into application inventory and CMDB completeness testing rather than run as a separate exercise indefinitely |

**Practical recommendation:** rather than running AI audits as standalone engagements forever, **fold D5, D6 and D9 into the standard application audit programme within two cycles.** Any application audit touching a system with an embedded model should test these as a matter of course. That is how this becomes sustainable rather than a permanent specialist overhead.

---

## 6. Which parts are most relevant to infrastructure audit?

| Domain | Infrastructure audit relevance |
|---|---|
| **D7 AI Security** | Endpoint registration in the API inventory and gateway coverage, authentication, rate limiting, TLS, vulnerability scanning and penetration test scope — all infrastructure-layer, all directly testable by the existing team |
| **D8 Third-Party & Cloud AI** | AI services are cloud services. Data residency, tenant configuration, encryption, key management, sub-processor disclosure, CUEC testing — this is cloud security audit |
| **Access management (within D7)** | Model registries, training data stores, GPU compute environments, prompt repositories, and **AI agent service identities** all need to enter the IAM and UAR populations. This is an infrastructure entitlement problem |
| **D11 Resilience** | Inference workload availability and capacity, failover, provider outage scenarios, kill switch — operational resilience and DR testing |
| **Logging (within D7 and D9)** | Log generation, retention, protection and review for AI platforms — including recognising the prompt/output store as a sensitive data repository in its own right |

**Practical recommendation:** the fastest route to credible AI coverage is **adding AI platforms to the scope of the next scheduled cloud security and IAM audits.** No new methodology, no specialist, and it produces findings. I would do this regardless of whether a dedicated AI engagement is approved.

---

## 7. Where could the audit approach fail?

Seven failure modes, in order of likelihood.

**1. We deliver an inventory and call it assurance.** The methodology correctly identifies inventory as the foundation and warns that a third of effort goes there. The risk is that we spend 60% of the engagement on it, produce an excellent completeness finding, and give the Audit Committee almost nothing about whether the AI making credit decisions actually works. **Mitigation: timebox the inventory. Report the completeness percentage with whatever confidence we have at the deadline and move on.**

**2. We conclude "process followed" on a model that is producing harm.** This is the most serious failure mode and it is inherent in a governance-only approach. Every gate can be passed, every document present, and the model still discriminatory or degraded. **Mitigation: pair the governance tests with the three outcome-facing tests that need no specialism — the reconstruction test, the adverse-action letter test, and asking a front-line officer to explain a decline. Outcome evidence is the check on process evidence.**

**3. Management disputes the criteria and we lose the report.** If we tier wrongly — or tier correctly but cannot defend it — the closing meeting becomes an argument about legitimacy rather than risk. **Mitigation: Legal sign-off on tiering in Phase 0; criteria matrix shared with management before fieldwork, not at the draft report stage.**

**4. We cannot get the data.** Inventory triangulation depends on accounts payable extracts, cloud billing detail and proxy logs. Procurement, Finance and the CISO all have to cooperate, and at least one will treat it as a fishing expedition. **Mitigation: secure data access commitments in the terms of reference, approved by the CAE, before Phase 1.**

**5. The estate changes faster than we report.** Twelve to eighteen weeks of fieldwork against an estate growing at the observed rate means the report describes a landscape that no longer exists. **Mitigation: state the as-at date prominently, and get the continuous monitoring phase funded. Without Phase 6 this is a one-off snapshot with a short shelf life.**

**6. We over-index on GenAI.** GenAI is visible, topical and interesting. Classical ML in credit scoring, ECL and AML is where the regulatory and financial exposure actually concentrates, and it is duller to audit. **Mitigation: enforce the sampling stratification and require at least three classical ML use cases in the sample.**

**7. Findings are agreed and not remediated.** Tier 2 and Tier 3 findings — expected practice and good practice — have a poor remediation record everywhere. Half this report will be Tier 2. **Mitigation: fewer, better-prioritised findings with realistic effort assessments, and escalate the aggregate governance weakness as a single Tier 1 issue rather than dispersing it across a dozen advisory points.**

---

## 8. Which audit domains should receive the most attention?

My ranking, which differs from the pack's in two places.

| Rank | Domain | Why |
|---|---|---|
| **1** | **D2 Inventory & Classification** | Everything depends on it, and it is where the first engagement delivers most |
| **2** | **D9 Change, Monitoring & Incident Management** | Reliably the weakest area, cheapest evidence, highest finding yield. Prompt change control alone justifies the domain |
| **3** | **D6 Fairness, Explainability & Human Oversight** | 🔺 *Higher than the pack ranks it.* This is where customer harm occurs and where BNM's attention is going. Our limitations here are real, but the override-rate and explanation tests are strong and cost almost nothing |
| **4** | **D7 AI Security** | Our strongest capability, fast to execute, unambiguous findings. Do it early to build credibility |
| **5** | **D8 Third-Party & Cloud AI** | Most of the estate is vendor-supplied. CUEC testing and configuration-versus-contract verification are high-yield and underused |
| **6** | **D1 Governance & Policy** | Entity-level and important, but slow-moving and easy to describe without testing. Do it once properly, then refresh |
| **7** | **D3 Risk Assessment & Approval** | 🔻 *Lower than the pack ranks it.* Largely evidenced through D1 and D2 testing; running it as a separate domain duplicates effort |
| **8** | **D4 Data Governance & Privacy** | Important but substantially covered by the DPO's own programme and any existing data governance audit. Coordinate rather than duplicate |
| **9** | **D5 Development & Validation** | Fold into application audit rather than running separately |
| **10** | **D11 Resilience** | Fold into the operational resilience audit |
| **11** | **D10 GenAI** | Correctly an overlay. Test it through D2, D7, D8 and D9, not separately |

---

## 9. What should be simplified?

1. **Drop the weighted risk score.** Keep the dimensions as a checklist and the escalation overrides as the decision rule.
2. **Eight domains, not eleven,** for the first engagement. Merge D3 into D1, D11 into D4 and the resilience audit, D5 into application audit.
3. **One structuring reference, chosen once, never revisited mid-engagement.** NIST AI RMF. Stop debating it.
4. **One criteria matrix page, not ten framework descriptions.** Nobody on the team will read [03](03-Malaysian-Landscape.md) twice; they will use the one-page matrix.
5. **Five core tests for the first engagement,** not fourteen. The "if you only do five tests" list in [11](11-Cheat-Sheet.md) is the right starting programme; add the rest in cycle two.
6. **Delete the six-month development plan** and replace it with: read the criteria, then build the inventory.
7. **One report structure for AI findings** that the team uses every time — criteria tier, condition, consequence in business language, root cause, action, owner, date.

---

## 10. How could the overall methodology be improved?

**Ten changes, in priority order.**

1. **Add outcome-facing tests as a mandatory counterweight to process testing.** The reconstruction test, the adverse-action letter test and the front-line explanation test must be in every engagement. They are the only defence against concluding "process followed" on a system that is causing harm, and none requires a specialist.

2. **Assess the second line explicitly.** Add a domain or a standing section on whether the AI risk and validation functions have the resource, competence, independence and authority to challenge. If they do not, that is the headline finding.

3. **Make agentic AI a first-class risk, not a footnote.** Any AI permitted to take actions should be automatically High-risk, inventoried as a privileged non-human identity, and subject to blast-radius enumeration. We will be auditing this within a cycle.

4. **Fold AI into existing audits rather than running standalone AI audits indefinitely.** Add AI platforms to the next cloud and IAM audits now. Add AI configuration items to the change audit programme. Add validation, fairness and oversight to the application audit programme. Within two cycles this should be embedded, not separate.

5. **Get the continuous monitoring phase funded, or accept a short shelf life.** A quarterly reconciliation of the inventory against procurement and cloud billing is largely automatable and is the difference between a living audit universe and a snapshot. Cost it and put it in the plan.

6. **Require an effort assessment before agreeing action dates.** Retrofitting explainability or re-validating a portfolio of models is a programme, not a policy update. Dates agreed without this will slip and the follow-up report will look worse than the original.

7. **Secure data access in the terms of reference.** AP extracts, cloud billing, proxy logs, HR data, tenant configuration. Get it agreed by the CAE before Phase 1 rather than negotiating it mid-fieldwork.

8. **Document Internal Audit's own AI position before starting.** What AI does this function use, under what approval? We cannot credibly audit shadow AI while running our own.

9. **Add an independence assessment to Phase 0** covering any advisory work this function has done on the AI framework, and disclose it in the report.

10. **Build aggregate exposure into the reporting.** How many decisions across the institution depend on models, what correlated failure looks like, and whether one provider or one underlying model sits behind multiple critical processes. The Board needs a portfolio view, not a list of eleven domain conclusions.

---

## Reviewer's conclusion

**Approved to proceed, with conditions.**

This is a credible, well-anchored methodology and materially better than most AI audit approaches I have seen, principally because it refuses to confuse governance assurance with model validation and because it anchors on criteria that are actually enforceable.

Its two real weaknesses are that it could deliver an inventory instead of assurance, and that a governance-only approach can pass a model that is causing harm. Both are addressable, and the changes needed are in §10 items 1 and 5.

**Conditions for approval:**
- Eight domains for the first engagement, not eleven
- The three outcome-facing tests are mandatory, not optional
- Legal sign-off on criteria tiering before fieldwork
- Data access commitments in the terms of reference, signed by the CAE
- Sixteen weeks, not twelve
- Minimum three classical ML use cases in the sample
- Scope limitation paragraph agreed with the CAE before the draft report
- A funding proposal for quarterly continuous monitoring submitted with the report

**And the instruction I would give the engagement lead:** do the inventory, do the five core tests, write eight good findings instead of twenty weak ones, and be explicit about what we did not look at. In a new discipline, a narrower report that holds up under challenge builds far more credibility than a broad one that does not.

---

*Back to [README](README.md)*
