---
title: Scraping Hierarchy
type: concept
created: 2026-07-13
updated: 2026-07-13
sources: ["[[limitless-research]]"]
tags: [framework, web-scraping, tool-selection, data-sourcing]
---

# Scraping Hierarchy

A decision framework for choosing the right web scraping tool in Clay. Each tool has a specific niche — the hierarchy is about matching the right tool to the data source and use case, not about quality ranking.

## The Hierarchy

```
Claygent → Zenrows → Apify → Native Scraper → Chrome Extension
```

### 1. [[claygent|Claygent]] — AI-Powered Web Research
**Best for:** General web research, custom data extraction, AI-powered analysis
**Strengths:** Combines web browsing with AI reasoning, handles unstructured pages, multi-column output with Neon model
**Limitations:** Cannot bypass anti-bot protections, cannot access login-gated or paywalled content
**Cost:** 1-3 credits per query (model-dependent)
**Reach for this first** when you need custom data from public web pages.

### 2. [[zenrows|Zenrows]] — Anti-Bot Bypass Scraping
**Best for:** Protected sites with CAPTCHAs, human verification, or anti-scraping measures
**Strengths:** Bypasses bot detection, JS rendering, premium proxies, auto-parse for Clay-ready output
**Limitations:** More expensive than basic scraping, requires configuration
**Cost:** Low per-request (Clay built-in credits or BYO account)
**Escalate to this** when Claygent fails on a protected site (Crunchbase, G2, etc.).

### 3. [[apify|Apify]] — Platform-Specific Scrapers
**Best for:** Bulk scraping from specific platforms (Reddit, Instagram, TikTok, Yellow Pages, job boards)
**Strengths:** Purpose-built actors for each platform, handles platform-specific quirks, community-maintained
**Limitations:** Separate subscription costs per actor, not general-purpose
**Cost:** Varies by actor ($0-$45+/month per actor)
**Use this** when you need data from a specific platform that has a dedicated Apify actor.

### 4. [[clay-native-scraper|Clay Native Scraper]] — Simple Extraction
**Best for:** Static pages, structured data extraction (emails, phones, links), body text for AI processing
**Strengths:** Cheapest option, built-in extraction presets, simple configuration
**Limitations:** Cannot handle dynamic/JS-heavy pages, no anti-bot bypass, no AI reasoning
**Cost:** Minimal credits
**Use this** for simple, cheap extraction from static pages — or to grab raw body text for downstream AI processing.

### 5. [[clay-chrome-extension|Clay Chrome Extension]] — Visual Browser Scraping
**Best for:** Lists, directories, conference attendee pages, structured tabular data visible in the browser
**Strengths:** Point-and-click visual selection, auto-detect lists, reusable custom recipes with URL patterns
**Limitations:** Runs in browser (not server-side), requires manual browsing, one page at a time
**Cost:** Free (browser extension)
**Use this** when you can see the data you want on a web page and want to grab it directly.

## Decision Framework

**Before scraping, ask:** Does a Clay enrichment provider already have this data?

If the answer is yes (headcount, funding, emails, tech stack, firmographics) → use [[waterfall-enrichment|waterfall enrichments]]. Cheaper, faster, more reliable.

If the answer is no (custom data, niche signals, platform-specific content) → choose a scraping tool:

| I need to... | Use |
|-------------|-----|
| Answer a custom question about a company's website | [[claygent]] |
| Scrape a site that blocks bots (Crunchbase, G2) | [[zenrows]] |
| Pull data from Reddit, Instagram, TikTok, etc. | [[apify]] |
| Grab emails/phones/links from a simple page | [[clay-native-scraper]] |
| Visually select data from a page I'm browsing | [[clay-chrome-extension]] |

## Relationship to Jigsaw

Scraping tools primarily collect [[jigsaw-framework|fill data]] — the specialized, custom signals that create [[gtm-alpha]]. Standard enrichment providers handle corner pieces and edges. Scraping fills the gaps where no provider has the data.

## See Also

- [[claygent]] — the primary scraping tool (start here)
- [[zenrows]] — for anti-bot bypass
- [[apify]] — for platform-specific scraping
- [[clay-native-scraper]] — for simple/cheap extraction
- [[clay-chrome-extension]] — for visual browser scraping
- [[waterfall-enrichment]] — the alternative when providers have the data
- [[jigsaw-framework]] — scraping collects fill-layer data
