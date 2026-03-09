# RISK_REGISTER.md — Trialsplained
## Product & Ethical Risk Register
*Last updated: 8 March 2026 | Owner: Nina Arden*

---

## Purpose

This document identifies every significant risk associated with Trialsplained — across product quality, user safety, legal/regulatory compliance, ethical obligations, and commercial viability. For each risk it records: likelihood, impact, current mitigation, and residual risk.

It exists to demonstrate that risks have been identified and considered — not just the ones that are easy to solve.

**Risk ratings:**
- Likelihood: High / Medium / Low
- Impact: High / Medium / Low
- Residual risk: the risk remaining after mitigations are applied

---

## Category 1 — User Safety Risks

---

### R01 — AI summary contains a factual error that influences a user's decision to join a trial

**Likelihood:** Medium — AI hallucination is a known limitation of LLMs; clinical terminology increases the risk of plausible-sounding errors

**Impact:** High — a user who joins a trial based on materially incorrect information about risks, eligibility, or commitment could suffer harm

**Current mitigations:**
- Every summary includes a prominent link to the official registry listing
- Every summary includes a last-verified date
- AI labelling is visible on every card — users are told summaries may contain errors
- Feedback button on every card with 48-hour response commitment
- Disclaimer on every page: "always verify with the official listing"
- GP consultation prompt on every trial card

**Residual risk:** Medium — mitigations reduce but do not eliminate the risk that a user reads only the Trialsplained summary without checking the official listing

**Mitigation roadmap:** Human review of summaries at v1.0; structured accuracy audit process at >1,000 MAU

---

### R02 — Phase I trial risk understated by plain-language simplification

**Likelihood:** High — simplification inherently reduces nuance; Phase I first-in-human risk is particularly susceptible to this

**Impact:** High — a user who joins a Phase I trial without understanding it is primarily a safety study, not a treatment, could have materially wrong expectations

**Current mitigations:**
- Amber-bordered Phase I callout on every Phase I trial card: explicit plain-English explanation that this is a safety trial with higher uncertainty
- Official listing link
- GP consultation prompt

**Residual risk:** Low-Medium — the callout is prominent and cannot be missed; however it cannot force the user to read it

---

### R03 — "Not yet recruiting" trial creates false hope for a vulnerable user

**Likelihood:** Medium — dementia, rare disease, and terminal condition users are likely to be emotionally invested in results

**Impact:** Medium — disappointment and distress if a user pursues a trial that isn't open; lower than R01/R02 as no physical harm pathway

**Current mitigations:**
- Plain-English tooltip on "Not yet recruiting" badge: explains the trial is not open and directs user to official listing for expected start date
- No "notify me" feature (which would require email collection and could amplify attachment to a specific trial)

**Residual risk:** Low — tooltip is always present; user is directed to official source for current status

---

### R04 — User in crisis uses the app in place of clinical support

**Likelihood:** Low-Medium — users searching for dementia, mental health, or terminal condition trials may be in acute distress

**Impact:** High — if the app becomes a substitute for clinical contact, outcomes could be seriously negative

**Current mitigations:**
- Every trial card includes "Talk to your GP about this trial" prompt
- "What do I do next?" journey explicitly positions GP as first contact, not the trial team
- No messaging or chat feature that could simulate clinical support
- No claims that Trialsplained can assess suitability

**Residual risk:** Low — product is clearly an information tool; no features that could plausibly substitute for clinical care

---

## Category 2 — Legal and Regulatory Risks

---

### R05 — UK GDPR: feedback form creates data controller obligations

**Likelihood:** High — any free-text submission to feedback@trialsplained.com means Nina is processing personal data as a data controller

**Impact:** Medium — no fine risk at prototype scale; reputational risk if a user complains about data handling; interview/due diligence risk if a company reviewer identifies this gap

**Current mitigations:**
- Feedback form includes explicit note: "Do not include personal health information"
- No personal data is requested or stored by the app itself
- Privacy notice identified as v0.2 pre-launch requirement

**Residual risk:** Medium (prototype) / High (if launched without privacy notice) — this is a known gap, documented and deferred

**Open question:** If a user includes personal health information in the feedback form despite the instruction, Trialsplained becomes a processor of Article 9 special category data. A data handling SOP is required before launch.

---

