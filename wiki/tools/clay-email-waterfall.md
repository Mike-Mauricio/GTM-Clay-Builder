---
title: Clay Email Waterfall
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]", "[[best-practices-getting-started]]"]
tags: [clay-feature, enrichment, email-finding, waterfall, validation]
---

# Clay Email Waterfall

Clay's multi-provider email finding enrichment that chains multiple email providers in a [[waterfall-enrichment|waterfall pattern]] with built-in validation. The primary way to find work email addresses for contacts in Clay.

## How It Works

1. Add enrichment → search "Work Email"
2. Configure the waterfall (add/reorder providers)
3. Set input columns:
   - **Company Domain** (required)
   - **Personal Social Profile URLs** (recommended — especially LinkedIn)
   - **Full Name + Company Name** (fallback if no social URLs)
4. Configure validation settings
5. Test on 10 rows → review → scale

## Input Priority

Best results come from providing multiple inputs. In order of effectiveness:
1. **LinkedIn URL + Company Domain** — highest accuracy
2. **Full Name + Company Domain** — good fallback
3. **Company Domain alone** — lowest accuracy, may return generic addresses

## Email Validation (ZeroBounce)

Every email waterfall includes a validation step (ZeroBounce by default, swappable):

| Validation Result | Meaning | Action |
|------------------|---------|--------|
| Valid | Email confirmed deliverable | Safe to send |
| Invalid | Email bounces | Do not send |
| Catch-all | Domain accepts all addresses | Use caution |

### Catch-All Handling

Catch-all domains accept any email address — so validation can't confirm the specific address exists. Clay offers a toggle: **"Only mark Safe to Send as valid"**

- **On** — Conservative. Catch-all emails marked as not safe to send. Lower volume, higher deliverability.
- **Off** — Aggressive. Catch-all emails included. Higher volume, risk of bounces.

## Hidden Validation Columns

After running an email waterfall, Clay creates validation detail columns that are **hidden by default**. To see them:
1. Open the Columns Panel
2. Look for ZeroBounce validation columns
3. Unhide to see detailed validation results per email

## Credit Mechanics

- Each provider in the waterfall has its own credit cost
- **Credits refunded on miss** — if a provider can't find an email, you get the credits back
- Cheapest providers run first (per [[waterfall-enrichment]] principles)
- Validation (ZeroBounce) has its own credit cost

## Best Practices

1. **Provide LinkedIn URLs** — dramatically improves hit rate over name+domain alone
2. **Test 10 rows first** — check hit rate and quality before scaling
3. **Review catch-all handling** — decide your risk tolerance before sending
4. **Unhide validation columns** — understand why specific emails were marked valid/invalid
5. **Use [[conditional-runs]]** — only run email waterfalls on records that need emails (Is Email Empty = true)

## See Also

- [[waterfall-enrichment]] — the general pattern email waterfalls implement
- [[email-verification]] — detailed breakdown of all five verification statuses and their deliverability implications
- [[work-email-provider-benchmark]] — data test comparing 12 work email providers across SMB and enterprise datasets
- [[personal-email-provider-benchmark]] — data test comparing 5 personal email providers
- [[clay-find-people]] — prerequisite: find contacts before finding their emails
- [[crm-export-dedup]] — use validated emails as unique identifiers for CRM dedup
- [[conditional-runs]] — gate email waterfalls behind qualification
- [[zeliq]] — EMEA-strong email/phone provider for waterfall inclusion
