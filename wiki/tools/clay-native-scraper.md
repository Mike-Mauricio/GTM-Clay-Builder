---
title: Clay Native Scraper
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[limitless-research]]"]
tags: [clay-feature, web-scraping, enrichment, simple-extraction]
---

# Clay Native Scraper

Clay's built-in, low-cost scraping tool for simple data extraction from static web pages. The cheapest scraping option in the [[scraping-hierarchy]] — positioned below [[claygent]] and [[zenrows]] but useful for straightforward extraction tasks.

## Two Primary Use Cases

### 1. Structured Data Extraction
Extract specific, predictable data types from web pages using built-in presets:
- **Emails** — All email addresses on a page
- **Phone numbers** — All phone numbers found
- **Links** — All URLs/hyperlinks
- **Lists** — Structured list items

Best for: company homepages, contact pages, directory listings — static pages with predictable structure.

### 2. Body Text for AI Processing
Extract the full body text of a page, then pipe it into downstream AI columns ([[ai-formulas]], [[claygent]], or ChatGPT integration) for:
- Copywriting based on website content
- Company categorization from website language
- Value proposition extraction
- Content analysis and summarization

This two-step pattern (scrape body text → AI analysis) is often cheaper than using Claygent directly, since the native scraper costs less per page.

## When to Use

| Scenario | Native Scraper? |
|----------|----------------|
| Simple static page, need emails/phones/links | Yes — cheapest option |
| Need raw body text for AI processing | Yes — scrape then analyze |
| Dynamic/JS-heavy page | No — use [[zenrows]] |
| Anti-bot protected site | No — use [[zenrows]] |
| Need AI reasoning about the content | No — use [[claygent]] |
| Scraping a specific platform (Reddit, etc.) | No — use [[apify]] |

## Position in Hierarchy

From [[scraping-hierarchy]]:
```
Claygent → Zenrows → Apify → **Native Scraper** → Chrome Extension
```

The native scraper is the simple/cheap default. Reach for it when the extraction is straightforward and the page is static.

## See Also

- [[scraping-hierarchy]] — where native scraper fits in the toolkit
- [[claygent]] — for when you need AI reasoning, not just extraction
- [[zenrows]] — for when native scraper can't access the page
- [[ai-formulas]] — downstream processing of scraped body text
