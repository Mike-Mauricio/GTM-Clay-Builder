---
title: Conditional Statements
type: concept
created: 2026-07-14
updated: 2026-07-14
sources: ["[[best-practices-getting-started]]"]
tags: [formulas, logic, conditional, if-then, workflow-design]
---

# Conditional Statements

In-formula logic for controlling data transformation and routing within Clay. Conditional statements evaluate conditions and return different outputs based on whether those conditions are true or false. Used in AI formulas, conditional snippets, and waterfall logic.

**Important distinction:** Conditional statements are in-formula logic (data transformation). [[Conditional-runs]] are enrichment gating (whether an enrichment runs at all). They serve different purposes and are configured in different places.

| Feature | Conditional Statements | [[Conditional Runs]] |
|---------|----------------------|---------------------|
| **What it controls** | Output value of a formula | Whether an enrichment executes |
| **Where it lives** | Inside a formula or AI prompt | In the enrichment's run settings |
| **Credit impact** | None (formulas are free) | Prevents credit spend on unqualified rows |
| **Use case** | "Return 'Enterprise' if headcount > 500" | "Only run email waterfall if domain exists" |

## Syntax

```
IF (condition)
  return result_if_true
ELSE IF (second_condition)
  return result_if_second_true
ELSE
  return default_result
```

### Logical Operators

- **AND** — both conditions must be true
- **OR** — either condition can be true
- **NOT** — inverts the condition
- **Comparison:** `==`, `!=`, `>`, `<`, `>=`, `<=`
- **String:** `contains`, `starts with`

## Where Conditional Statements Are Used

1. **AI Formulas** — transform data: scoring leads, qualifying opportunities, classifying records
2. **Conditional Runs** — gate enrichment execution (see [[conditional-runs]])
3. **Conditional Snippets** — embed conditional logic in outbound messages based on contact criteria
4. **Waterfalls** — maximize coverage with multiple providers based on data availability

## Common Patterns

### Lead Qualification

```
IF (company.size > 500)
  return "Enterprise"
ELSE IF (company.size > 50)
  return "Mid-Market"
ELSE
  return "SMB"
```

### Email Validation

```
IF (person.email contains @gmail.com OR @yahoo.com)
  return "Personal email"
ELSE
  return "Work email"
```

### Regional Routing

```
IF (region == "US")
  return "10% Discount"
ELSE IF (region == "EMEA")
  return "15% Discount"
ELSE
  return "No Discount Available"
```

## Best Practices

### Handle Nulls and Edge Cases

Empty fields, unexpected formats, and boundary values cause the most formula errors. Always test:
- **Empty fields:** Ensure blank `company_size` defaults correctly (e.g., "Not Qualified")
- **Boundary values:** Test `company_size = 50` in `>= 50` conditions to avoid misclassification
- **Unexpected formats:** Handle `company_size = "unknown"` with a default fallback

### Use Parentheses for Complex Conditions

Group conditions explicitly when combining AND/OR to avoid ambiguous evaluation:

- **Ambiguous:** `size > 100 AND location == "US" OR revenue > 1M`
- **Clear:** `(size > 100 AND location == "US") OR revenue > 1M`

### Test Before Scaling

Run formulas on 5-10 rows before applying to the full table. Check edge cases with missing data, unexpected formats, and boundary values.

## Relationship to Boolean Decomposition

For complex multi-condition logic, consider creating dedicated boolean columns instead of deeply nested IF statements:

1. `Is Enterprise` → `company.size > 500`
2. `Is US Based` → `location contains "US"`
3. `Is High Intent` → `intent_score > 75`
4. `Segment` → combines the booleans into a routing decision

Each boolean is independently testable and reusable across formulas. This is the same principle used in [[conditional-runs]] for enrichment gating.

## See Also

- [[conditional-runs]] — gating enrichments (not formulas) behind boolean conditions
- [[ai-formulas]] — where conditional statements are most commonly used
- [[lead-scoring]] — conditional logic for score calculation
- [[lead-routing]] — conditional routing based on qualification criteria
- [[dynamic-column-references]] — referencing column data inside conditional formulas
