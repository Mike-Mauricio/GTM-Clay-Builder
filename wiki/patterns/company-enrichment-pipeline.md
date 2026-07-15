---
title: Company Enrichment Pipeline
type: pattern
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]"]
tags: [pattern, enrichment, company-data, pipeline, fete]
---

# Company Enrichment Pipeline

The standard pattern for discovering and enriching company data in Clay, following [[fete-framework|FETE]] and [[jigsaw-framework|Jigsaw]].

## Architecture

```
Find Companies → Corner Pieces → Edge Enrichments → Fill Enrichments → Transform → Export
```

### Phase 1: Find (Corner Pieces)
**Goal:** Get companies into Clay with minimum viable identifiers

Sources:
- [[clay-find-companies]] — Native dataset (100+ providers)
- [[clay-google-maps]] — Local/SMB businesses
- CSV import — From external lists
- CRM import — From existing database

**Required outputs:** Company domain, Company LinkedIn URL

### Phase 2: Enrich — Edges
**Goal:** Add firmographic and technographic context

Run [[waterfall-enrichment|waterfall enrichments]] for:
- **Firmographic:** Industry, headcount, HQ location, founding date, revenue
- **Funding:** Funding stage, last round amount, total raised
- **Technographic:** Tech stack, tools used, integrations
- **Growth:** Hiring velocity, website traffic, social presence

Order: cheapest providers first. Test 10 rows per enrichment. Gate expensive enrichments behind [[conditional-runs]].

### Phase 3: Enrich — Fill
**Goal:** Add custom signals for scoring and personalization

Use [[claygent]] for:
- B2B vs. B2C classification
- Specific technology/integration mentions
- Free trial availability
- Value proposition extraction
- Competitive tool usage

Use [[ai-formulas]] to derive:
- Composite scores from multiple edge signals
- Boolean qualification flags
- Segment classifications

### Phase 4: Transform
**Goal:** Clean data for downstream use

- [[clay-normalization-tools|Normalize]] company names (strip Inc., LLC, etc.)
- Normalize locations for CRM consistency
- Format phone numbers
- Clean whitespace from imported data

### Phase 5: Export
**Goal:** Activate data in downstream systems

- Export to CRM via [[crm-export-dedup]] pattern
- Export to Google Sheets for sharing/analysis
- CSV download for one-time transfers

## Credit Budget Example

For a 1,000-company enrichment:
- Find: Free (from Clay's dataset or import)
- Edges: ~2-5 credits/company × 1,000 = 2,000-5,000 credits
- Fill (Claygent): ~1-3 credits/company × qualified subset = variable
- Transform: Free (AI Formulas + normalization)
- Export: Free (CSV) or minimal (CRM integration)

Gate fill enrichments behind edge-based qualification to control costs.

## See Also

- [[people-enrichment-pipeline]] — the companion pattern for contacts
- [[fete-framework]] — the workflow this pipeline implements
- [[jigsaw-framework]] — the data strategy this pipeline follows
- [[experiment-before-scale]] — test each phase before scaling
