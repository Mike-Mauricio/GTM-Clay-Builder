---
title: Email Verification
type: concept
created: 2026-07-14
updated: 2026-07-14
sources: ["[[best-practices-getting-started]]"]
tags: [email, verification, deliverability, enrichment, data-quality]
---

# Email Verification

Clay shows verification status for every email address through detailed checks. Understanding these statuses is critical for maintaining deliverability, avoiding bounces, and focusing outreach on reachable contacts.

## Five Statuses

| Status | Meaning | Deliverable? | Action |
|--------|---------|-------------|--------|
| **Valid** | Specific, active address connected to a real, monitored inbox | Yes | Safe to email. Ideal for outreach. |
| **Invalid** | Address does not exist — misspelling, deactivated account, or dead domain | No | Remove from list immediately. Will bounce. |
| **Catch-all** | Domain accepts all addresses, even non-existent ones. No guarantee a real inbox is behind it. | Maybe | Proceed with caution. Lower engagement expected. Consider separate send pool. |
| **Unknown** | Couldn't be verified — typically a temporary mail server issue | Maybe | Retry verification later. May be valid but unconfirmable right now. |
| **Role-based** | Tied to a function, not a person (e.g., `info@`, `sales@`, `support@`). Monitored by teams. | Yes, but low engagement | Use only when no personal address is available. Expect lower response rates. |

## Deliverability Impact

### Safe to Send
- **Valid** emails — your best targets. These should be the default for outreach campaigns.

### Risky
- **Catch-all** — technically deliverable but unreliable. Some outreach teams send to catch-all addresses from a separate sending domain to protect primary domain reputation.
- **Unknown** — may become verifiable later. Re-check before sending.
- **Role-based** — deliverable but impersonal. Lower engagement rates.

### Do Not Send
- **Invalid** — guaranteed bounce. Sending to invalid addresses damages sender reputation and can trigger blacklisting.

## Re-Verification

Email verification statuses change over time as domains update settings or addresses become inactive. Best practices:

- **Re-verify before every campaign** — don't assume stale data is still accurate
- **Re-verify catch-all and unknown addresses periodically** — they may resolve to valid or invalid
- **Build re-verification into [[clay-audiences]]** — use scheduled sources to keep email status current

## Workflow Integration

In Clay, email verification typically slots into the [[people-enrichment-pipeline]] after the [[clay-email-waterfall]]:

```
Find email (waterfall) → Verify email → Route by status → Send to qualified only
```

Use [[conditional-runs]] to gate downstream enrichments and exports behind verification status:
- "Only export if Email Status = Valid"
- "Only run phone waterfall if Email Status = Invalid" (pivot to phone outreach)

## See Also

- [[clay-email-waterfall]] — multi-provider email finding with validation
- [[people-enrichment-pipeline]] — where verification fits in the full pipeline
- [[conditional-runs]] — gating exports behind email status
- [[zeliq]] — enrichment provider that returns verification status with emails
- [[clay-sequencer]] — email sending tool that benefits from verified addresses
