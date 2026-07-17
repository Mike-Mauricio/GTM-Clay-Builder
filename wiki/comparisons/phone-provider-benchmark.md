---
title: Mobile Phone Provider Benchmark
type: comparison
created: 2026-07-14
updated: 2026-07-14
sources:
  - "[[best-practices-getting-started]]"
tags:
  - enrichment
  - data-quality
  - benchmarks
  - phone
---

# Mobile Phone Provider Benchmark

Clay's internal benchmark testing 10 mobile phone providers across three regions (NAMER, EMEA, APAC), validated in partnership with TitanX. The study evaluated 9,806 mobile numbers from 6,000+ B2B contacts to measure accuracy, coverage, and cost per quality number.

## Providers Tested

Forager, Nimbler, Wiza, Datagma, LeadMagic, RocketReach, People Data Labs, ContactOut, Findymail, Prospeo.

## Methodology

### Dataset

- **6,000+ B2B contacts** across three regions: North America (NAMER), Europe/Middle East/Africa (EMEA), and Asia Pacific (APAC)
- Enrichment produced **9,806 mobile numbers** (multiple providers can return different numbers for the same contact)
- Numbers were deduplicated to unique combinations of mobile number + full name before scoring

### Regional Scoring

Different verification methods by region, reflecting available infrastructure:

**NAMER & EMEA — TitanX Scoring**

TitanX applied their proprietary Titan Scoring algorithm: manual cold calling plus evaluation of 11 additional data signals over 4 days. Numbers received one of four scores:

| Score | Definition | Expected Connect Rate |
|-------|-----------|----------------------|
| **P1** | Verified + high propensity to answer | ~25%+ connection rate |
| **P2** | Verified + lower propensity to answer | ~4-10% connection rate |
| **P3** | Unverified + very low propensity | Under 1% connection rate |
| **Needs Attention** | Inactive, disconnected, or wrong person | 0% — remove from lists |

TitanX's process specifically catches the "Right Name, Wrong Person" problem — when data appears accurate but belongs to a different person with the same name (e.g., John Smith the professor vs. John Smith the CEO).

**Quality score formula (NAMER/EMEA):**
- P1 = full weight (1.0x)
- P2 = half weight (0.5x)
- P3 = quarter weight (0.25x)
- Needs Attention = negative impact

**APAC — Manual Cold Calling**

An offshore team called each number at least 5 times (or until deterministic outcome):

| Score | Definition |
|-------|-----------|
| **Good** | Contact answered and confirmed their name, OR voicemail mentioned contact's name |
| **Unverified** | Calls went unanswered, no name-confirming voicemail |
| **Bad** | Out of service, or wrong person answered — remove from lists |

**Quality score formula (APAC):**
- Good = full weight (1.0x)
- Unverified = quarter weight (0.25x)
- Bad = negative impact

### Cost Analysis

Cost per quality mobile number calculated using Clay credit pricing, plus a time-savings factor — sales reps stuck with unverified numbers waste hours on unproductive calls.

## Key Findings

| Metric | Result |
|--------|--------|
| Total contacts enriched | 6,000+ |
| Total mobile numbers returned | 9,806 |
| P1 or "Good" numbers | **23%** of total |
| Improvement from quality providers | Up to **5x more conversations per hour** |

### What the Numbers Mean

- **Only 23% of phone numbers are high-quality.** Roughly 3 out of 4 mobile numbers returned by providers are P2, P3, or worse. This is the headline finding — raw phone number coverage is misleading without quality scoring.
- **Provider quality varies dramatically.** The gap between the best and worst providers (by quality score) is wide enough to justify careful selection and waterfall ordering.
- **5x conversation multiplier.** TitanX found that using providers with more verified mobile numbers gives sales reps up to 5x more live conversations per hour. This is the ROI case for paying more per credit for higher-quality phone data.
- **Coverage varies by region.** Provider performance differs across NAMER, EMEA, and APAC. A provider that leads in North America may underperform in APAC.
- **Coverage also varies by industry.** While this study didn't test by industry, Clay notes that industry-specific coverage differences exist and should be tested for your ICP.

> **Note:** Provider-by-provider rankings, regional coverage breakdowns, and cost-per-quality-number figures were presented in visual charts in the original source. Consult the [Clay University data test](https://university.clay.com/docs/data-test-methodology-mobile-phone-region) for the full provider comparison tables.

## Implications for Waterfall Design

1. **Phone waterfall is even more important than email waterfall.** With only 23% of numbers being P1/Good quality, single-provider phone enrichment is a losing strategy. A multi-provider [[waterfall-enrichment]] maximizes your chance of getting a verified number.

2. **Region-aware waterfall ordering.** Provider performance varies by region. If your ICP spans multiple geographies, build separate phone waterfall sequences per region — or at minimum, adjust provider order based on regional strengths.

3. **Quality scoring before dialing.** Integrate TitanX or equivalent scoring into your [[people-enrichment-pipeline]] before passing numbers to SDRs. The difference between a P1 number (25% connect rate) and a P3 number (<1%) is the difference between productive outreach and wasted time.

4. **Gate phone enrichment aggressively.** Phone numbers cost credits and phone verification costs more. Use [[conditional-runs]] to only enrich phone numbers for contacts that have already passed email outreach without response, or for high-priority accounts where phone is the primary channel.

5. **Remove "Needs Attention" / "Bad" numbers immediately.** These have 0% connection rate and actively waste rep time. Build a cleanup step into your pipeline that flags and removes these before export to your dialer or CRM.

6. **Budget for the 23% reality.** If you need 200 quality phone numbers, expect to enrich 800-900 contacts across multiple providers. Plan credit spend accordingly and use the cost-per-quality-number metric (not cost-per-enrichment) for budgeting.

7. **Phone + email = multichannel coverage.** Phone enrichment complements email enrichment — contacts unreachable by email may pick up the phone, and vice versa. Design your [[people-enrichment-pipeline]] to pursue both channels in parallel, with routing logic based on which contact data you successfully verified.

## Related Pages

- [[waterfall-enrichment]] — The general pattern: cheapest-first, multi-provider chaining
- [[clay-email-waterfall]] — Email waterfall for comparison (same pattern, different data type)
- [[people-enrichment-pipeline]] — Full contact enrichment pipeline including phone finding
- [[company-enrichment-pipeline]] — Company-level enrichment (feeds into people-level enrichment)
- [[credit-optimization]] — Strategies for managing enrichment spend
- [[conditional-runs]] — Boolean gating to skip enrichments on unqualified rows
- [[lead-scoring]] — Quality scores from phone verification can feed into lead scoring models
