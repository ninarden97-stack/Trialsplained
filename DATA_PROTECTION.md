# DATA_PROTECTION.md — Trialsplained
## DPO-Level Data Protection Framework
*Last updated: 8 March 2026*
*This document is for transparency purposes and does not constitute legal advice.*

---

## 1. Data Controller Details

| Field | Detail |
|-------|--------|
| Controller | Nina Arden (sole trader) |
| Product | Trialsplained |
| Contact | hello@trialsplained.com |
| ICO Registration | Not yet registered — required before public launch |
| DPO | Not required at current scale — Nina Arden acts as responsible person |

---

## 2. GDPR Principles — How Trialsplained Complies

| Principle | How Applied |
|-----------|------------|
| Lawfulness, fairness, transparency | No personal data collected. AI labelling on all content. Feedback form purpose stated clearly. |
| Purpose limitation | Feedback emails used only to correct inaccuracies. Not used for marketing. |
| Data minimisation | Zero personal data collected by design. Search terms not stored. |
| Accuracy | AI summaries include last-verified dates. Feedback mechanism exists. 48-hour correction commitment. |
| Storage limitation | Feedback emails deleted after 12 months. No other storage. |
| Integrity and confidentiality | No databases. No user accounts. No data transmission beyond feedback email. |
| Accountability | This document. ETHICS.md. RISK_REGISTER.md. All publicly available on GitHub. |

---

## 3. Lawful Basis for Processing

| Processing Activity | Lawful Basis | Notes |
|--------------------|-------------|-------|
| Serving trial information | Not applicable — no personal data processed | Public registry data only |
| Receiving feedback emails | Legitimate interests | Low risk; user-initiated; no health data |
| B2B contact emails | Legitimate interests | Business contact; no health data |

---

## 4. Special Category Data Assessment

Health data is Article 9 special category data under UK GDPR. It requires explicit consent or another specific condition to process.

**Current assessment: Trialsplained does not process any special category data.**

Architectural safeguards preventing special category data collection:
- No user accounts or profiles
- No health questionnaires or eligibility screening
- No integration with health records
- Feedback form explicitly states: "Do not include personal health information"
- Session data (saved trials) stored in browser only — never transmitted

**Trigger for reassessment:**
Any feature involving user health data requires a full DPIA before implementation and must not be built without legal review.

---

## 5. Data Subject Rights

Under UK GDPR, individuals have the following rights. Current position:

| Right | Applicable? | How Handled |
|-------|-------------|------------|
| Right of access | Limited — we hold almost no personal data | Respond to requests within 1 month |
| Right to erasure | Limited — feedback emails only | Delete on request within 30 days |
| Right to rectification | Not applicable | N/A |
| Right to portability | Not applicable | N/A |
| Right to object | Not applicable | N/A |
| Right to restrict processing | Not applicable | N/A |

**Contact for data subject requests:** hello@trialsplained.com

---

## 6. Third-Party Data Processors

| Processor | Data Shared | Safeguard |
|-----------|-------------|-----------|
| Google (Gemini via Lovable) | Trial registry text only — no personal data | Google Cloud DPA in place via Lovable |
| Lovable (hosting) | App data — no personal data | Lovable Terms of Service |
| ClinicalTrials.gov | None — we query their API | Public API; no data shared |
| Email provider (Gmail) | Feedback email content | Standard Gmail ToS; low risk |

---

## 7. International Data Transfers

- App hosted in EU (eu-west-1 region) — selected deliberately for GDPR compliance
- No personal data transferred outside UK/EU
- AI processing via Lovable/Google — EU data centres

---

## 8. Privacy Notice — Required Before Public Launch

Draft structure for privacy notice:

**What information we collect:**
We do not collect personal information when you use Trialsplained. We do not require you to create an account, provide your name, or share any health information.

If you use the "Is this accurate?" feedback button, your message is sent to feedback@trialsplained.com. Please do not include personal health information in feedback messages.

**How we use information:**
Feedback messages are used only to correct inaccuracies in our trial summaries. We do not use them for marketing or share them with third parties.

**Your rights:**
You have the right to request deletion of any feedback message you have sent. Contact hello@trialsplained.com.

**Cookies:**
Trialsplained uses only technically necessary cookies to remember your accessibility preferences (text size, high contrast). No tracking or advertising cookies are used.

**Contact:**
Data protection queries: hello@trialsplained.com

---

## 9. Cookie Audit

| Cookie | Purpose | Type | Consent Required? |
|--------|---------|------|-----------------|
| text-size preference | Remembers A/A+ setting | Functional | No — technically necessary |
| contrast preference | Remembers high contrast setting | Functional | No — technically necessary |
| welcome-banner-dismissed | Remembers if banner was dismissed | Functional | No — technically necessary |

**No tracking cookies. No advertising cookies. No analytics cookies (until Plausible added in v0.2 — will update).**

PECR compliance: Functional cookies only — no consent banner required under current configuration.

---

## 10. Data Breach Response Plan

In the unlikely event of a data incident:

**Step 1 — Identify and contain (within 24 hours)**
- Identify what data may have been affected
- Contain the breach (e.g. take down affected feature)

**Step 2 — Assess (within 48 hours)**
- Is personal data involved?
- How many individuals affected?
- What is the risk of harm?

**Step 3 — Report (within 72 hours if required)**
- If likely to result in risk to individuals: report to ICO within 72 hours
- ICO reporting: https://ico.org.uk/for-organisations/report-a-breach/

**Step 4 — Notify affected individuals (if high risk)**
- Contact affected individuals without undue delay

**Step 5 — Document**
- Log all breaches in incident register regardless of severity
- Record: date, nature, categories of data, number of people, consequences, actions taken

---

## 11. Pre-Launch Compliance Checklist

- [ ] ICO registration completed (£40/year)
- [ ] Privacy notice published on site
- [ ] Cookie notice reviewed — current config does not require banner
- [ ] Terms of use published
- [ ] Feedback form updated with privacy statement
- [ ] Data retention policy documented and actioned
- [ ] Third-party processor agreements reviewed

---

*This document demonstrates DPO-level thinking applied to a prototype product. The current data risk is low by design. The purpose of this document is to show that data protection has been considered architecturally — not bolted on after the fact.*

*Nina Arden — MSc Clinical Trials, UCL*
