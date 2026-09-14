# 08 — Presentation: Risk-Based Approach to AI Governance Audit

**Audience:** Chief Internal Auditor · Head of IT Audit · Technology Risk leadership · Senior management
**Duration:** 25 minutes presentation + 15 minutes discussion
**Tone:** Executive. Decision-oriented. Not academic.

> **Three design rules applied throughout:** (1) one message per slide, stated as a sentence, not a topic; (2) no slide has more than six lines of body text; (3) every slide answers "so what should we do?" — a deck to a CIA is a request for a decision, not a lecture.

> 📊 **Rendered version:** https://claude.ai/code/artifact/a4d3f107-34f2-49cf-9552-ec999d2c0714 — the same deck laid out as a web page, with a Presenter view / Slides-only toggle. Private until you share it.

---

## SLIDE 1 — Title

**Key Message**
Internal Audit has a defined, credible method for providing assurance over AI.

**Ready-to-copy Slide Content**
> # Risk-Based Approach to AI Governance Audit
> ### Providing assurance over artificial intelligence using the discipline we already have
>
> Internal Audit — Technology & Cybersecurity
> [Month Year]

**Recommended Visual Layout**
Full-bleed dark or brand-colour background. Title left-aligned at the optical centre, subtitle in lighter weight beneath. No stock imagery of robots or glowing brains — it undermines credibility with this audience instantly. If a visual is needed, use a simple abstract line motif or the institution's own brand graphic.

**Speaker Notes**
> "AI has moved into our core processes faster than any technology I've seen — credit, fraud, AML, onboarding, and now every desktop through copilots. The question I've been asked, and the question this deck answers, is whether Internal Audit can give the Board assurance over it.
>
> My answer is yes — and sooner than you might expect. Not because we've become data scientists, but because roughly eighty-five per cent of what AI assurance requires is work this function already does to a high standard. What I want to walk you through is the method, what we'd cover, what we would deliberately not opine on, and what I need from you."

---

## SLIDE 2 — Why AI Governance Matters Now

**Key Message**
AI is already embedded in our regulated processes, the regulator is actively shaping expectations, and governance has not kept pace with adoption.

**Ready-to-copy Slide Content**
> ## Why now
>
> **Adoption has outpaced governance**
> Over 70% of Malaysian financial service providers have deployed at least one AI application — up sharply year on year *(BNM, 2025)*
>
> **The regulator is moving**
> - BNM Discussion Paper on AI in the Financial Sector — Aug 2025
> - Industry AI Governance Framework — endorsed by ABM, supported by BNM
> - New JPDP guidelines on automated decision-making — 2026
>
> **The Governor has been explicit**
> > *"Responsibility cannot be delegated to an algorithm."*
> > — BNM Governor, July 2026
>
> **The gap:** AI is making regulated decisions today under governance designed for deterministic systems.

**Recommended Visual Layout**
Three stacked bands, each with a bold header and two supporting lines. The Governor's quote in a pull-quote treatment at the lower third — it does more persuasive work than any statistic. Optional: a simple two-line chart showing adoption rising against governance maturity flat.

**Speaker Notes**
> "Three things have changed in the last eighteen months.
>
> First, scale. BNM's own survey puts adoption above seventy per cent of financial service providers. This is no longer pilots.
>
> Second, regulatory direction. BNM issued a discussion paper in August 2025 and has said a feedback statement is coming. The industry, through the AICB Chief Risk Officers' Forum and with BNM's support, has published an AI Governance Framework. And in May this year the Data Protection Commissioner issued guidelines on automated decision-making that speak directly to what our models do.
>
> Third — and this is the one that matters for us — the Governor put accountability on the record in July. If the regulator is saying responsibility cannot be delegated to an algorithm, the obvious next question to this institution is: who *is* responsible, and how do you know it's working? That question lands on Internal Audit.
>
> I'd flag one thing deliberately: none of this is yet mandatory AI regulation. I'll come back to why that actually strengthens rather than weakens our position."

---

## SLIDE 3 — What Makes AI Different

**Key Message**
AI adds five genuinely new control objectives to our existing technology risk framework — everything else is IT audit we already do.