### R06 — EU GDPR applies to EU users who access the app

**Likelihood:** High — ClinicalTrials.gov is a global platform; the app will be accessible globally; EU users will find it

**Impact:** Medium — the app collects no data, which limits exposure; however, the absence of a privacy notice and cookie disclosure creates non-compliance

**Current mitigations:**
- Data minimisation by design: no personal data collected
- localStorage use (accessibility preferences, session saves) may require PECR disclosure

**Residual risk:** Medium — acknowledged, not resolved; documented for transparency

**Mitigation roadmap:** UK/EU privacy notice at v0.2; legal review of PECR/localStorage position before launch

---

### R07 — Product misclassified as SaMD by a regulatory body

**Likelihood:** Low — current feature set is clearly information provision, not clinical decision support

**Impact:** High — SaMD classification would require full MHRA/MDR conformity assessment; effectively halting the product

**Current mitigations:**
- No eligibility screening feature
- No health record integration
- No personalised recommendations
- No clinical decision support functionality
- SaMD trigger points documented in DECISION_LOG.md D10 and REGULATORY_FRAMEWORK.md
- Any new feature assessed against trigger points before build

**Residual risk:** Low — current product is clearly outside SaMD scope; risk is in future feature decisions

---

### R08 — Liability for harm caused by acting on Trialsplained information

**Likelihood:** Low — user is clearly directed to official listing and GP; no clinical recommendations are made

**Impact:** High — if a user suffered harm and claimed Trialsplained's summary contributed, reputational and legal exposure would be significant

**Current mitigations:**
- Disclaimer on every page
- AI labelling with explicit "may contain errors" statement
- Mandatory official listing link on every card
- GP consultation prompt on every card
- "Not medical advice" statement throughout

**Residual risk:** Low-Medium — disclaimer is not a complete legal shield; terms of service and legal review required before real-world launch

**Mitigation roadmap:** Terms of service, professional legal review, and assessment of professional indemnity insurance requirements before any promotion beyond builder's direct network

---

## Category 3 — Ethical Risks

---

### R09 — Plain-language simplification creates health equity risk by oversimplifying consent-relevant information

**Likelihood:** Medium — simplification is the product's core function; the risk of losing material information is inherent

**Impact:** High — informed consent is a fundamental right; a product that makes trials seem simpler than they are undermines the consent process it aims to support

**Current mitigations:**
- Phase I callout is non-negotiable and cannot be simplified away
- Placebo arm disclosure is mandatory on every applicable trial card
- Withdrawal rights stated on every expanded card
- Side effects included in expanded content
- Official listing link — always present

**Residual risk:** Medium — cannot be fully mitigated by design; requires ongoing accuracy monitoring

**Open question:** Should Trialsplained work with clinical researchers to establish a plain-language review standard for trial summaries? This would improve quality significantly but requires resource. Deferred to v1.0.

---

### R10 — App is not accessible to the populations most underrepresented in trials

**Likelihood:** High — the app is English-only; communities most underrepresented in UK trials often include speakers of Polish, Bengali, Urdu, Somali, and other languages

**Impact:** High — an app intended to improve trial access that cannot be used by underrepresented communities partially defeats its own purpose

**Current mitigations:**
- Accessibility controls (text size, high contrast) address one dimension of access
- Year 9 reading level target addresses literacy within English
- Issue documented publicly in ETHICS.md

**Residual risk:** High — no mitigation for non-English speakers at current version

**Mitigation roadmap:** Language translation (priority: Polish, Bengali, Urdu) at v0.3; community co-design required for meaningful implementation

---

### R11 — B2B commercial model creates incentive misalignment with patient interests

**Likelihood:** Low-Medium — a B2B model where sponsors pay for listing or prominence would create direct conflict of interest with the no-ranking principle

**Impact:** High — if Trialsplained accepts payment from trial sponsors for any form of preferential treatment, the product's core trust proposition is destroyed

**Current mitigations:**
- Decision D03 explicitly forecloses ranking and recommendations
- Decision D11 commits to honest capability statements only
- For Organisations page is framed around plain-language services (patient documents, materials) — not trial promotion
- No advertising model considered or planned

**Residual risk:** Low — foreclosed by design at this stage; requires governance policy before any commercial engagement

---

### R12 — AI model used may have biases that affect which trials are better summarised

