# PRODUCT_VISION.md — Trialsplained

*Last updated: 8 March 2026*

---

## The Problem

Clinical trial consent forms and registry listings are written at undergraduate reading level. Most adults in the UK read at approximately a 14-year-old reading level (Lancet, 2024). Over 80% of clinical trials face recruitment delays. Underrepresentation of diverse populations in trials produces evidence that doesn't generalise.

The information gap is not a secret. It is documented, published, and unresolved.

Existing tools:
- **ClinicalTrials.gov** — 400,000+ studies, written for researchers
- **NIHR Be Part of Research** — a database for researchers, not a patient translator
- **NHS App** — announced trial sign-up integration (2025), portal only, no plain language layer
- **EC Trial Finder** — oncology only, for NHS clinical staff

No existing tool provides a plain-language AI layer designed for general public users.

---

## Users

**Primary users (consumer product):**
- Patients recently diagnosed with a condition
- Family members and carers researching options
- Members of the public interested in preventative medicine, mental health, longevity
- Researchers wanting a plain-language overview

**Secondary users (B2B product — future):**
- NHS trusts seeking to improve patient-facing trial recruitment communications
- Contract Research Organisations (CROs) seeking to reduce recruitment delays
- Patient advocacy groups and charities providing trial information to members
- Pharmaceutical companies seeking accessible plain-language summaries for public-facing materials

---

## Differentiation

| Feature | ClinicalTrials.gov | NIHR BPOR | Trialsplained |
|---|---|---|---|
| Plain English summaries | ✗ | ✗ | ✓ |
| Designed for general public | ✗ | Partial | ✓ |
| Placebo / commitment disclosure | Buried | Buried | Prominent |
| WhatsApp share | ✗ | ✗ | ✓ |
| Print for GP | ✗ | ✗ | ✓ |
| AI transparency labelling | N/A | N/A | ✓ |
| No data collection | ✗ | ✗ | ✓ |
| Withdrawal rights explained | ✗ | ✗ | ✓ |

---

## Success Metrics

See `METRICS.md` for full details.

Primary: Trial card expansion rate (>40% of sessions) | Share actions (>15% of expansions)  
Secondary: Searches completed | Accuracy feedback rate (<2%)

---

## Conditions (v1)

Diabetes | Cardiovascular disease | Migraines | Dementia | Mental health & anxiety | Longevity

Selected to reflect how the general public searches for health information — not research community priorities.

---

## Version History

| Version | Date | Description |
|---|---|---|
| v0.1 | 8 March 2026 | Initial build — SheBuilds IWD 2026 |

---

## Roadmap

**v0.2 (next 30 days)**
- Additional conditions
- Improved mobile WhatsApp share formatting
- Accuracy feedback review and correction cycle

**v0.3 (60–90 days)**
- Language translation (priority: Polish, Bengali, Urdu)
- Expanded condition coverage
- Structured accuracy audit process

**v1.0 (6 months)**
- API integration with live ClinicalTrials.gov data
- B2B pilot with one NHS trust or CRO
- Privacy-respecting analytics (Plausible)

---

---

# REGULATORY_FRAMEWORK.md — Trialsplained

*Last updated: 8 March 2026*

---

## Current Position

Trialsplained is **not currently a medical device** under UK, EU, or US frameworks.

The product:
- Does not diagnose any condition
- Does not recommend treatment for any individual
- Does not personalise results based on health data
- Does not integrate with health records
- Does not make clinical decisions or support clinical decision-making

It is an information accessibility tool — the equivalent of a plain-language explainer leaflet — applied to publicly available registry data.

---

## Relevant Frameworks

### UK — UKCA / MHRA Software as a Medical Device (SaMD)
The MHRA's Software as a Medical Device guidance (2024) classifies software as a medical device if it is intended to be used for a medical purpose — including diagnosis, prevention, monitoring, treatment, or alleviation of disease.

Plain-language information provision is not classified as a medical purpose under this guidance. The product remains outside SaMD classification as long as it does not make individual clinical recommendations.

### EU — MDR (EU) 2017/745
The EU MDR applies to medical devices placed on the EU market. Rule 11 of Annex VIII covers software. The same principle applies: software that provides only general information does not meet the definition of a medical device.

### US — FDA Digital Health / SaMD
FDA guidance on Clinical Decision Support Software (2022) distinguishes between software that displays/retrieves information (not regulated) and software that analyses patient data to make clinical recommendations (regulated). Trialsplained currently falls in the unregulated category.

---

## Trigger Points for Reclassification

The following product changes would require regulatory engagement before implementation:

| Change | Likely Regulatory Implication |
|---|---|
| Personalised trial recommendations based on user health profile | SaMD reclassification likely — MHRA engagement required |
| Integration with NHS health records (e.g. via FHIR API) | SaMD reclassification likely; data processing requirements under UK GDPR |
| Eligibility screening feature ("Are you eligible?") | SaMD reclassification likely |
| Clinical decision support for healthcare professionals | Definite SaMD classification; full MDR/UKCA conformity required |
| Storage of personal health data | UK GDPR Article 9 (special category data) compliance required |

---

## Data Handling (Current)

- No personal data collected
- No cookies beyond technically necessary
- No analytics tracking individuals
- Session-based saved trials — stored in browser only, not transmitted
- Feedback form (free text only) — submitted to feedback@trialsplained.com — no health data requested

Current data handling is compliant with UK GDPR by design (data minimisation principle).

---

## Planned Compliance Steps

As the product scales:
1. Formal DPIA (Data Protection Impact Assessment) before any user data collection
2. Privacy policy publication
3. MHRA pre-submission discussion if any personalisation features are added
4. Legal review before B2B contracts with NHS entities (NHS DSP Toolkit requirements)

---

*This document is for transparency purposes and does not constitute legal advice. Regulatory positions are based on guidance current as of March 2026.*
