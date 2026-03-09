# LEGAL_AND_IP.md — Trialsplained
*Last updated: 8 March 2026*
*This document is for transparency and portfolio purposes. It does not constitute legal advice.*

---

## 1. Intellectual Property — What Nina Owns

### The Product
Trialsplained is an original work created by Nina Arden on 8 March 2026. The following are owned by Nina Arden:

- The product name "Trialsplained" and tagline "Clinical trials, explained like a human"
- The UI/UX design, layout, and visual identity
- All written content — summaries, copy, page text, documentation
- The product concept, architecture, and feature decisions
- All GitHub documentation (PM spec, ethics framework, risk register, decision log, regulatory framework)

### What Nina Does Not Own
- ClinicalTrials.gov data — this is public domain, provided by the US National Library of Medicine
- NIHR trial data — publicly available under Open Government Licence
- The Lovable platform — Nina owns the output, not the builder
- Gemini AI model — owned by Google; Nina owns the prompts and outputs, not the model

### Protecting the Name
"Trialsplained" is not yet a registered trademark. Steps to take before commercial launch:
- UK trademark search: https://www.gov.uk/search-for-trademark
- Register as a UK trademark (Class 42 — software services; Class 44 — medical services) — approx £170–200
- Register trialsplained.com domain (already done) — maintain renewal

---

## 2. Copyright Position

### Nina's Content
All original written content, documentation, and design created by Nina Arden is automatically protected by UK copyright law from the moment of creation. No registration required in the UK.

This includes:
- All plain-English trial summaries written for the demo
- All product documentation
- The pitch deck
- Substack articles

### AI-Generated Content
The legal position on AI-generated content copyright is evolving. Current UK position (as of 2026):
- UK Copyright, Designs and Patents Act 1988 s.9(3): computer-generated works are protected for 50 years, with copyright owned by "the person who made the arrangements necessary for the creation"
- This means Nina, as the person who designed the prompts, system, and product, has the strongest claim to ownership of AI-generated outputs
- This is not fully settled law — document your prompt authorship (already done in GitHub)

---

## 3. Data Protection — GDPR Position

### Current Status: Low Risk
Trialsplained currently collects no personal data. This is a deliberate design decision that minimises GDPR obligations.

### What This Means Practically
| Data Type | Collected? | Legal Basis Required? |
|-----------|-----------|----------------------|
| Name | No | N/A |
| Email address | No | N/A |
| Health data | No | N/A |
| Location | No | N/A |
| Search terms | No (session only) | N/A |
| IP address | No (no analytics) | N/A |
| Feedback form content | Yes — free text email | Legitimate interests |

### The Feedback Form
When a user submits "Is this accurate?" feedback, a plain text email is sent to feedback@trialsplained.com. This is the only personal data risk:
- Users are told not to include personal health information
- No health data is requested or stored
- This is low-risk processing under UK GDPR
- A privacy notice is required before public launch

### Before Public Launch — Required
- [ ] Privacy notice published on the site
- [ ] Cookie notice (if any cookies added)
- [ ] Terms of use published
- [ ] Data Protection registration with ICO (required if processing personal data — £40/year for small organisations)

### Before B2B Contracts — Required
- [ ] Data Processing Agreement (DPA) template for organisation partners
- [ ] DPIA (Data Protection Impact Assessment) if processing special category data
- [ ] NHS DSP Toolkit review if contracting with NHS entities

---

## 4. Liability Position

### What Trialsplained Is Not Liable For
As an information tool (not a medical device, not clinical advice):
- Trialsplained cannot be held liable for a user's decision to join or not join a trial
- The disclaimer on every page and in the footer establishes this clearly
- The "speak to your doctor" guidance is a legal as well as ethical requirement

### Risk Reduction Measures Already in Place
- Disclaimer on every page
- AI labelling on every summary
- "Always check the official listing" on every card
- "This is not medical advice" in footer of every page
- No eligibility screening (avoids clinical recommendation liability)
- No "Apply now" buttons (avoids acting as a recruitment agent)

### What Would Increase Liability
- Adding eligibility screening
- Storing user health data
- Making treatment recommendations
- Accepting payment from sponsors for trial placement
- Claiming summaries are medically verified

### Professional Indemnity Insurance
Not required for the current prototype. Required before:
- Any paid B2B contracts
- Any NHS engagement
- Any feature that could be construed as clinical advice

Approximate cost: £200–500/year for a sole trader operating in health information.

---

## 5. Terms of Use — Required Before Public Launch

Draft terms of use must cover:
1. What the service is and is not (information only, not medical advice)
2. AI-generated content disclaimer
3. No liability for decisions made based on content
4. User must verify all information with official sources
5. Feedback submissions — what happens to them
6. Acceptable use (no scraping, no commercial reuse of content)
7. Governing law: England and Wales

---

## 6. Third-Party Obligations

| Service | Obligation |
|---------|-----------|
| ClinicalTrials.gov API | Attribution required — "Data from ClinicalTrials.gov" on every page ✅ Already done |
| NIHR data | Open Government Licence — attribution required ✅ Already done |
| Lovable platform | Terms of service — Nina owns her content and data |
| Google Gemini (via Lovable) | Outputs are owned by the user (Nina) under Google's terms |
| Namecheap domain | Annual renewal — set to auto-renew |

---

## 7. Open Source Consideration

The GitHub repository is currently public. This means:
- Anyone can view the code and documentation
- Anyone can fork it
- This is intentional — it demonstrates transparency and PM thinking

If the product becomes commercial, consider:
- Adding a licence file (MIT for open source; or a custom licence restricting commercial use)
- Currently no licence = default copyright applies = others cannot legally reuse the code without permission

Recommendation: Add `LICENSE.md` to the repo with this text for now:
> "© Nina Arden 2026. All rights reserved. This code is shared for transparency and portfolio purposes. Commercial use, redistribution, or derivative products require written permission from the author."

---

*For legal advice specific to your situation, consult a solicitor specialising in technology and health law. The Clinic (UCL's free legal clinic for alumni) may be a relevant resource.*