**Ready-to-copy Slide Content**
> ## What actually changes
>
> | Traditional IT risk | AI adds |
> |---|---|
> | Behaviour is written in code | Behaviour is learned from data |
> | Fails visibly | **Degrades silently** |
> | Explainable by reading the logic | **May not be explainable at all** |
> | Applies rules uniformly | **Can discriminate without anyone intending it** |
> | Changes only when we change it | **A vendor can change it without telling us** |
> | Testable against expected results | Assessed statistically, across a population |
>
> **Five new control objectives:** fairness · explainability · drift detection · training-data provenance · human oversight effectiveness
>
> Everything else — access, change, SDLC, logging, cloud, third party, resilience — is our existing programme, extended in scope.

**Recommended Visual Layout**
Two-column comparison table, the right column visually emphasised (bold, accent colour). Below it, a single horizontal strip containing the five new control objectives as equal-weight chips. Keep the closing sentence on its own line — it is the reassurance the room needs.

**Speaker Notes**
> "I want to be precise about what's new, because if we overstate it we'll be told we're not equipped, and if we understate it we'll miss the risks that matter.
>
> The row I'd draw your attention to is the second one: traditional systems fail visibly. AI degrades silently. A model that has stopped working looks perfectly healthy on every dashboard we currently monitor — it's up, it's responding, it's fast. It's just wrong. That inverts an assumption baked into our change management thinking: that if nothing changed, nothing needs re-checking.
>
> And the fifth row is new in a way that should concern us: with third-party AI, the vendor can change the model underneath us. We have no equivalent of that anywhere else in our technology estate.
>
> But look at the bottom line. Five new control objectives. Everything else on the AI audit programme is access management, change management, SDLC, logging, cloud security, third-party risk and resilience — applied to a new asset. That's us."

---

## SLIDE 4 — The Malaysian Governance Landscape

**Key Message**
There is no mandatory AI regulation yet — but existing mandatory requirements already apply to AI in full, and that is what we will audit against.

**Ready-to-copy Slide Content**
> ## What we audit against
>
> **⚖️ Mandatory — enforceable findings today**
> - **RMiT** (revised Nov 2025) — access, change, cloud, third party, resilience, incident management. *An AI system is a technology system.*
> - **PDPA 2010** (as amended 2024) + **JPDP guidelines on DPIA, Automated Decision-Making & Profiling, Data Protection by Design** (2026)
> - **FSA s.134** customer information secrecy · **Outsourcing** · **e-KYC** · **Fair treatment of financial consumers**
>
> **🏛️ Expected industry practice**
> - **AI Governance Framework** — AICB CRO Forum, BNM-supported, ABM-endorsed. Principles: transparency, accountability, fairness, privacy, robustness
>
> **📘 Direction of travel — not yet a requirement**
> - **BNM Discussion Paper on AI** (Aug 2025); feedback statement indicated for 2026
>
> **We will label every finding by tier. No advisory point will be presented as non-compliance.**

**Recommended Visual Layout**
Three horizontal tiers stacked vertically, colour-coded by weight: solid/dark for mandatory, mid-tone for industry practice, light/outlined for direction of travel. The visual gradient itself carries the message. Bottom line in bold on its own.

**Speaker Notes**
> "This is the slide I'd ask you to hold on to, because it's where AI audits usually go wrong in the closing meeting.
>
> As of today there is no BNM policy document on AI. Management will say that — and they'll be right. But it doesn't get anyone off the hook, because AI systems are already covered by the requirements in the middle of that top tier. RMiT doesn't need an AI chapter to apply to AI. An AI platform has users, changes, endpoints, and a cloud dependency. If it isn't in our user access review population, that's an RMiT gap, and we can name the clause.
>
> Same with the PDPA. The Commissioner's automated decision-making guideline, issued in May, is the closest thing Malaysia has to direct regulation of algorithmic decisions — and it's cross-sector, so it applies to us now.
>
> The middle tier is the sector's own framework. That's our benchmark for 'expected practice' — developed with BNM's support and endorsed by ABM. A gap against it isn't non-compliance, but it is a variance from what our peers are doing, and that's a legitimate thing to report to this Committee.
>
> The bottom tier shapes recommendations only. My commitment to you is that we will label every finding by tier in the report. That's how we keep credibility in the room when management pushes back."