**Likelihood:** Medium — LLM training data may underrepresent certain conditions, populations, or geographies

**Impact:** Medium — biased summarisation could result in some trials being described more clearly or favourably than others without any intentional ranking

**Current mitigations:**
- All summaries link to official listing — users are not dependent on the summary alone
- Accuracy feedback mechanism catches systematic errors
- Issue documented in RESPONSIBLE_AI.md

**Residual risk:** Medium — not measurable without structured bias testing; deferred to v1.0

---

## Category 4 — Product & Commercial Risks

---

### R13 — Demo data is mistaken for live search by users or reviewers

**Likelihood:** Medium — the app is designed to look fully functional; hardcoded demo data is not visibly distinguished from live data

**Impact:** Medium — a user who searches for a real condition and trusts the results as live data could be misled; a company reviewer who understands it's a demo will not be misled

**Current mitigations:**
- All demo trials are real trial types (not invented conditions or treatments)
- Official listing links present — a user who clicks through will see real data
- "Last verified [date]" label present

**Residual risk:** Medium (real users) / Low (company reviewers) — acceptable for a portfolio prototype; must be resolved before any public promotion

---

### R14 — For Organisations page creates expectations that cannot be met

**Likelihood:** Low — page is framed as "early stage, looking for pilot partners"; services described are things Nina can actually deliver

**Impact:** Medium — if an organisation responds expecting enterprise software, the gap between expectation and reality could damage credibility

**Current mitigations:**
- Page explicitly states this is early stage
- GDPR prototype note is honest about current limitations
- Services described are deliverable by one person with clinical research experience
- Contact is email only — no form or CRM that implies infrastructure

**Residual risk:** Low — honest framing reduces expectation gap

---

### R15 — App becomes a recruitment funnel without the regulatory framework for it

**Likelihood:** Low — no "apply" button, no direct trial contact facilitation, no pre-screening

**Impact:** High — if Trialsplained were perceived or used as a patient recruitment tool, it would face regulatory scrutiny and could conflict with trial sponsor protocols

**Current mitigations:**
- No "Apply now" button anywhere
- "What do I do next?" journey explicitly routes through GP, not direct trial contact
- For Organisations page positions as plain-language support, not recruitment
- Product does not receive referral fees or any value from trial participation

**Residual risk:** Low — product architecture forecloses the recruitment pathway

---

## Risk Summary Table

| ID | Risk | Likelihood | Impact | Residual Risk | Status |
|----|------|-----------|--------|--------------|--------|
| R01 | AI summary factual error | Medium | High | Medium | Mitigated, monitoring |
| R02 | Phase I risk understated | High | High | Low-Medium | Mitigated (callout) |
| R03 | Not yet recruiting false hope | Medium | Medium | Low | Mitigated (tooltip) |
| R04 | App used instead of clinical support | Low-Medium | High | Low | Mitigated (design) |
| R05 | GDPR: feedback form | High | Medium | Medium | Known gap, deferred |
| R06 | EU GDPR exposure | High | Medium | Medium | Known gap, deferred |
| R07 | SaMD misclassification | Low | High | Low | Monitored (trigger points) |
| R08 | Liability for harm | Low | High | Low-Medium | Deferred to launch |
| R09 | Simplification undermines consent | Medium | High | Medium | Ongoing monitoring |
| R10 | Not accessible to underrepresented groups | High | High | High | Known gap, roadmap |
| R11 | B2B incentive misalignment | Low-Medium | High | Low | Foreclosed by design |
| R12 | AI bias in summaries | Medium | Medium | Medium | Deferred to v1.0 |
| R13 | Demo data mistaken for live | Medium | Medium | Low-Medium | Acceptable for prototype |
| R14 | For Organisations expectation gap | Low | Medium | Low | Mitigated (honest framing) |
| R15 | App becomes recruitment funnel | Low | High | Low | Foreclosed by design |

---

## Open Risks Requiring Action Before Real-World Launch

The following risks must be resolved before Trialsplained is promoted beyond the builder's direct network:

1. **R05 / R06** — Privacy notice published; GDPR legal review completed
2. **R08** — Terms of service published; legal review completed
3. **R13** — Live data integration or clear "demo data" labelling implemented

*These are documented as known gaps, not overlooked ones.*
