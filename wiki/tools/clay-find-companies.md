---
title: Clay Find Companies
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]"]
tags: [clay-feature, find, company-discovery, native-dataset]
---

# Clay Find Companies

Clay's native company discovery feature powered by 100+ data providers. The primary way to source B2B company targets into Clay for enrichment and outbound.

## How It Works

1. Create a new Workbook
2. Select "Find Companies"
3. Apply filters to define your target list
4. Preview results before importing
5. Import into table (skip default enrichments to conserve credits on trial)

## Available Filters

| Filter | Description |
|--------|-------------|
| Industry | Company industry/vertical classification |
| Headcount | Employee count ranges |
| Location | HQ or office location |
| Keywords | Terms in company description |
| Founding Date | Company age / founding year |

## Important: Snapshot vs. Live Data

Find Companies returns **self-reported snapshot data** — a point-in-time view from Clay's aggregated database. This means:
- Data may be stale (headcount from 6 months ago, old industry classifications)
- Accuracy requires validation through Enrich actions
- Don't treat imported data as ground truth — verify with [[waterfall-enrichment|waterfall enrichments]]

## Workbooks vs. Tables

- **Workbooks** — Containers that hold one or more tables. Created when you start a new Find flow.
- **Tables** — Individual data grids within a workbook. Each Find action creates a table.

## Default Enrichments Warning

When importing, Clay may offer to run default enrichments automatically. For new users or credit-conscious workflows, **skip these** — you'll have more control running enrichments manually after import.

## Output: Corner Pieces

Find Companies produces [[jigsaw-framework|corner pieces]]:
- Company domain
- Company LinkedIn URL
- Company name

These unlock all downstream [[waterfall-enrichment|waterfall enrichments]] and [[claygent]] queries.

## See Also

- [[clay-find-people]] — find contacts at discovered companies
- [[clay-google-maps]] — alternative for local/SMB businesses
- [[jigsaw-framework]] — Find Companies provides corner pieces
- [[fete-framework]] — Find Companies is the first step in FETE
