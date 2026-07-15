---
title: Versium
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: ["[[signals-and-abm]]"]
tags: [tool, enrichment, ad-matching, email-hash, meta, google-ads]
---

# Versium

Email hash provider used in Clay for matching contacts to ad platform audiences. Converts email addresses into hashed identifiers that Facebook/Meta and Google Ads use for custom audience matching.

## How It Works

1. Enrich contacts in Clay with Versium to get email hashes
2. Use [[conditional-runs]] to filter out non-ICP contacts
3. Push hashed audience to Meta or Google Ads via Clay's native ad audience export

## Ad Audience Export Flow

```
Enriched contacts → Versium email hash → Filter by ICP → Create ad audience → Push to Meta/Google
```

Clay can natively create a **custom Meta audience**: Exports → Create ad audience → connect Meta Ad Account → Contact List → map fields. Processing takes ~48 hours, and Clay shows the match rate after sync.

## Use Cases

- **ABM ad campaigns** — target specific accounts with personalized ads
- **Retargeting** — serve ads to website visitors identified through Clay
- **Lookalike audiences** — seed Meta/Google with your best customers to find similar prospects

## See Also

- [[abm-architecture]] — Versium in the ABM ad intelligence workflow
- [[clay-signals]] — ad engagement as a signal source
- [[conditional-runs]] — filtering contacts before ad push
