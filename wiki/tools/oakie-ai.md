---
title: Oakie AI
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]"]
tags: [clay-feature, enrichment, financial-filings, sec, public-companies]
---

# Oakie AI

Clay's native integration for enriching data from public company SEC filings (10-K, 10-Q). Extracts insights from financial documents that would otherwise require manual reading of 100+ page filings.

## How It Works

1. Start with a public company list (need stock ticker)
2. If no stock ticker: use [[claygent]] to find it from the company domain
3. Run Oakie AI enrichment with: stock ticker + date range + filing type
4. Oakie returns raw filing insights
5. Use AI summarization to extract specific signals (e.g., "3 key challenges this company faces")

## Setup Steps

1. **Get stock tickers** — Claygent with [[metaprompter]]: "Help me find the stock ticker for this company from this domain"
2. **Configure Oakie AI** — Input: stock ticker, date range, filing type (10-K annual, 10-Q quarterly)
3. **Run enrichment** — Returns filing content/insights
4. **AI summarization** — Follow-up AI column: "Extract three key insights about challenges this company is facing"
5. **Map to columns** — Separate insights into individual columns for scoring/routing

## Oakie AI vs. Claygent for Financial Data

| Dimension | Oakie AI | Claygent |
|-----------|---------|----------|
| Accuracy | Higher — purpose-built for SEC filings | Variable — depends on finding the right page |
| Simplicity | Plug in ticker, get insights | Must find the 10-K URL, write extraction prompt |
| Depth | Structured filing data | More flexible — can look beyond just filings |
| Best for | Few high-confidence insights from filings | Custom analysis, cross-referencing multiple sources |

**Decision rule:** Use Oakie AI when you want reliable filing data with minimal configuration. Use Claygent when you need deeper customization or want to combine filing data with other sources.

## Use Cases

- Identify key business challenges for outbound messaging
- Track revenue trends for expansion signals
- Detect strategic priorities for value proposition alignment
- Monitor risk factors for account health assessment
- Compare competitors' financial positions

## Limitations

- **Public companies only** — Requires SEC filings (not available for private companies)
- **Needs stock ticker** — Extra step to discover ticker from company name/domain
- **Structured filings only** — Doesn't cover press releases, earnings calls, or investor presentations

## See Also

- [[claygent]] — alternative for deeper financial research
- [[perplexity-enrichment]] — for broader market/competitive research
- [[metaprompter]] — for building the stock ticker discovery prompt
- [[jigsaw-framework]] — financial data is fill-layer intelligence
