---
title: AI Formulas
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]"]
tags: [clay-feature, ai, transformation, zero-credit, formulas]
---

# AI Formulas

Clay's credit-free AI-powered transformation tool for structured, deterministic data manipulation. Unlike [[claygent]] (which browses the web), AI Formulas operate on data already in your Clay table — extracting, calculating, formatting, and classifying without consuming credits.

## Key Properties

- **Zero credits** — No cost per execution
- **Deterministic** — Same input produces same output (rule-based, not generative)
- **Reusable** — Formulas can be copied across tables
- **Fast** — No external API calls, processes instantly

## Deterministic vs. Generative

AI Formulas are for **deterministic** transformations — structured, rule-based operations with predictable outputs:
- Extract domain from email address
- Calculate years of experience
- Format phone numbers
- Classify job titles into categories

They are NOT for **generative** tasks like writing personalized emails, summarizing articles, or creative content. Those require [[claygent]] or ChatGPT integration.

## Common Use Cases

### Data Extraction
- Extract all companies from work history into a comma-separated list
- Pull domain from email address
- Extract area code from phone number

### Calculations
- Calculate total years of work experience
- Get tenure in most recent role (years + months)
- Compute time since last funding round

### Formatting & Cleaning
- Standardize date formats
- Clean inconsistent job titles
- Normalize location strings
- Convert text to title case / lowercase

### Classification
- Categorize job titles into seniority buckets
- Tag companies by industry sub-segment
- Flag records meeting specific criteria

### Boolean Logic
- Create qualification flags (Is Qualified: true/false)
- Build gating columns for [[conditional-runs]]
- Compare domains for CRM dedup validation

## Best Practices

1. **Use the "/" command** to reference columns by name — avoids hardcoded references that break on rename
2. **Test on 5-10 rows first** — verify logic before running on full table
3. **Prefer AI Formulas over enrichments** for data already in the table — why pay credits for a transformation?
4. **Combine with [[conditional-runs]]** — use AI Formulas to create boolean gating columns

## See Also

- [[clay-normalization-tools]] — another zero-credit transformation tool
- [[claygent]] — for when you need data from outside Clay
- [[credit-optimization]] — AI Formulas as a cost-saving strategy
- [[conditional-runs]] — boolean columns from AI Formulas gate enrichments