---

## SLIDE 5 — Our Audit Philosophy

**Key Message**
Risk-based, lifecycle-based and governance-focused — and explicit about what we will not opine on.

**Ready-to-copy Slide Content**
> ## Three principles, one boundary
>
> **Risk-based**
> We will not audit 47 use cases equally. We rate them, and we go deep where customer, regulatory and financial impact is highest.
>
> **Lifecycle-based**
> A model can pass every control at launch and be unfit eleven months later without anything changing. We audit the whole life, not the go-live.
>
> **Governance-focused**
> We audit whether the system works — the policy, the gates, the ownership — using individual models as evidence.
>
> ---
> **The boundary**
> We audit **whether appropriate validation happened**.
> We do **not** perform statistical model validation.
> That distinction will be stated explicitly in the report.

**Recommended Visual Layout**
Three principles as equal columns or cards across the upper two-thirds. A clear horizontal rule. The boundary statement below in a contrasting block — visually set apart, because it is the thing the CIA most needs to hear and approve.

**Speaker Notes**
> "Three principles, and one boundary I want you to sign off explicitly.
>
> Risk-based: with forty-plus use cases and the resource we have, equal coverage means thin coverage everywhere. We'll rate the population and go deep on eight to ten.
>
> Lifecycle-based: this is the one that differs most from a standard application audit. A traditional system that passed its controls at go-live is broadly still fine a year later. A model isn't — the world moves and the model doesn't. So a point-in-time review at deployment gives false comfort.
>
> Governance-focused: if I deep-dive three models and say nothing about the other forty-four, I've given the Board almost nothing. So we audit the process, and use models as evidence of whether the process works.
>
> Now the boundary. We will test whether validation was done — by someone independent, before approval, to the scope our own standard requires, with limitations documented and findings closed. We will not re-perform the statistics and we will not opine on whether a model is mathematically sound. That's second line's job, and if you want us to assure the *quality* of their validation, I'll need a specialist for a few days and I'll come back to you on that. What I won't do is let this report imply we've checked something we haven't."

---

## SLIDE 6 — End-to-End Audit Approach

**Key Message**
Six phases, roughly twelve weeks, with a continuous element that keeps assurance current between audits.

**Ready-to-copy Slide Content**
> ## How we will run it
>
> **0 · Position** — set criteria, define scope boundary, book specialists · *1–2 wks*
> **1 · Understand** — map the AI landscape and build an independent inventory · *2–3 wks*
> **2 · Scope & Risk Assess** — rate the population, select 8–10 for depth · *1–2 wks*
> **3 · Assess Design** — test whether controls would work if they operated · *2–3 wks*
> **4 · Test Operation** — sample, observe, reperform · *3–4 wks*
> **5 · Report & Follow Up** — root cause, agreed actions, Audit Committee · *2 wks*
>
> **6 · Continuous Monitoring** — quarterly inventory reconciliation and forum observation · *ongoing*
>
> *Roughly 12 weeks. Phase 1 is the heavy lift — expect a third of the effort establishing what AI we actually have.*

**Recommended Visual Layout**
Horizontal flow of six numbered steps with arrows, durations beneath each. Phase 6 shown as a return arc looping back beneath the chain to Phase 1 — it visually communicates that this is a cycle, not a one-off. Phase 1 given slightly greater visual weight.

**Speaker Notes**
> "Standard audit phases, with two things I'd highlight.
>
> First, Phase 0. Before fieldwork, we settle the criteria — what's mandatory, what's expected practice, what's advisory — and we write down what counts as 'AI' for scoping. That definition sounds academic until you try to decide whether the lead-scoring feature inside the CRM is in scope. It is, and a loose definition is how institutions end up with an inventory that's half complete.
>
> Second, Phase 6. An estate that grew from eighteen systems to forty-one in a year cannot be assured by an audit we run every two years. So I'm proposing a light quarterly reconciliation — inventory against procurement and cloud billing data, which is largely automatable — plus attending the AI governance forum as an observer. Low cost, and it keeps the audit universe current.
>
> On timing: about twelve weeks. I'd flag that Phase 1 is heavier than it looks. In a first-year AI audit, roughly a third of the effort goes into establishing what AI actually exists — and in my experience that turns out to be the most valuable single output of the engagement."

