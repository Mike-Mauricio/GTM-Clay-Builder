---
title: Zeliq
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: ["[[best-practices-getting-started]]"]
tags: [tool, enrichment, phone, email, emea, waterfall, verification]
---

# Zeliq

Contact enrichment provider with strong coverage in EMEA markets and specialized industries (remodeling, construction). Finds and verifies phone numbers and email addresses linked to professional profiles. Valuable as a waterfall provider for non-US contact data where other providers have gaps.

## Actions

### Find Phone Number

Locates and validates phone numbers associated with professional profiles, with a focus on EMEA coverage.

**Inputs:**
- Professional profile URL (e.g., `https://www.linkedin.com/in/johndoe/`)
- Work email (e.g., `john.doe@clay.com`)

**Outputs:**
- Phone numbers (array)
- Most probable phone number
- Email address
- LinkedIn profile URL

### Find Email

Finds and verifies work email addresses using either a LinkedIn URL or name + domain.

**Inputs (one of):**
- Professional profile URL, OR
- Person's full name + company domain

**Outputs:**
- Most probable email
- Most probable email status (verification status)
- Emails (full list with verification status)
- First name, last name
- Company domain
- LinkedIn profile URL

## Waterfall Positioning

Zeliq is most valuable as a mid-to-late waterfall provider for EMEA-heavy pipelines. Position it after cheaper US-focused providers but before expensive last-resort options:

```
US providers (cheap) → Zeliq (EMEA strength) → Premium fallbacks
```

For contacts in specialized industries (construction, remodeling) where mainstream providers underperform, Zeliq may be worth running earlier in the chain.

Both actions support [[conditional-runs]] via the "Only run if" setting — gate behind qualification or missing data to avoid unnecessary credit spend.

## See Also

- [[waterfall-enrichment]] — multi-provider chaining strategy
- [[clay-email-waterfall]] — email-specific waterfall implementation
- [[people-enrichment-pipeline]] — full contact enrichment workflow
- [[email-verification]] — understanding verification statuses returned by Zeliq
