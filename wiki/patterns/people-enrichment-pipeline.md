---
title: People Enrichment Pipeline
type: pattern
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]"]
tags: [pattern, enrichment, people-data, pipeline, fete]
---

# People Enrichment Pipeline

The standard pattern for discovering and enriching contact data in Clay. Typically follows a [[company-enrichment-pipeline]] — you find companies first, then find people at those companies.

## Architecture

```
Find People → Corner Pieces → Email Waterfall → Additional Enrichments → Transform → Export
```

### Phase 1: Find (Corner Pieces)
**Goal:** Get contacts into Clay with minimum viable identifiers

**Prerequisite:** A companies table with LinkedIn URLs or domains (from [[company-enrichment-pipeline]])

Process:
1. [[clay-find-people]] at target companies
2. Set persona filters (title, seniority, function, location)
3. Iterate on filters until results match target persona
4. Import contacts

**Required outputs:** LinkedIn URL, Full Name

### Phase 2: Enrich — Email Waterfall
**Goal:** Find verified work email addresses

Run [[clay-email-waterfall]]:
1. Configure waterfall providers (cheapest first)
2. Input: Company Domain + LinkedIn URL (best combination)
3. Configure validation (ZeroBounce) and catch-all handling
4. Test 10 rows → review hit rate → scale

### Phase 3: Enrich — Additional Contact Data
**Goal:** Add demographic and professional context

Available enrichments:
- **Phone numbers** — Direct dial, mobile (waterfall)
- **Social profiles** — Twitter, Facebook, Instagram, GitHub
- **Work history** — Previous companies, roles, tenure
- **Education** — Degree, school, field of study

Use [[conditional-runs]] — only enrich records that passed email validation.

### Phase 4: Enrich — Fill (via Claygent)
**Goal:** Custom research for personalization

Use [[claygent]] to research:
- Recent LinkedIn activity or posts
- Conference speaking history
- Published content or thought leadership
- Specific expertise or certifications

### Phase 5: Transform
**Goal:** Clean and format for outbound

- Normalize names and titles
- Calculate tenure and experience metrics with [[ai-formulas]]
- Create personalization snippets
- Build boolean qualification flags
- Generate composite scores

### Phase 6: Export
**Goal:** Push to activation systems

- [[crm-export-dedup]] — CRM with duplicate prevention
- Email sequencer — Direct push to outbound tools
- Google Sheets — For team review before activation

## Linked Tables: Credit Efficiency

When people are found from a companies table, Clay creates a linked table. This means:
- Company-level data (industry, funding, tech stack) is enriched **once** on the company table
- Every contact pulls from the same company data
- No per-person company enrichment spend

This is one of the most impactful [[credit-optimization]] techniques.

## See Also

- [[company-enrichment-pipeline]] — prerequisite: enrich companies first
- [[clay-find-people]] — the Find phase tool
- [[clay-email-waterfall]] — the critical enrichment step
- [[crm-export-dedup]] — the export pattern
- [[experiment-before-scale]] — test each phase before scaling