---

## SLIDE 7 — Risk-Based Scoping

**Key Message**
We narrow from the full population to eight to ten use cases through a transparent, defensible rating — and we test the cheap controls across all of them.

**Ready-to-copy Slide Content**
> ## From 47 systems to 10 deep dives
>
> **AI Inventory** — all systems, including embedded and third-party AI
> ↓
> **Risk Classification** — customer impact · automation · regulatory exposure · financial impact · data sensitivity · explainability · criticality · third-party dependency
> ↓
> **Mandatory High-risk escalation** — automated customer decisions · biometric data · capital / AML / ECL · critical business services
> ↓
> **8–10 use cases selected for detailed testing**
>
> ---
> **In parallel: population-level testing of every system** — does it have an owner, a risk rating, a validation date, an approval?
> *"47 of 47 tested" is a far stronger statement to the Board than "10 sampled."*

**Recommended Visual Layout**
A funnel narrowing top to bottom, four stages, with the count shrinking visibly (47 → rated → High-risk → 10). To the right, a separate side-channel box showing population-level testing running alongside — the visual point being that we are not abandoning the other 37.

**Speaker Notes**
> "The obvious challenge to a sample of ten out of forty-seven is: what about the other thirty-seven?
>
> Two answers. First, the selection isn't arbitrary — it's a weighted rating across eight dimensions, with mandatory escalation for anything making an automated customer decision, using biometric data, or feeding capital, ECL or AML. We document why each system was selected *and why each was excluded*. That matters: if something goes wrong next year in an area we didn't cover, a documented risk-based rationale is the difference between a scoping decision and an audit failure.
>
> Second — and this is the part I'd emphasise to the Board — we test the cheap controls across the entire population. Does every system have a named owner? A risk rating? A completed validation? An approval? That data is easy to obtain and covers all forty-seven. Combining full-population testing of cheap attributes with deep sampling of expensive ones gives far better coverage than either alone.
>
> One more thing worth flagging: we'll re-rate a handful of systems ourselves using management's own criteria. Where our rating comes out higher than theirs, that's a finding about the risk assessment process — and it affects all forty-seven systems, not just the ten we tested."

---

## SLIDE 8 — AI Governance Audit Domains

**Key Message**
Every domain in scope traces back to a specific mandatory instrument or industry-endorsed principle from Slide 4 — nothing on this list was picked freehand.

**Ready-to-copy Slide Content**
> ## Why these domains
>
> | Domain | Mandatory anchor (⚖️) | Expected practice anchor (🏛️) |
> |---|---|---|
> | 1 · Governance, Policy & Risk Appetite | RMiT — technology risk governance, board & senior management oversight | Accountability |
> | 2 · AI Inventory & Classification | RMiT — technology asset & risk register | Accountability · Robustness |
> | 3 · Risk Assessment & Approval | RMiT — risk assessment before deployment / change | Robustness |
> | 4 · Data Governance & Privacy | PDPA + JPDP (DPIA / ADMP / DPbD) · FSA s.134 | Privacy |
> | 5 · Development, Acquisition & Validation | RMiT — SDLC & change management | Robustness |
> | 6 · Fairness, Explainability & Human Oversight | JPDP ADMP Guideline · Fair Treatment of Financial Consumers | Fairness · Transparency |
> | 7 · AI Security | RMiT — cybersecurity & cyber resilience | Robustness |
> | 8 · Third-Party & Cloud AI | RMiT — third party / cloud · BNM Outsourcing PD | Robustness · Accountability |
> | 9 · Change, Monitoring & Incident Management | RMiT — change management & incident reporting | Robustness |
> | 10 · Generative AI *(overlay)* | Inherits 1–9, plus PDPA/JPDP ADMP where output feeds a decision | All five principles |
> | 11 · Resilience & Record Keeping | RMiT — operational/cyber resilience · retention obligations | Robustness |
>
> **Every domain carries at least one mandatory anchor. Nothing on this scope rests on the BNM Discussion Paper alone.**
>
> *The Discussion Paper's "risks in AI adoption" section is the broad rationale for treating AI as elevated risk across the estate — it shapes prioritisation, not the criteria themselves.*

