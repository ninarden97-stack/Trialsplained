# DECISION_LOG.md — Trialsplained
## Product Decision Log
*Last updated: 8 March 2026 | Owner: Nina Arden*

---

## Purpose

This document records every significant product decision made during the design and build of Trialsplained — what was decided, why, and what alternatives were considered and rejected. It exists so that future collaborators, reviewers, or a future version of the product team can understand not just what was built, but why.

Decisions are categorised as: **DECIDED** (resolved) or **OPEN** (identified, not yet resolved, with rationale for deferral).

---

## Decision Framework

Each decision follows this structure:
- **Decision:** What was decided
- **Rationale:** Why
- **Alternatives considered:** What else was evaluated
- **Why alternatives were rejected:** The reasoning
- **Status:** DECIDED / OPEN
- **Date:** When decided
- **Dependencies:** What this decision affects or is affected by

---

## D01 — Primary audience definition

**Decision:** Trialsplained serves a broad public audience — patients, families, carers, researchers, and curious members of the public — rather than a single defined persona.

**Rationale:** Clinical trial literacy is a population-wide problem. Narrowing to one persona (e.g. "patient recently diagnosed") would reduce the addressable audience and limit the SEO and sharing surface. The plain-language approach works for all segments simultaneously.

**Alternatives considered:**
- Patient-only product
- Researcher-only product
- Separate patient and professional products

**Why alternatives were rejected:** Patient-only misses the family carer dynamic (families research together — WhatsApp sharing data confirms this). Researcher-only already has ClinicalTrials.gov. Separate products require more infrastructure than a one-day build can support.

**Status:** DECIDED
**Date:** 8 March 2026

---

## D02 — No user accounts or data collection

**Decision:** Trialsplained collects no personal data. No account creation. No email capture. Trial saves are session-based only (browser localStorage, cleared on tab close).

**Rationale:** The user base includes vulnerable people (recent diagnosis, terminal condition, elderly). Requiring data to access health information creates a barrier that disproportionately affects the most vulnerable users and is not justified by any product need at this stage.

**Alternatives considered:**
- Optional accounts for persistent trial saves
- Email-yourself saved trials link
- Anonymous analytics (Plausible / Fathom)

**Why alternatives were rejected:** Optional accounts create an account infrastructure requirement and GDPR obligations before we have evidence of user need. Email-yourself requires email collection — a data controller obligation. Anonymous analytics deferred to v0.3 when usage justifies it; privacy notice must be published first.

**Open question:** Session-based saves are lost when the tab is closed. User testing may reveal this is a significant friction point — particularly for older users or those using shared devices. This will be evaluated in v0.2.

**Status:** DECIDED (accounts and email capture); OPEN (whether session-only saves are sufficient)
**Date:** 8 March 2026
**Dependencies:** D08 (GDPR), D09 (liability)

---

## D03 — No trial ranking or recommendations

**Decision:** Trialsplained does not rank, score, or recommend trials. Results are displayed without implied quality ordering.

**Rationale:** Ranking implies comparative quality assessment. Trialsplained does not have the clinical expertise, real-time data, or regulatory clearance to assess which trial is "better" for any individual. Ranking would also create an incentive misalignment if commercial relationships with sponsors are ever introduced — a conflict of interest the product is designed to foreclose.

**Alternatives considered:**
- Relevance ranking (by condition match, location proximity)
- User-defined sort (by phase, commitment, location)
- Popularity ranking (by saves or shares)

**Why alternatives were rejected:** Relevance and proximity ranking without user health data is low-value and potentially misleading. User-defined sort may be added in v0.2 as a neutral feature. Popularity ranking would create social proof dynamics inappropriate for a health decision context.

**Status:** DECIDED
**Date:** 8 March 2026

---

## D04 — Phase I trials require explicit risk callout

**Decision:** Every Phase I trial card displays a prominent amber-bordered callout: "This is an early-stage safety trial. The primary purpose is to assess safety, not to test whether the treatment works. Phase I trials carry greater uncertainty than later-phase trials."

**Rationale:** Phase I means first-in-human testing. AI plain-language simplification could inadvertently make Phase I trials sound more benign than they are. A user making a health decision based on an oversimplified Phase I summary could be materially harmed. The ethical obligation to preserve risk information outweighs the aesthetic preference for clean card design.

**Alternatives considered:**
- Phase label only (no callout)
- Remove Phase I trials from consumer results entirely
- Explain phases on the How it works page only

