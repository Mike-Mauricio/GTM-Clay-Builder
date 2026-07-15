---
title: Analyze Image
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]"]
tags: [clay-feature, enrichment, visual-data, multimodal, image-analysis]
---

# Analyze Image

Clay's multimodal enrichment for extracting data from images and web page screenshots. Enables visual data extraction — pulling structured information from what's visible on a page rather than from text/HTML.

## Two Enrichments

### Analyze Image
Processes an image URL and returns AI-extracted insights based on your prompt.

### Get Page Screenshot
Captures a full-page screenshot of a URL, producing an image that Analyze Image can then process.

Together they enable: URL → screenshot → image analysis → structured data.

## Primary Use Case: Logo Extraction Pipeline

Extract customer/partner logos from company homepages and convert them into a structured company list:

1. **Start with company domains** (from your prospect table)
2. **Analyze Image** with prompt: "Analyze and return a comma-separated list of the company names for every logo you see on the page, prioritized by getting all the logos on the page. Scroll to the bottom of the page and make sure you get all the logos. Return only the list."
3. **Input:** Company domain URL
4. **Convert to JSON** — AI enrichment: "Return this comma-separated list as a JSON list" using JSON schema output format
5. **Configure JSON schema** — Define the array structure
6. **Write to new table** — "Take action on list" creates a row per logo/company
7. **Create logo table** — New table with extracted company names
8. **Find domains** — [[claygent]] to extract domains from company names for further enrichment

## Other Use Cases

| Use Case | What It Detects |
|----------|----------------|
| Customer logo extraction | Who a company's customers/partners are |
| Hiring badge detection | LinkedIn screenshots showing "We're hiring" badges |
| Live chat widget detection | Whether a website has a chat widget (competitor signal) |
| Award/certification badges | Industry certifications visible on homepage |
| Technology stack indicators | Tool logos in integration pages |

## Why Visual Enrichment Matters

Some data only exists visually — it's not in the HTML, not in any database, not scrapable as text:
- Customer logos on homepages
- Screenshots from social media
- Visual indicators on profiles
- Design/layout patterns

Analyze Image opens up a data source category that [[claygent]], [[zenrows]], and [[clay-native-scraper]] can't access.

## See Also

- [[claygent]] — complementary text-based scraping
- [[jigsaw-framework]] — visual data is fill-layer intelligence
- [[gtm-alpha]] — visual signals competitors aren't collecting
- [[ai-formulas]] — for processing Analyze Image output downstream
