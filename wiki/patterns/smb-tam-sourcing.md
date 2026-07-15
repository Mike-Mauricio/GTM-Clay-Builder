---
title: SMB TAM Sourcing
type: pattern
created: 2026-07-14
updated: 2026-07-14
sources:
  - "[[tam-sourcing-course]]"
tags:
  - pattern
  - tam
  - smb
  - local-business
  - openmart
  - google-maps
  - review-analysis
---

# SMB TAM Sourcing

A specialized TAM sourcing workflow for small and medium-sized businesses that traditional B2B databases miss. While standard tools like ZoomInfo and Apollo cover enterprise and mid-market well, they provide roughly 20% coverage of local businesses — dentists, law firms, contractors, restaurants, retail shops. This pattern fills that gap.

## The Untapped Market

Everyone fights over the same enterprise prospects in the same databases. Meanwhile, millions of local businesses have real budgets, real pain points, and near-zero inbound marketing competition.

Traditional B2B databases were built for companies with LinkedIn pages, press releases, and Series A announcements. They structurally miss:
- Single-location service businesses
- Owner-operated shops and practices
- Franchise locations
- Businesses without a meaningful web presence
- Emerging businesses too new for database coverage

The opportunity is in the coverage gap. If your product serves local businesses, sourcing from the same databases as everyone else means you're competing for the 20% while ignoring the 80%.

## Strategic Advantages

**1. Untapped market access.** Less competition for attention means higher response rates and often faster sales cycles. Local business owners are not drowning in sales emails the way enterprise buyers are.

**2. Hyper-local personalization.** You can mention specific neighborhoods, local competitors, community presence, and regional context. This creates immediate credibility that generic enterprise outreach cannot match. A message referencing "your Downtown Portland location" lands differently than one referencing "your company."

## Primary Tools

### [[openmart]]
Purpose-built for SMB discovery. The strongest option for North American local business sourcing.

- **Unlimited results** — no cap on records returned
- **Semantic search** — describe what you're looking for in natural language
- **Multi-source aggregation** — pulls from Google Maps, Yelp, business directories, and more
- **Advanced filtering** — website presence, review count, employee size, ratings
- **Coverage:** USA, Puerto Rico, Canada, Australia, New Zealand

### [[clay-google-maps]]
Global coverage for location-based businesses.

- **Up to 1,000 results** per search
- **Google categories** for business type filtering
- **Global reach** — use for markets outside OpenMart's coverage areas
- **Rich metadata** — ratings, review count, hours, address, phone, website

### [[apify]]
Specialized scrapers for niche data sources.

- **Yelp scraper** — pulls review data, ratings, business details. For a restaurant POS product, Yelp scraping provided 90% market coverage vs. 20% from traditional B2B databases.
- **Niche directory scrapers** — industry-specific directories (HomeAdvisor, Healthgrades, Avvo, etc.)
- **Custom scrapers** — build or configure scrapers for any structured data source

## Workflow

### 1. Define Geographic Parameters

Target markets based on:
- **Product-market fit** — where does your solution solve the clearest pain?
- **Competitive landscape** — where is competition thinnest?
- **Ability to provide local support** — can you service these markets effectively?

Be specific with location targeting. "Downtown Chicago" produces very different results than "Chicago metro area." Start narrow, prove the playbook works, then expand geography.

### 2. Discover Businesses

Use [[openmart]] with semantic search and filters as the primary discovery channel:

```
Search: "coffee shops with espresso bar"
Filters:
  - Has a website that loads successfully
  - Minimum 50 Google reviews
  - Rating 4.0+
  - Location: Portland, OR (5-mile radius)
```

Supplement with [[clay-google-maps]] for markets outside OpenMart's coverage, and [[apify]] for niche directory data (Yelp reviews, industry-specific listings).

### 3. Enrich and Qualify

Four enrichment layers tailored for SMB:

**Segment and categorize using AI formulas.** Local businesses within the same industry vary wildly. AI classification separates them into actionable segments. Example: for coffee shops, classify as "specialty" or "new-wave" based on keywords in descriptions, menu items, and review language. Each segment has different needs and willingness to pay.

