---
title: Apify
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[limitless-research]]", "[[tam-sourcing-course]]"]
tags: [clay-feature, web-scraping, marketplace, platform-specific, enrichment, tam-sourcing]
---

# Apify

An open-source marketplace of specialized, community-built scrapers ("actors") natively integrated into Clay. Unlike [[claygent]] (general-purpose AI scraping) or [[zenrows]] (anti-bot bypass), Apify provides purpose-built scrapers for specific platforms and data sources.

## Key Concept: Actors

Apify's library contains **2,000+ pre-built actors** — ready-made scrapers optimized for specific platforms:
- **Reddit scraper** — Posts, comments, user data from subreddits or threads
- **Instagram Business scraper** — Profiles, follower counts, engagement rates
- **TikTok scraper** — Videos, profiles, trends
- **Facebook scraper** — Pages, groups, posts
- **Google scraper** — Search results, Maps data
- **Yelp scraper** — Business listings, reviews, ratings (key for SMB TAM sourcing)
- **Similarweb scraper** — Website traffic, session duration, bounce rates
- **Yellow Pages scraper** — Business listings
- **Job listing scrapers** — Indeed, LinkedIn Jobs, etc.
- **Apartments.com scraper** — Real estate listings

The marketplace is community-maintained — new actors are constantly being added. You rarely need to build scrapers from scratch.

## How It Works in Clay

1. **Create your Apify account** and browse the actor library
2. **Configure your actor**: Click "Create Task" to add it to your library. Switch input format from Manual to JSON mode and copy the body text — this becomes your input data structure in Clay
3. **Connect to Clay**: Actions → Run Apify Actor → select the task → paste JSON configuration under "Input Data"
4. Results import directly into Clay table columns
5. Use Clay's enrichment and transformation tools for further processing

## Cost Model

**Important:** Apify actors may have their own subscription costs separate from Clay credits.

| Component | Cost |
|-----------|------|
| Clay integration | Included in Clay plan |
| Actor subscription | Varies by actor ($0–$45+/month) |
| Usage/volume | Some actors charge per request or per result |

Example: The "Unlimited Reddit Web Scraper" costs $45/month after a 1-day free trial.

Always check the actor's pricing before committing to a workflow.

## Example: Reddit Scraping

1. Select "Unlimited Reddit Web Scraper" actor
2. Configure: target thread/subreddit URL, extraction depth
3. No login required for public Reddit data
4. Results arrive within minutes
5. Import posts, comments, and user data into Clay
6. Enrich and analyze with Clay's AI tools

## When to Use

| Scenario | Use Apify? |
|----------|-----------|
| Need data from a specific social platform | Yes — find the platform actor |
| Need bulk data from a niche directory | Yes — check for a specialized actor |
| General web research on company websites | No — use [[claygent]] |
| Protected site with anti-bot measures | No — use [[zenrows]] |
| Simple email/phone extraction from a page | No — use [[clay-native-scraper]] |

## Position in Hierarchy

From [[scraping-hierarchy]]:
```
Claygent → Zenrows → **Apify** → Native Scraper → Chrome Extension
```

Apify fills the "platform-specific" niche — when you need data from a source that has a dedicated scraper built for it.

## TAM Sourcing with Apify

Apify is a key tool for [[tam-sourcing-pipeline|TAM sourcing]] — especially for markets traditional B2B databases miss. Examples:

**Restaurant POS Example:** Scrape Yelp for restaurants in specific zip codes. Extract contact info, revenue estimates (from review volume and pricing), and review sentiment data revealing operational pain points. Result: ~90% market coverage vs ~20% from traditional B2B databases.

**GTM Alpha Workflow (Social → Web → Outreach):**
1. Instagram Business Scraper → find brands with 50K+ followers
2. Similarweb Scraper → check website traffic, session duration, bounce rates
3. Identify brands with huge followings but low website engagement = "marketing budget exists but needs conversion help"
4. Clay AI → compose personalized copy referencing specific metrics discovered

This creative data collection creates [[gtm-alpha]] — finding hidden opportunities competitors systematically miss.

## See Also

- [[scraping-hierarchy]] — where Apify fits in the toolkit
- [[claygent]] — general-purpose alternative
- [[zenrows]] — for anti-bot bypass (different use case)
- [[clay-native-scraper]] — simpler/cheaper alternative for basic extraction
- [[tam-sourcing-pipeline]] — Apify as a TAM sourcing input
- [[smb-tam-sourcing]] — Apify for SMB market coverage
- [[openmart]] — alternative for SMB discovery in supported regions
