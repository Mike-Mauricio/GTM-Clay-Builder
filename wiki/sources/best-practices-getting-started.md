---
title: "Best Practices: Getting Started"
type: source
created: 2026-07-14
updated: 2026-07-14
sources: []
tags: [clay-docs, best-practices, reference, getting-started]
---

# Best Practices: Getting Started

Clay University documentation batch — 36 reference articles covering Clay platform best practices, feature documentation, and data benchmarks. Unlike the Clay Academy courses (which are structured learning paths), these are standalone reference docs for specific features and workflows.

## Source Details

- **Origin:** Clay University (university.clay.com) — "Best Practices - Getting Started" section
- **Format:** 36 Markdown articles clipped via Obsidian Web Clipper
- **Ingested:** 2026-07-14
- **Disposition:** All files moved verbatim to `Knowledge/Clay/Best-Practices/` as reference material. Net-new content synthesized into wiki pages; overlapping content merged into existing pages.

## Content Coverage

### Net-New Topics (16 new wiki pages created)

| Topic | Wiki Page | Category |
|-------|-----------|----------|
| Clay Ads platform | [[clay-ads]] | tool |
| Clay AI architecture & privacy | [[clay-ai-architecture]] | concept |
| Clay API & CLI | [[clay-api-cli]] | tool |
| Clay HTTP API | [[clay-http-api]] | tool |
| Clay Sources | [[clay-sources]] | tool |
| Clay Table Management | [[clay-table-management]] | tool |
| Clay Table Alerts | [[clay-table-alerts]] | tool |
| Conditional Statements | [[conditional-statements]] | concept |
| Dynamic Column References | [[dynamic-column-references]] | concept |
| Email Verification | [[email-verification]] | concept |
| Find AI (UseFind.ai) | [[find-ai]] | tool |
| Phone Provider Benchmark | [[phone-provider-benchmark]] | comparison |
| Personal Email Provider Benchmark | [[personal-email-provider-benchmark]] | comparison |
| Scheduled Operations | [[scheduled-operations]] | concept |
| Work Email Provider Benchmark | [[work-email-provider-benchmark]] | comparison |
| Zeliq | [[zeliq]] | tool |

### Existing Pages Updated

| Wiki Page | New Content Added |
|-----------|-------------------|
| [[credit-optimization]] | Action vs Data credit distinction, detailed per-provider credit costs |
| [[clay-audiences]] | Specific row limits (1M people, 500K companies), FAQs, troubleshooting |
| [[clay-functions]] | Detailed FAQs, debugging workflow, Functions vs Column Templates |
| [[clay-signals]] | Five signal types list, custom signals, plan gating details |
| [[clay-mcp]] | Troubleshooting steps, admin controls, identity sync |
| [[clay-email-waterfall]] | Email verification status definitions |
| [[conditional-runs]] | Distinction from conditional statements |
| [[lead-routing]] | Round-robin integration details |

### Low-Value / Minimal Content (not given standalone pages)

- Delete content within workspace — basic UI operations
- Templates and Claybooks — brief intro, linked to clay.com resources
- Write to Other Table — deprecated as of December 2025
- Enrichment recipes — Enterprise-only, small feature

## Article Index

| # | Article | Primary Topic |
|---|---------|---------------|
| 1 | Actions & Data Credits | Pricing/credits |
| 2 | AI in Clay | AI features/privacy |
| 3 | Audiences - Clay Docs | Audiences |
| 4 | Audiences FAQs and best practices | Audiences |
| 5 | Clay Ads - Clay Docs | Ads |
| 6 | Clay Ads compliance best practices | Ads/compliance |
| 7 | Clay API & CLI | API/developer |
| 8 | Conditional runs - Clay Docs | Data management |
| 9 | Conditional statements - Clay Docs | Formulas |
| 10 | Data test Mobile phone providers by region | Benchmarks |
| 11 | Data test Personal email providers | Benchmarks |
| 12 | Data test Work email providers | Benchmarks |
| 13 | Delete content within your workspace | Workspace admin |
| 14 | Does Clay have an API? | API/developer |
| 15 | Email verification statuses | Email/data quality |
| 16 | Enrichment recipes - Clay Docs | Enterprise features |
| 17 | Find AI integration | AI/sourcing |
| 18 | Functions - Clay Docs | Functions |
| 19 | Guide Ways to save Clay credits | Credits/best practices |
| 20 | How AI is priced | AI pricing |
| 21 | HTTP API - Clay Docs | API/developer |
| 22 | HTTP API with JWT authentication | API/developer |
| 23 | MCP troubleshooting and FAQs | MCP |
| 24 | Message drafting overview | Content/messaging |
| 25 | Referencing dynamic data from other columns | Formulas |
| 26 | Round-robin integration overview | Integrations/routing |
| 27 | Saved searches - Clay Docs | Sources |
| 28 | Scheduled columns - Clay Docs | Automation |
| 29 | Scheduled sources - Clay Docs | Automation |
| 30 | Signals in Clay | Signals |
| 31 | Sources - Clay Docs | Sources |
| 32 | Table alerts - Clay Docs | Table management |
| 33 | Table management settings | Table management |
| 34 | Table versions - Clay Docs | Table management |
| 35 | Templates and Claybooks | Getting started |
| 36 | Zeliq integration - Clay Docs | Integrations |

## Key Takeaways

1. **Data benchmarks are invaluable for waterfall design.** The three data test articles provide real benchmark data (9,806 phone numbers, 2,354 personal emails, 4,794 work emails tested) that should drive provider selection in [[waterfall-enrichment]] workflows.
2. **Table management is deeper than expected.** Auto-dedupe, auto-run hierarchy, passthrough tables, table alerts, and table versions form a production monitoring layer not covered in the Academy courses.
3. **Clay Ads opens a new activation channel.** Beyond sequencers and CRM exports, Clay can now sync audiences directly to Meta, Google, and LinkedIn ad platforms — with compliance best practices.
4. **The API story is three approaches, not one.** Webhooks (data in), third-party wrappers (Make/Zapier), and Enterprise REST API (direct enrichment lookups) serve different use cases.
5. **Action Credits vs Data Credits is a critical distinction.** Data Credits fund enrichments; Action Credits fund CRM pushes, webhooks, and email sends. Different pools, different budgeting.
