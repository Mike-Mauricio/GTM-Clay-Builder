---
title: Waterfall Enrichment
type: concept
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]"]
tags: [enrichment, waterfall, credit-efficiency, data-providers]
---

# Waterfall Enrichment

A multi-provider enrichment pattern where Clay queries data providers in sequence, stopping at the first successful result. Providers are ordered cheapest-first to minimize credit spend. Credits are refunded on misses — you only pay when a provider returns data.

## How It Works

1. Clay sends the request to Provider A (cheapest)
2. If Provider A returns data → done, use that result
3. If Provider A misses → try Provider B (next cheapest)
4. Continue through the chain until data is found or all providers are exhausted

**Example:** Funding Stage enrichment waterfall
- IntelliSense (1 credit) → PitchBook (3 credits) → DealRoom (4 credits)
- If IntelliSense has the data, you pay 1 credit. If only DealRoom has it, you pay 4. Credits for missed providers are refunded.

## Pre-Configured Waterfalls

Clay provides pre-configured waterfall sequences for common enrichment types. Users can:
- **Reorder providers** — Change the sequence based on data quality preferences
- **Add/remove providers** — Customize the waterfall for specific use cases
- **Set provider-specific inputs** — Some providers need different identifiers

## Key Waterfall Types

| Enrichment | Purpose | Typical Providers |
|-----------|---------|-------------------|
| Work Email | Find business email | Multiple providers, cheapest first |
| Funding Stage | Company funding round | IntelliSense → PitchBook → DealRoom |
| Company Data | Firmographics | Multiple, varies by data point |
| Phone Number | Direct dial / mobile | Multiple providers with fallthrough |
| Jobs | Hiring data | PredictLeads → Google Jobs → Clay Native |

## Design Principles

1. **Cheapest first.** Always order by credit cost ascending. No reason to spend 4 credits when 1-credit data is available.
2. **Quality vs. cost tradeoff.** Sometimes a more expensive provider has better data for your specific ICP. Test and adjust ordering.
3. **Test with 10 rows.** Always run waterfalls on a small batch first. Review hit rates per provider before scaling.
4. **Gate with [[conditional-runs]].** Don't run expensive waterfalls on records that haven't passed basic qualification.

## Relationship to Jigsaw

Waterfalls are the primary mechanism for collecting [[jigsaw-framework|edge data]] — the firmographic and demographic context that sits between corner pieces and fill. They're systematic and provider-driven, unlike [[claygent]] which handles custom fill data.

## See Also

- [[credit-optimization]] — broader cost management strategies
- [[conditional-runs]] — gating waterfalls behind qualification
- [[clay-email-waterfall]] — specific email waterfall implementation
- [[jigsaw-framework]] — where waterfalls fit in the data strategy
