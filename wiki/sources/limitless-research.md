---
title: "Limitless Research"
type: source
created: 2026-07-13
updated: 2026-07-13
sources: ["https://university.clay.com"]
tags: [clay-academy, web-scraping, research, intermediate]
---

# Limitless Research

**Source:** Clay University (university.clay.com)
**Type:** Video course (7 lessons)
**Level:** Intermediate — web scraping and research toolkit
**Location:** `Knowledge/Clay/Lessons/Limitless-Research/`

## Overview

Clay's intermediate course focused on web scraping and research capabilities. Teaches the complete scraping toolkit hierarchy and when to use each tool. Builds on [[clay-101-gtm-automation|Clay 101]] foundations — assumes knowledge of [[fete-framework|FETE]], [[jigsaw-framework|Jigsaw]], and basic [[claygent]] usage.

Two lessons (Claygent overview, Prompt Engineering) are repeats from Clay 101. The 5 net-new lessons cover the scraping decision framework and four additional scraping tools.

## Lesson Index

| # | Lesson | Focus | Key Concepts |
|---|--------|-------|-------------|
| 01 | Intro to Web Scraping | Strategy | [[scraping-hierarchy]], when to scrape vs. enrich, data source evaluation |
| 02 | Claygent AI Web Scraper | Tool | [[claygent]] model selection (Neon/GPT-4/Claude), preset templates (repeat from 101) |
| 03 | Deep Dive: Clay Scrapers | Tool | [[clay-native-scraper]], structured extraction, body text for AI processing |
| 04 | Deep Dive: Zenrows | Tool | [[zenrows]], anti-bot bypass, protected site scraping (Crunchbase example) |
| 05 | Deep Dive: Apify Actors | Tool | [[apify]], scraper marketplace, platform-specific actors (Reddit example) |
| 06 | Deep Dive: Chrome Extension | Tool | [[clay-chrome-extension]], visual scraping, auto-detect, custom recipes |
| 07 | Prompt Engineering Crash Course | Technique | [[prompt-engineering-at-scale]], 4-principle framework, copywriting prompts (repeat from 101) |

## Key Takeaways

1. **The scraping hierarchy determines tool choice.** Claygent first → Zenrows for protected sites → Apify for platform-specific sources → Native Scraper for simple/cheap extraction → Chrome Extension for visual browser scraping.
2. **Scraping vs. enrichment is a strategic decision.** Use enrichment providers when they have the data (headcount, funding, emails). Scrape when the data lives on web pages no provider indexes.
3. **Zenrows unlocks protected sources.** Sites like Crunchbase with anti-bot measures need Zenrows' anti-bot bypass — Claygent alone can't access them.
4. **Apify is a marketplace, not a single tool.** Each actor is purpose-built for a specific platform (Reddit, Instagram, Yellow Pages, etc.) and may have its own subscription cost.
5. **The Chrome Extension is browser-side scraping.** Unlike server-side tools (Claygent, Zenrows, Apify), it runs in your browser and scrapes what you can see on screen.
6. **Claygent's Neon model enables multi-column output.** A single Claygent run can return structured data across multiple columns — reducing the need for follow-up AI processing.

## The Scraping Hierarchy

From [[scraping-hierarchy]]:

```
Claygent → Zenrows → Apify → Native Scraper → Chrome Extension
```

Each tool has a specific niche. The hierarchy is about matching the right tool to the data source, not about quality ranking.

## Cross-References

- Concepts: [[scraping-hierarchy]]
- Tools: [[claygent]] (updated), [[clay-native-scraper]], [[zenrows]], [[apify]], [[clay-chrome-extension]]
- Patterns: [[prompt-engineering-at-scale]]
- Related: [[jigsaw-framework]] (scraping collects fill data), [[gtm-alpha]] (scraping enables unique data)
