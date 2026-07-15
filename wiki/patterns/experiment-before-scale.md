---
title: Experiment Before Scale
type: pattern
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]", "[[audiences-course]]", "[[functions-course]]"]
tags: [pattern, testing, credit-efficiency, workflow-design, best-practice, audiences, functions]
---

# Experiment Before Scale

The cardinal rule of Clay workflow development: always test enrichments on a small batch before running them on the full dataset. This protects against wasted credits, unexpected results, and data quality issues.

## The Pattern

```
5-10 rows → Review → 50 rows → Review → Full dataset
```

### Step 1: Micro-Test (5-10 rows)
- Run the enrichment on a tiny batch using "Save & Run (10 Rows)"
- Check: Does it return data? Is the data format correct? Are there obvious errors?
- This costs almost nothing and catches fundamental issues (wrong input column, bad prompt, misconfigured waterfall)

### Step 2: Moderate Test (50 rows)
- Scale to 50 rows to check consistency
- Check: Hit rate across rows, edge cases (null values, unusual formats), credit cost per record
- This is where you spot patterns — some industries have worse data coverage, some job titles don't match

### Step 3: Full Scale
- Run on the complete dataset with confidence
- Monitor progress for unexpected failures
- Use [[conditional-runs]] to skip rows that don't meet criteria

## Why It Matters

| Without Testing | With Testing |
|----------------|-------------|
| Burn entire credit budget on bad enrichment | Spend <1% of budget validating |
| Discover data quality issues after the fact | Catch issues before committing |
| No opportunity to refine prompts or filters | Iterate on small batches cheaply |
| Can't estimate credit cost for full run | Accurate cost projection from sample |

## The R&D Budget

[[clay-101-gtm-automation|Clay 101]] recommends allocating **10-15% of monthly credits** as a dedicated experimentation budget. Frame this as "buying insights" — even failed tests teach you what data is and isn't available for your ICP.

## What to Check in Review

1. **Hit rate** — What percentage of rows returned data?
2. **Data quality** — Is the returned data accurate and useful?
3. **Format consistency** — Are outputs in a predictable format?
4. **Edge cases** — How does it handle null inputs, unusual values?
5. **Credit cost** — What's the per-record cost? Multiply by total dataset size.
6. **Provider performance** — In waterfalls, which providers are contributing?

## Applies To

- [[waterfall-enrichment|Waterfall enrichments]]
- [[claygent]] prompts
- [[ai-formulas|AI Formula]] logic
- [[clay-email-waterfall|Email waterfalls]]
- CRM exports ([[crm-export-dedup]])
- Any new enrichment or transformation

## Tables as Labs, Audiences as Production

The [[clay-audiences]] distinction reinforces this pattern at a higher level:

- **Tables are laboratories** — iterate, form hypotheses, test Claygent prompts, build multi-step conditional flows. You rarely want to experiment at 50,000+ row scale.
- **Audiences are production** — stable, reliable, proven enrichments run at millions-record scale.

The workflow: **experiment in a Table → validate → graduate to an Audience.** Once you've figured out your data structure, moving to scale should make things simpler, not more complex.

## Functions: Test Then Save

[[clay-functions]] follow the same principle:

1. **Build the workflow in a table** and verify it works
2. Test on small batches, iterate on prompts and logic
3. **Save as a function** only when confident
4. Function auto-propagates to every table that calls it

Never save an untested workflow as a function — it will break at scale across multiple tables.

## See Also

- [[credit-optimization]] — test-then-scale as a cost strategy
- [[claygent]] — especially important for prompt iteration
- [[gtm-alpha]] — experimentation is how you discover alpha
- [[clay-audiences]] — Tables as labs, Audiences as production
- [[clay-functions]] — test before saving as reusable function