**Recommended Visual Layout**
A single traceability table, one row per domain, reusing the tier colours from Slide 4 — a solid mandatory-anchor cell in every row is the visual proof this scope isn't built on guidance alone. Keep the domain column narrow and fixed; let the two anchor columns wrap on mobile. The bottom line and the Discussion Paper footnote each sit on their own line, visually set apart from the table.

**Speaker Notes**
> "I had a version of this slide that just grouped the eleven domains into four bands — governance, AI-specific, extended IT, and the GenAI overlay. It looked tidy, but it invited an obvious question I'd rather answer here than in the room: why these eleven, and why not more or fewer?
>
> This version answers it directly. Every domain in our programme has at least one mandatory anchor — a specific RMiT provision, the PDPA and the JPDP guidelines, the outsourcing policy, or the fair treatment of financial consumers requirements. I did that deliberately. Nothing on this scope rests only on the AI Governance Framework or the BNM discussion paper, because those are Tier 2 and Tier 3, and I don't want to build a mandatory-sounding audit programme on voluntary ground.
>
> Where the discussion paper does useful work is prioritisation, not justification. Its 'risks in AI adoption' section is the reason we're treating AI as elevated risk across the whole estate — but notice every domain already stands on its own mandatory or industry-endorsed anchor without it.
>
> One flag for the room: these are indicative mappings to the current instruments. Before we issue anything against them, we'll cite the exact clause in the current RMiT Policy Document and the relevant JPDP guideline — that's a Phase Zero task, not something I'm asking you to take on faith today."

---

## SLIDE 9 — Walkthrough: AI-Enabled Credit Scoring

**Key Message**
Here is exactly what the work looks like on a real use case — and none of these tests requires a data scientist.

**Ready-to-copy Slide Content**
> ## Worked example — retail credit scoring model
>
> | | |
> |---|---|
> | **Risk** | The model declines applicants on grounds we cannot explain or justify, with degraded performance we would not detect |
> | **Control** | Independent validation before approval · disparate-impact testing against a pre-agreed threshold · reason codes stored with each decision · credit officer review with override authority · monthly performance and fairness monitoring |
> | **Evidence** | Validation report (author + reporting line) · approval paper and dates · fairness threshold documentation · stored decision records · override statistics · 12 months of monitoring output · a real adverse-action letter |
> | **Test** | Compare validation date to go-live date · trace validator's reporting line on the org chart · trend the override rate and check decision timestamps · trace every monitoring threshold breach to a response · **ask a branch officer to explain a specific decline** |
> | **Potential finding** | Validation completed 12 days after the model began making customer decisions; no fairness threshold set in advance; override rate 0.3% with median 4-second review; a threshold breach in month 7 with no recorded response; front-line staff unable to explain declines |
>
> **Every test above is documentary, observational or timestamp-based.**

**Recommended Visual Layout**
Five-row table with the row labels as a bold left column in accent colour. The final line beneath the table, emphasised. If space is tight, split across two slides rather than shrinking the type — this slide does the heaviest persuasive work in the deck and must be readable.

**Speaker Notes**
> "I want to make this concrete, because 'AI audit' can sound abstract until you see the actual tests.
>
> Take our retail credit scoring model. Five tests.
>
> One: compare the date on the validation report to the go-live date. If validation finished after the model started declining customers, that's a finding, and the evidence is two dates.
>
> Two: find the validator's name and trace their reporting line. If they report to the person who built the model, the validation wasn't independent. That's an org chart.
>
> Three: pull the override rate. If credit officers override the model 0.3% of the time, and the timestamps show four seconds between the recommendation appearing and the decision being recorded, then the human-in-the-loop control we've told ourselves exists is a click. That's a spreadsheet and some timestamps.
>
> Four: take every monitoring threshold breach and trace it to a response. Breaches with no recorded response is the single most common finding in this space.
>
> Five — and this is my favourite because it costs nothing — go to a branch and ask an officer to explain a specific decline. If they can't, then we cannot explain our credit decisions to a customer, to the Ombudsman, or to BNM. No amount of technical documentation changes that.
>
> Not one of those five requires a data scientist."