**Why alternatives were rejected:** Phase label alone requires the user to know what Phase I means — this defeats the purpose of a plain-language product. Removing Phase I trials reduces access for patients with conditions where Phase I is the only available option (e.g. rare diseases). Explanation on How it works only doesn't reach users who don't read it.

**Status:** DECIDED
**Date:** 8 March 2026
**Dependencies:** D05 (AI responsibility), D09 (liability)

---

## D05 — User responsibility for verifying AI summaries

**Decision:** The user bears responsibility for verifying AI summary accuracy by checking the official listing. Trialsplained's obligation is to make verification easy (prominent link, last-verified date, feedback mechanism) and to label AI involvement clearly on every card.

**Rationale:** Trialsplained is an information accessibility tool, not a medical tool. The role of the product is to lower the barrier to finding and understanding trials — not to certify the accuracy of clinical information. Certifying accuracy would require human clinical review at scale, which is not feasible at this stage, and would potentially push the product into SaMD regulatory territory.

**Alternatives considered:**
- Human review of all AI summaries before publication
- Human review triggered by any accuracy feedback
- No AI labelling (present summaries as verified)

**Why alternatives were rejected:** Human review at scale requires infrastructure not available at this stage — this is a v1.0 commitment. Human review on feedback is implemented now. No AI labelling is rejected on ethical grounds — users have a right to know AI is involved.

**Open question:** At what volume of usage does the current feedback-only oversight model become inadequate? This needs to be reassessed at 1,000 monthly active users.

**Status:** DECIDED (current model); OPEN (scaling threshold)
**Date:** 8 March 2026
**Dependencies:** D04 (Phase I), D09 (liability)

---

## D06 — "Not yet recruiting" trials included with mandatory explanation

**Decision:** Trials with "Not yet recruiting" status are shown in results, but the status badge includes a mandatory plain-English tooltip: "This trial isn't open yet. It may not begin accepting participants for some time. Check the official listing for the expected start date."

**Rationale:** Excluding not-yet-recruiting trials reduces utility — particularly for users with rare conditions or long planning horizons (e.g. carers researching options for a family member). However, displaying the badge without explanation could cause harm to vulnerable users who don't understand what it means.

**Alternatives considered:**
- Hide not-yet-recruiting trials entirely
- Show status badge only without explanation
- Add "notify me when open" email alert

**Why alternatives were rejected:** Hiding reduces access without user consent. Badge-only fails users unfamiliar with trial terminology. Email notification requires email collection — GDPR obligation, deferred to v0.3.

**Status:** DECIDED
**Date:** 8 March 2026

---

## D07 — Professional / researcher view as opt-in toggle

**Decision:** A "Patient view | Professional view" toggle is available on every trial card and as a page-level switch. Professional view shows technical data (NCT number, eligibility criteria, site contacts). Patient view is the default.

**Rationale:** The audience includes researchers and healthcare professionals who need technical data. Displaying this data to all users by default would undermine the plain-language positioning. The toggle lets the product serve both audiences without compromising either.

**Alternatives considered:**
- Separate professional product / URL
- Professional data hidden behind account creation
- No professional view at all

**Why alternatives were rejected:** Separate product requires more infrastructure. Account-gating creates GDPR obligations and a barrier to access. No professional view limits B2B credibility and portfolio impact.

**Note:** All data in professional view is publicly available on ClinicalTrials.gov. The view is labelled "for researchers and healthcare professionals" to manage expectations.

**Status:** DECIDED
**Date:** 8 March 2026

---

## D08 — GDPR and data protection position

**Decision:** As a prototype, Trialsplained is designed with data minimisation as a core principle. No personal data is collected. The feedback form sends free text to an email address. The For Organisations page shows an email address only (no form). A full privacy notice is required before any real-world launch.

**Rationale:** Any form that collects name, organisation, or free text creates a data controller obligation under UK GDPR. As a prototype built in 24 hours with no legal review, the responsible position is to minimise data collection and explicitly acknowledge that a privacy notice is required before launch.

**Alternatives considered:**
- Full GDPR-compliant privacy notice published at launch
- Contact form with consent checkbox and privacy notice link
- No feedback mechanism at all

**Why alternatives were rejected:** Full privacy notice requires legal review — not feasible in 24 hours. Contact form with consent checkbox is the right v0.2 approach. No feedback mechanism removes a critical product quality signal.

