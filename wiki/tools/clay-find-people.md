---
title: Clay Find People
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]"]
tags: [clay-feature, find, contact-discovery, people-search]
---

# Clay Find People

Clay's contact discovery feature that layers on top of company data. Finds people at target companies based on job title, seniority, department, and other persona-based filters.

## Prerequisites

Find People requires company data with [[jigsaw-framework|corner pieces]] — specifically:
- Company LinkedIn URLs (preferred) or
- Company domains (acceptable fallback)

LinkedIn URLs produce better results than domains alone.

## How It Works

1. Open an existing companies table
2. Actions → "Find People at These Companies"
3. Set table reference and company identifier column
4. Define persona filters
5. Preview and iterate
6. Import contacts (skip default enrichments)

## Available Filters

| Filter | Description |
|--------|-------------|
| Job Title | Keywords in title (e.g., "VP of Sales", "Head of Marketing") |
| Function | Department/function classification |
| Seniority | Level (C-suite, VP, Director, Manager, etc.) |
| Experience Level | Years of experience ranges |
| Location | Person's location |
| Certifications | Professional certifications |
| Languages | Languages spoken |
| Education | Degree, school, field of study |
| Exclusions | Titles or keywords to exclude |

## Linked Tables

A critical [[credit-optimization]] technique:

When you find people from a companies table, Clay creates a **linked table** — the people table references the company table. This means:
- Company-level enrichments (industry, funding, tech stack) are enriched **once** on the company table
- Every contact at that company can pull from the same company data
- No need to re-enrich company fields per person — massive credit savings

## Iterative Refinement

Don't expect to nail your persona filters on the first try:
1. Start with broad filters
2. Preview results
3. Refine (add exclusions, narrow seniority, adjust titles)
4. Preview again
5. Import when the results match your target persona

## See Also

- [[clay-find-companies]] — prerequisite: find companies before people
- [[clay-email-waterfall]] — next step: find email addresses for contacts
- [[jigsaw-framework]] — Find People adds people-level corner pieces
- [[credit-optimization]] — linked tables save company-level enrichment costs
