---
title: Conditional Runs
type: concept
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]", "[[crm-enrichment]]", "[[best-practices-getting-started]]"]
tags: [enrichment, gating, credit-efficiency, workflow-design]
---

# Conditional Runs

A Clay feature that gates enrichment execution behind boolean conditions. An enrichment only runs on a row if its condition evaluates to true — otherwise the row is skipped and no credits are consumed.

## Why It Matters

Without conditional runs, every enrichment runs on every row in the table. This wastes credits on:
- Records that don't meet basic qualification criteria
- Records already enriched from a previous run
- Records missing required input data (which would fail anyway)

Conditional runs are the primary mechanism for implementing the GTM engineering principle: **gate expensive enrichments behind qualification.**

## Common Patterns

### Gate Behind Qualification
Only enrich records that pass initial filters:
- "Only run if Industry = 'Financial Services'"
- "Only run if Headcount > 50"
- "Only run if Funding Stage is not empty"

### Gate Behind Missing Data
Only enrich records that need the data:
- "Only run if Work Email is empty"
- "Only run if Funding Stage is empty"

### Gate Behind Previous Enrichment
Chain enrichments by requiring a previous step to have succeeded:
- "Only run if Company Domain is not empty" (corner piece exists)
- "Only run if LinkedIn URL is not empty" (corner piece exists)

### Gate Before CRM Export
Only push records that meet export criteria:
- "Only run if no matching CRM Contact ID found" ([[crm-export-dedup]])
- "Only run if Email Validation = 'Safe to Send'"

### Gate CRM Updates (Prevent Overwrites)
Control when enriched data overwrites existing CRM fields:
- "Only update if CRM field is empty" — prevent overwriting existing data
- "Only update if new data is more recent" — recency validation
- "Only update if confidence score meets threshold" — quality gate
- "Only update if source priority is higher" — source hierarchy

These conditions are critical for the [[crm-enrichment-lifecycle]] to avoid overwriting manually-maintained fields (notes, custom scores, relationship data). See [[clay-hubspot-integration]] and [[clay-salesforce-integration]] for CRM-specific implementation.

## Boolean Gating Columns

For complex conditions, create dedicated boolean columns (using [[ai-formulas]]) that evaluate to true/false. Then reference these in conditional runs:

1. Create column `Is Qualified` → formula checks headcount, industry, funding
2. Create column `Needs Email` → formula checks if work email is empty
3. Set conditional run: "Only run if Is Qualified = true AND Needs Email = true"

This approach (boolean decomposition) makes logic testable, debuggable, and reusable across multiple enrichments.

## Conditional Runs vs Conditional Statements

Conditional runs and [[conditional-statements]] are different features that complement each other:

| | Conditional Runs | [[conditional-statements\|Conditional Statements]] |
|---|---|---|
| **What it controls** | Whether an enrichment runs at all | Logic within a formula column |
| **Scope** | Per-enrichment gating | Per-cell formula evaluation |
| **Effect** | Skips the row entirely → saves credits | Returns different values per row → routes/classifies |
| **Syntax** | "Only run if" formula in Run Settings | IF/THEN/ELSE inside formula columns |

Use conditional runs to **save credits** by skipping unqualified rows. Use conditional statements to **route and classify** within formulas that do run.

## Formula Syntax

Conditional run formulas support three operator types:
- **Comparison:** equals, greater than, not equal to, contains
- **Logical:** AND, OR, NOT (e.g., `NOT {{status}} == "Closed"`)
- **Dynamic variables:** use `/` to reference columns

**"Use AI" button:** In Run Settings, input plain language instructions and Clay generates the conditional formula automatically.

**Alternative method:** Filter existing rows in a view, then run enrichments — filtered views only enrich visible rows. This acts as an implicit conditional without writing a formula.

## See Also

- [[credit-optimization]] — conditional runs as a cost strategy
- [[waterfall-enrichment]] — conditional runs gate waterfall execution
- [[crm-export-dedup]] — conditional runs prevent duplicate CRM entries
- [[crm-enrichment-lifecycle]] — conditional runs for safe CRM writes
- [[ai-formulas]] — used to create boolean gating columns
- [[clay-hubspot-integration]] — conditional Create/Update patterns
- [[clay-salesforce-integration]] — conditional patterns + Upsert alternative