**Business maturity indicators.** Signals that a business is growing and ready to invest:
- Multiple locations (especially with recent additions)
- New service offerings or menu expansions
- Active hiring (job postings on their website or Indeed)
- Recent renovations or rebranding
- Increasing review volume over the last 6 months

**Customer sentiment analysis.** AI analyzes reviews to extract actionable intelligence. Use [[claygent]] with a prompt like:

```
Analyze the last 20 Google reviews for this business and identify:
1. Primary customer complaints (slow service, high prices, quality issues)
2. Competitive advantages mentioned by reviewers
3. Pain points suggesting need for operational solutions
4. Customer demographic patterns (families, professionals, tourists)

Return structured JSON with each category.
```

Review analysis is the SMB equivalent of enterprise intent data. A restaurant with complaints about "long wait times" and "order mistakes" is a better prospect for a POS system than one with perfect reviews.

**Website and digital presence assessment.** Rate digital maturity on a three-tier scale:

| Level | Indicators | Implication |
|-------|-----------|-------------|
| Basic | No website, or single-page placeholder | Needs foundational digital services |
| Intermediate | Functional website, basic online ordering or booking | Ready for optimization and automation |
| Advanced | Modern website, active social media, online reviews managed | Ready for sophisticated solutions |

Use OpenMart's filter for "Has a website that loads successfully" as a baseline qualifier. Businesses without websites need basic digital services; businesses with outdated sites are often ready for more sophisticated solutions.

**Growth signal detection.** Flag businesses showing expansion patterns:
- Multiple locations with recent additions
- Increasing review volume (20%+ growth quarter-over-quarter)
- New service offerings listed on website or Google Business Profile
- Job postings indicating scaling operations

### 4. Score and Route

Apply [[lead-scoring]] criteria adapted for SMB realities. Enterprise scoring models don't translate directly — SMB scoring emphasizes:

- **Review-based signals** over intent data (reviews are the SMB equivalent of G2 activity)
- **Location count** as a proxy for revenue and growth stage
- **Digital maturity** as an indicator of technology adoption readiness
- **Sentiment patterns** that reveal operational pain points your product solves
- **Recency of growth signals** — a business that just opened a second location is more ready to invest than one that's been stable for 5 years

### 5. Activate

SMB outreach demands hyper-local personalization. Generic templates fail. Every touch should reference:

- **Specific neighborhood or street** — "your Hawthorne District location"
- **Local competitors** — "we work with three other Portland coffee shops including..."
- **Community presence** — reference their involvement in local events, partnerships, or community boards
- **Specific review insights** — "your customers love the atmosphere but mention wait times during morning rush"
- **Relevant local context** — seasonal trends, local regulations, neighborhood developments

This level of specificity is only possible because the enrichment pipeline captures local context that enterprise databases never touch.

## Best Practices

- **Be specific with location.** "Downtown Chicago" and "Chicago metro area" produce very different prospect pools. Start narrow.
- **Test and iterate on filtering criteria.** Start broad to understand the landscape, then tighten filters as you learn which segments convert.
- **Focus on data sources providing genuine competitive advantage.** If your competitors can pull the same list from ZoomInfo, the list isn't a differentiator. Review data, local context, and AI classification create moats.
- **Respect the SMB buying process.** Decisions are faster but more personal. The owner is often the buyer, the user, and the decision-maker. Speak to their daily reality, not to abstract business outcomes.
- **[[experiment-before-scale]]** — Build the workflow in a Clay Table with 50-100 records first. Validate enrichment quality, scoring accuracy, and conversion rates before promoting to an Audience.

## Related

- [[tam-sourcing]] — Core TAM sourcing concept
- [[tam-sourcing-pipeline]] — Full pipeline architecture (this pattern is a specialized variant)
- [[openmart]] — Primary SMB discovery tool
- [[clay-google-maps]] — Global location-based sourcing
- [[apify]] — Niche directory and review scrapers
- [[claygent]] — AI research agent for custom enrichment
- [[lead-scoring]] — Scoring frameworks adapted for SMB signals
