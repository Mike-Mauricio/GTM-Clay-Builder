---
title: "Clay 101: GTM Automation"
type: source
created: 2026-07-13
updated: 2026-07-13
sources: ["https://university.clay.com"]
tags: [clay-academy, clay-101, fete, jigsaw, foundations]
---

# Clay 101: GTM Automation

**Source:** Clay University (university.clay.com)
**Type:** Video course (17 lessons)
**Level:** Beginner — foundational Clay knowledge
**Location:** `Knowledge/Clay/Lessons/Clay-101/`

## Overview

Clay's official introductory course covering the complete workflow lifecycle for GTM automation. Teaches two foundational frameworks — [[fete-framework|FETE]] (Find, Enrich, Transform, Export) and [[jigsaw-framework|Jigsaw]] (corner pieces → edges → fill) — then walks through each phase with hands-on lessons.

This course forms the foundation for all Clay work. Every concept introduced here compounds in advanced courses.

## Lesson Index

| # | Lesson | Phase | Key Concepts |
|---|--------|-------|-------------|
| 01 | Intro: FETE & Jigsaw | Framework | [[fete-framework]], [[jigsaw-framework]], blank canvas problem |
| 02 | Your First GTM Use Case | Framework | Three workflow examples, [[gtm-alpha]] |
| 03 | How to Experiment | Mindset | [[credit-optimization]], R&D budget, [[experiment-before-scale]] |
| 04 | Finding Companies | Find | [[clay-find-companies]], workbooks, filters, snapshot data |
| 05 | Finding People | Find | [[clay-find-people]], linked tables, persona targeting |
| 06 | Finding Businesses (Google Maps) | Find | [[clay-google-maps]], SMB prospecting, local discovery |
| 07 | Finding Jobs | Find | Jobs as source vs. enrichment, hiring signals |
| 08 | Enrich Intro | Enrich | Enrichment as GTM intelligence, Jigsaw "edges" |
| 09 | Enriching Company Data | Enrich | [[waterfall-enrichment]], firmographic/technographic data |
| 10 | Enriching People Data | Enrich | [[clay-email-waterfall]], ZeroBounce validation, catch-all handling |
| 11 | Enriching with Claygent | Enrich | [[claygent]], last mile data, prompt engineering |
| 12 | Transform: Normalize | Transform | [[clay-normalization-tools]], credit-free cleaning |
| 13 | Transforming with AI Formulas | Transform | [[ai-formulas]], deterministic transforms, zero-credit |
| 14 | Export Intro | Export | CSV export, export views, integration planning |
| 15 | Exporting to Google Sheets | Export | Live sync, Add Row, Lookup/Add/Update |
| 16 | Exporting to CRM | Export | [[crm-export-dedup]], conditional creates, duplicate prevention |
| 17 | Where to Go Next | Conclusion | Advanced paths, community resources |

## Key Takeaways

1. **Every Clay workflow follows FETE.** Find your targets, Enrich with context, Transform for quality, Export to activate. No exceptions.
2. **Jigsaw determines data strategy.** Start with corner pieces (domains, LinkedIn URLs), build edges (firmographics, demographics), then fill with specialized data.
3. **Waterfall enrichments are the default pattern.** Multiple providers, cheapest first, stop on first hit. Credits refunded on misses.
4. **Credit-free tools exist and matter.** AI Formulas and normalization tools cost zero credits — use them liberally for transformations.
5. **Claygent solves the "last mile."** When no database has the data you need, Claygent browses the web in real time. Requires good prompts with negative constraints.
6. **Always test before scaling.** Run 10 rows → review → 50 rows → review → full dataset. Never run enrichments on the full table first.
7. **CRM export requires dedup-first thinking.** Lookup existing contacts before creating new ones. Use conditional runs to prevent duplicates.

## Frameworks Introduced

- **[[fete-framework|FETE]]** — Find, Enrich, Transform, Export. The four-phase workflow pattern.
- **[[jigsaw-framework|Jigsaw]]** — Corner pieces (identifiers), Edges (context), Fill (specialized data). The data layering strategy.

## Cross-References

- Concepts: [[fete-framework]], [[jigsaw-framework]], [[waterfall-enrichment]], [[credit-optimization]], [[gtm-alpha]], [[conditional-runs]]
- Tools: [[claygent]], [[ai-formulas]], [[clay-normalization-tools]], [[clay-google-maps]], [[clay-find-companies]], [[clay-find-people]], [[clay-email-waterfall]]
- Patterns: [[experiment-before-scale]], [[crm-export-dedup]], [[company-enrichment-pipeline]], [[people-enrichment-pipeline]]
