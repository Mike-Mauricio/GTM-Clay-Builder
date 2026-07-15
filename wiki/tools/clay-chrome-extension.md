---
title: Clay Chrome Extension
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[limitless-research]]"]
tags: [clay-feature, web-scraping, browser-extension, visual-scraping]
---

# Clay Chrome Extension

A browser extension for visually scraping structured data from web pages directly into Clay tables. Unlike Clay's server-side scraping tools ([[claygent]], [[zenrows]], [[apify]], [[clay-native-scraper]]), the Chrome Extension runs in your browser — you see the page and point-and-click to select the data you want.

## Key Features

### Auto-Detect
The extension automatically identifies lists and tables on web pages. When it works, you can scrape an entire list with one click.

**Example:** Navigating to an experts directory and auto-detecting 78 entries without manual configuration.

### Custom Recipes
When auto-detect fails (non-standard page layouts), create a reusable custom recipe:

1. Navigate to "Select Data" in the extension
2. Create a new recipe with a descriptive name
3. Set a URL pattern (e.g., `clay.com/expert*`) for reuse across similar pages
4. Click on **two items** in the list to trigger the list selector
5. Choose which attributes to extract (name, location, cost, description, etc.)
6. Preview data in tabular format
7. Save recipe for future use
8. Add data to Clay workspace

### URL Pattern Matching
Custom recipes can be saved with URL patterns, making them reusable across pages with similar structure. If you scrape one page of a paginated directory, the same recipe works on all pages.

## Best Use Cases

| Use Case | Why Chrome Extension |
|----------|---------------------|
| Conference attendee lists | Structured list visible on page |
| Competitor customer/case study pages | List of logos, names, testimonials |
| Expert/partner directories | Tabular data with consistent structure |
| Paginated lists/directories | Recipe reuse across pages |
| Any visible list you want in Clay | Point-and-click simplicity |

## Limitations

- **Browser-side only** — Must manually navigate to each page
- **One page at a time** — Not for bulk scraping across hundreds of URLs
- **Requires visible data** — Cannot access data behind logins or in APIs
- **Best for structured/tabular data** — Unstructured pages need more configuration

## When to Use vs. Other Tools

| Scenario | Chrome Extension? |
|----------|------------------|
| I can see a list on a web page I want to grab | Yes |
| I need to scrape 500 URLs automatically | No — use [[claygent]] or [[apify]] |
| The site blocks automated scraping | No — use [[zenrows]] |
| I need AI to interpret the page content | No — use [[claygent]] |
| I need bulk platform-specific data | No — use [[apify]] |

## Position in Hierarchy

From [[scraping-hierarchy]]:
```
Claygent → Zenrows → Apify → Native Scraper → **Chrome Extension**
```

The Chrome Extension is the most manual tool in the hierarchy — but it's free, requires no configuration, and works immediately on any visible structured data.

## See Also

- [[scraping-hierarchy]] — where Chrome Extension fits in the toolkit
- [[claygent]] — for server-side AI-powered scraping
- [[clay-native-scraper]] — server-side alternative for simple extraction
