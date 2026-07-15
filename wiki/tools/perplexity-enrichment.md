---
title: Perplexity Enrichment
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]"]
tags: [clay-feature, enrichment, ai, web-research, perplexity]
---

# Perplexity Enrichment

Clay's native integration with Perplexity AI for fast, source-cited web research. Complements [[claygent]] — while Claygent browses specific URLs and reasons about content, Perplexity searches the broader web and returns summaries with source citations.

## Perplexity vs. Claygent

| Dimension | Perplexity | Claygent |
|-----------|-----------|----------|
| Approach | Web search → summarized answer | Visit specific URL → extract/analyze |
| Citations | Yes — returns sources | No — returns answer only |
| Best for | Trends, competitive intel, market context | Custom data extraction from known pages |
| Speed | Fast summaries | Depends on page complexity |
| Input | Natural language question | URL + extraction prompt |

## Use Cases

| Query Type | Example |
|-----------|---------|
| Market trends | "Restaurant trends in Austin 2024" |
| Competitive positioning | "How does Gusto compare to Rippling for HR software in 2024?" |
| Event intelligence | "Top food & beverage trade shows in Chicago Q2 2024" |
| Industry research | "What are the biggest challenges in commercial real estate lending?" |

## When to Use

Use Perplexity when you need:
- Broad web research (not extraction from a specific page)
- Source citations included in the answer
- Market/competitive/trend intelligence
- Fast summaries of complex topics

Use [[claygent]] instead when you need:
- Data from a specific URL
- Custom extraction logic
- Yes/no answers about specific pages
- Multi-column structured output

## See Also

- [[claygent]] — complementary tool for URL-specific extraction
- [[oakie-ai]] — for financial filing-specific research
- [[jigsaw-framework]] — Perplexity provides fill-layer intelligence
- [[gtm-alpha]] — Perplexity enables unique research at scale