---

## SLIDE 10 — Integration with IT Audit

**Key Message**
AI assurance is our existing technology controls extended in scope, plus five new control objectives — not a separate function.

**Ready-to-copy Slide Content**
> ## This is not a new audit function
>
> ### Existing IT controls — extended in scope
> Access management → *now covers model registries, training data, prompts, AI agent identities*
> Change management → *now covers models, training data, prompts, thresholds, vendor model updates*
> SDLC → *adds independent validation, fairness testing, adversarial testing as gates*
> Logging & monitoring → *adds model performance and drift as monitored signals*
> Cloud & infrastructure → *adds AI data residency, inference endpoints, prompt log stores*
> Third-party risk → *adds no-training clauses, model change notification, ISO 42001*
> Resilience → *adds fallback to non-AI process, kill switch, decision reconstruction*
>
> ### Plus five new control objectives
> Fairness · Explainability · Drift detection · Training-data provenance · Human oversight effectiveness
>
> ### = AI Governance Assurance
>
> **Existing IT controls remain necessary — but are no longer sufficient.**

**Recommended Visual Layout**
Two stacked blocks joined by a large "+", resolving into a single result bar at the bottom. The top block uses the institution's established audit colour; the second block an accent colour; the result bar combines both. Closing line in bold beneath.

**Speaker Notes**
> "This is the slide for anyone who thinks we need to hire a separate AI audit team.
>
> Every line in that top block is something this function already does well. What changes is scope. Our access review population needs to include the model registry and the training data store. Our change management definition needs to include prompts — and I'd note that in most institutions right now, prompts are edited directly in a vendor console with no change record at all. That's an unauthorised change to a production control, and it's a finding we can raise with the change management skills we already have.
>
> The five new objectives underneath are genuinely new. Fairness, explainability, drift, data provenance, and whether human oversight actually works. That's where we'll need to build capability and, in places, buy specialist support.
>
> The sentence at the bottom is the one I'd ask you to take away. Our existing controls remain necessary — nothing is removed. But they're no longer sufficient on their own. An auditor who tests AI change management using an unmodified traditional programme will conclude 'adequate' and be wrong, because the programme won't ask about prompts, retraining, or a vendor changing the model underneath us."

---

## SLIDE 11 — Reporting and Continuous Monitoring

**Key Message**
We report in business consequence, we tier our criteria, and we stay current between audits rather than waiting two years.

**Ready-to-copy Slide Content**
> ## How we will report — and stay current
>
> **Reporting discipline**
> - **Lead with consequence, not mechanism** — not *"the model exhibits distributional drift"* but *"we may be missing fraud we previously caught, and we would not know"*
> - **Group by theme, not by system** — eight instances of missing monitoring is one finding with eight examples
> - **Label every finding by criteria tier** — regulatory requirement / expected practice / good practice
> - **Distinguish "the control failed" from "the control does not exist"** — different severity, different owner
> - **Quantify** — *"14 of 41 systems"*, never *"several systems"*
>
> **Continuous monitoring between audits**
> - Quarterly inventory reconciliation against procurement and cloud billing — largely automatable, high yield for shadow AI
> - Standing observer seat at the AI governance forum
> - AI incidents reviewed as they arise
> - Quarterly one-page assurance update to the Head of IT Audit

**Recommended Visual Layout**
Two panels side by side: "Reporting discipline" left, "Continuous monitoring" right, divided by a vertical rule. Use a small clock or cycle icon on the right panel only. Keep the contrasting quote pair on the first bullet visually distinct — it demonstrates the principle rather than describing it.

