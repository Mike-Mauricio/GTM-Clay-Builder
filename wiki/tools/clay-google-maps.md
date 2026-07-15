---
title: Clay Google Maps Integration
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]", "[[tam-sourcing-course]]"]
tags: [clay-feature, find, smb-prospecting, local-business, google-maps, tam-sourcing]
---

# Clay Google Maps Integration

Clay's integration with Google Maps for discovering local and SMB businesses that traditional B2B databases miss. Ideal for prospecting dentists, lawyers, contractors, restaurants, and other businesses with weak digital footprints.

## When to Use

- **SMB prospecting** — Target businesses that don't show up in Clay's native B2B dataset
- **Local targeting** — Find businesses in specific geographic areas
- **Service businesses** — Dentists, lawyers, contractors, plumbers, restaurants
- **Untapped markets** — Businesses competitors can't find through standard B2B databases

## How It Works

1. Create a new table → Select Google Maps as source
2. Define search area (city, neighborhood, or address + radius)
3. Choose search method:
   - **Business type** (recommended) — Uses Google's business category taxonomy
   - **Free text** — Keyword search (less precise)
4. Submit and wait for results (may take time to fully populate)
5. Returns up to **1,000 results** per query

## Search Tips

- **Be precise with location** — Narrow areas produce better results than broad regions
- **Use business types over free text** — More accurate categorization
- **Allow time for full population** — Results may trickle in over minutes
- **Plan secondary enrichments** — Google Maps gives you the business; you still need contacts, emails, etc.

## Data Returned

Google Maps results include:
- Business name and address
- Phone number
- Website URL
- Star rating and review count
- Business category
- Operating hours

## Secondary Enrichment Pattern

Google Maps gives you the Find phase. You still need the Enrich phase:
1. Google Maps → business list with websites and phones
2. [[claygent]] → scrape websites for additional business details
3. [[clay-find-people]] or Claygent → find decision-maker contacts
4. [[clay-email-waterfall]] → find email addresses
5. Export → CRM or email sequencer

## Google Maps vs OpenMart

For SMB/local business discovery, Clay offers two tools:

| Feature | Google Maps | [[openmart\|OpenMart]] |
|---------|-------------|---------|
| **Result limit** | 1,000 per query | Unlimited |
| **Search type** | Google categories / free text | Semantic business discovery |
| **Data sources** | Google only | Google Maps + Yelp + other directories |
| **Location search** | Radius from address | Text-based, multi-location |
| **Filtering** | Basic (category, area) | Advanced (website presence, review count, employee size) |
| **Coverage** | Global | USA, Puerto Rico, Canada, Australia, New Zealand |

**Rule of thumb:** Use [[openmart]] for large-scale SMB campaigns in supported regions. Use Google Maps for international markets or quick market scans. See [[smb-tam-sourcing]] for the complete workflow.

## See Also

- [[clay-find-companies]] — alternative for B2B companies in standard databases
- [[openmart]] — purpose-built SMB discovery (more features, limited geography)
- [[claygent]] — for enriching Google Maps results with custom data
- [[fete-framework]] — Google Maps is a Find phase tool
- [[jigsaw-framework]] — Google Maps provides corner pieces for local businesses
- [[tam-sourcing-pipeline]] — Google Maps as a TAM sourcing input
- [[smb-tam-sourcing]] — the complete SMB workflow
