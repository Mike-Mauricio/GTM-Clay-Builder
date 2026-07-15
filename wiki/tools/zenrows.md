---
title: Zenrows
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[limitless-research]]"]
tags: [clay-feature, web-scraping, anti-bot, protected-sites, enrichment]
---

# Zenrows

Clay's integrated solution for scraping websites with strong anti-bot protections. When [[claygent]] or the [[clay-native-scraper|native scraper]] fail because a site blocks automated access, Zenrows bypasses CAPTCHAs, human verification, and bot detection to extract the data.

## When to Use

Escalate to Zenrows when:
- Claygent returns empty results or errors on a specific site
- The target site has CAPTCHAs, human verification, or "prove you're not a bot" challenges
- You need data from known protected sources (Crunchbase, G2, review sites, etc.)

## Key Features

| Feature | Purpose |
|---------|---------|
| Auto-parse | Formats scraped data for Clay consumption |
| JavaScript rendering | Handles dynamic/JS-heavy pages |
| Premium Proxy | Routes requests through premium IP addresses |
| Anti-bot bypass | Circumvents CAPTCHAs and bot detection |

## Setup in Clay

1. Add enrichment → search "Zenrows"
2. Input: URL column (the page to scrape)
3. Enable **auto-parse** (formats output for Clay)
4. Enable **JavaScript rendering with Premium Proxy** (handles dynamic pages)
5. Enable **anti-bot measures** (bypasses protection)
6. Run on test rows first

## Example: Crunchbase Scraping

Crunchbase is the canonical Zenrows use case — it has strong anti-scraping measures that block Claygent:

1. Build a Crunchbase URL column (e.g., `https://crunchbase.com/organization/{company-slug}`)
2. Run Zenrows with auto-parse + JS rendering + anti-bot enabled
3. Raw output contains: funding rounds, investor names, partners, company rankings
4. Use [[ai-formulas]] or Clay's column extraction to structure the raw output

**Key insight:** Zenrows can surface more current data than Claygent's general web search. In the course example, Magic's Series C was not found by Claygent but was found via Crunchbase + Zenrows.

## Cost

- **Remarkably low cost** per request (per the course)
- Can use Clay's built-in Zenrows credits or connect a personal Zenrows account for higher volume
- BYO account option for heavy scrapers

## Position in Hierarchy

From [[scraping-hierarchy]]:
```
Claygent → **Zenrows** → Apify → Native Scraper → Chrome Extension
```

Zenrows is the escalation tool — you reach for it when Claygent can't access the data due to site protections.

## See Also

- [[scraping-hierarchy]] — where Zenrows fits in the toolkit
- [[claygent]] — try this first before escalating to Zenrows
- [[apify]] — alternative for platform-specific scraping
- [[ai-formulas]] — for structuring raw Zenrows output