**Speaker Notes**
> "Two things here.
>
> On reporting — the failure mode with AI findings is writing them in a language the Audit Committee can't act on. 'Distributional drift in the input feature space' is accurate and useless. 'Our fraud model's performance has degraded over eleven months, we may be missing fraud we previously caught, and nobody would know because no one is monitoring it' — that gets a decision.
>
> The tiering point I made earlier applies here too, and I'd ask you to hold me to it. If we present an advisory point as regulatory non-compliance, we lose the argument in the closing meeting and it damages the credibility of everything else in the report.
>
> On continuous monitoring — I'm proposing something modest. A quarterly reconciliation of the inventory against procurement and cloud billing data. It's largely automatable and it's the single most reliable way to detect AI appearing outside governance. Plus an observer seat at the AI governance forum, which costs us an hour a month and tells us more about the control environment than a week of document review.
>
> That gives you a quarterly one-pager, and it keeps the audit universe current in an estate that's changing faster than our audit cycle."

---

## SLIDE 12 — Key Takeaway and Ask

**Key Message**
We can deliver credible AI assurance this cycle with the team we have — here is what I need.

**Ready-to-copy Slide Content**
> ## Where this lands
>
> ### Effective AI governance should enable responsible AI adoption while keeping AI risk within the institution's risk appetite.
>
> **Internal Audit's role:** to give the Board confidence that this is actually happening — not to slow adoption down.
>
> ---
> **What I need from you**
>
> 1. **Endorsement of the scope boundary** — we audit whether validation happened; we do not perform model validation
> 2. **Specialist budget** — approximately 5 days of data science input to review validation quality on high-risk models
> 3. **Access** — observer status at the AI Governance Forum, and access to procurement, cloud billing and proxy data for inventory reconciliation
> 4. **Agreement on timing** — approximately 12 weeks, commencing [date]
>
> **First deliverable, within 4 weeks: an independently verified AI inventory. In most institutions, that alone changes the conversation.**

**Recommended Visual Layout**
Key message as a large centred statement in the upper third, visually distinct — it should read as a principle, not a bullet. Horizontal rule. The four asks as a clean numbered list. Final line in a highlighted band at the base of the slide.

**Speaker Notes**
> "Let me close on the framing and then the ask.
>
> The purpose of AI governance is not to stop the bank using AI. It's to let the bank use AI confidently — to adopt it at pace while keeping the risk inside the appetite this Board has set. Our role is to give the Board evidence that this is genuinely happening, not to be the function that slows it down. I'd want that understood by the business before we start, because the reception we get shapes what we're shown.
>
> Four asks.
>
> One — endorse the boundary. We audit whether validation happened, not whether the maths is right. If you want us to go further, that's a different engagement and a different budget.
>
> Two — about five days of data science input, so a specialist can tell me whether the validation work on our highest-risk models was methodologically sound. Without it I can tell you validation occurred; I can't tell you it was any good.
>
> Three — access. Observer status at the AI Governance Forum, and data from procurement, cloud billing and the proxy. That last one is how we find AI nobody registered.
>
> Four — about twelve weeks.
>
> And the line I'd leave you with: within four weeks I can give you an independently verified inventory of what AI this institution actually runs. In most institutions the verified number is roughly double what management believes. If that's true here, that finding alone will reshape how the Board thinks about this — and it's the foundation for everything else we do."

---

## Facilitator's note — likely challenges from this audience

| Challenge | Response |
|---|---|
| *"There's no BNM AI regulation — what are you auditing against?"* | RMiT, PDPA and the JPDP guidelines are mandatory and already apply. We label every finding by tier so advisory points are never presented as non-compliance. (Slide 4) |
| *"We don't have data scientists in Internal Audit."* | Eighty-five per cent of the programme is access, change, third-party and governance testing. For the remainder, five days of specialist input. (Slides 3, 5, 9) |
| *"The business will say we're slowing down innovation."* | The framing is enablement — a clear governance path is what stops teams building in the shadows. Our first deliverable is an inventory, which helps them as much as us. (Slide 12) |
| *"Isn't this Model Risk Management's job?"* | MRM covers models in its framework. Our first test is whether the boundary is defined — and in most institutions GenAI and embedded AI fall outside MRM with nothing else picking them up. (Slides 5, 8) |
| *"Can't we wait until BNM issues something?"* | The estate is growing faster than the audit cycle, the PDPA guidelines are already in force, and building the inventory now is the prerequisite for responding to whatever BNM issues. (Slides 2, 6) |

---

*Next: [09 — Knowledge Review](09-Knowledge-Review.md)*