**Open questions (documented for interview and review purposes):**
1. ClinicalTrials.gov is a global platform. EU users may access Trialsplained, triggering EU GDPR obligations in addition to UK GDPR. This is unresolved.
2. The feedback email address (feedback@trialsplained.com) receives free-text submissions. If a user includes personal health information despite the explicit instruction not to, Trialsplained becomes a processor of special category data under Article 9. A data handling procedure is required for v0.2.
3. Browser localStorage is used for accessibility preferences and session saves. This is technically not a cookie but may still require disclosure under PECR (Privacy and Electronic Communications Regulations) depending on interpretation. Legal review required before launch.

**Status:** DECIDED (current data minimisation approach); OPEN (privacy notice, EU GDPR, PECR, health data in feedback)
**Date:** 8 March 2026
**Dependencies:** D02 (no accounts), D05 (feedback form)

---

## D09 — Liability position

**Decision:** Trialsplained is an information tool. The user is responsible for verifying information by checking the official listing. Trialsplained's liability position rests on: (a) clear AI labelling, (b) mandatory links to official listings, (c) prominent disclaimer on every page, (d) explicit "not medical advice" statement, (e) GP consultation prompt on every trial card.

**Rationale:** This is the appropriate liability position for a prototype information tool with no clinical review infrastructure. It is consistent with how similar information services (health websites, NHS patient information) manage liability.

**Alternatives considered:**
- Seek legal review before launch
- Obtain professional indemnity insurance
- Publish a formal terms of service

**Why alternatives were rejected:** Legal review and insurance are requirements for a real-world launch — not a 24-hour prototype. These are v0.2 pre-launch requirements, documented explicitly.

**Open question:** At what point does the product's reach require a formal terms of service and legal review? This is a launch gate, not a feature gate. Terms of service, privacy notice, and legal review are required before Trialsplained is promoted to any population beyond the builder's direct network.

**Status:** DECIDED (current prototype position); OPEN (formal launch requirements)
**Date:** 8 March 2026

---

## D10 — Regulatory classification

**Decision:** Trialsplained is not a medical device under current UK (UKCA/MHRA), EU (MDR 2017/745), or US (FDA SaMD) frameworks. It is an information accessibility tool — the digital equivalent of a plain-language patient information leaflet.

**Rationale:** SaMD classification is triggered when software is intended for a medical purpose — diagnosis, prevention, monitoring, or treatment of disease. Trialsplained does not perform any of these functions. It rewrites publicly available information into accessible language.

**Trigger points for reclassification (documented for review):**
- If the app adds eligibility screening ("Are you eligible?") → potential SaMD trigger
- If the app integrates with NHS health records (FHIR API) → definite SaMD trigger
- If the app provides personalised trial recommendations based on user health data → definite SaMD trigger
- If the app is used by healthcare professionals to support clinical decisions → potential SaMD trigger

**Status:** DECIDED (current classification); OPEN (monitoring for trigger points)
**Date:** 8 March 2026
**Dependencies:** D07 (professional view), D08 (GDPR)

---

## D11 — For Organisations page: honest capability statement

**Decision:** The For Organisations page describes services Nina can actually deliver based on her clinical research background (patient-facing documents, ethics committee submissions, plain-language materials). It does not promise infrastructure, API integrations, or enterprise software that doesn't exist.

**Rationale:** Misrepresenting capability to potential B2B contacts is a reputational risk and an integrity issue. The honest framing — "early stage, looking for pilot partners" — is both accurate and more credible to experienced NHS and pharma stakeholders than overstated claims.

**Status:** DECIDED
**Date:** 8 March 2026

---

## D12 — Credentials visibility

**Decision:** Nina's clinical research credentials appear prominently on the homepage (credentials strip), on the For Organisations page (credentials block), and subtly in the footer of every page ("Built by Nina Arden — MSc Clinical Trials, UCL"). They do not appear inline on trial cards or results pages.

**Rationale:** Credentials serve two distinct purposes: (1) patient trust — users need to know this was built by someone with domain knowledge, not a random developer; (2) B2B credibility — organisations need to know the builder understands the clinical research context. Homepage placement serves purpose 1; For Organisations placement serves purpose 2. Footer placement provides a persistent lightweight signal without cluttering patient-facing content.

**Status:** DECIDED
**Date:** 8 March 2026
