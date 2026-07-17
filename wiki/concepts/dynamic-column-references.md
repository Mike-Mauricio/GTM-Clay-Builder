---
title: Dynamic Column References
type: concept
created: 2026-07-14
updated: 2026-07-14
sources: ["[[best-practices-getting-started]]"]
tags: [formulas, columns, references, prompts, dynamic-data, syntax]
---

# Dynamic Column References

The mechanism for pulling data from one column into another column's formula, AI prompt, or message draft. In Clay, you reference columns dynamically using the slash command (`/`) which opens a menu of available columns and their nested fields.

## The Slash Command

Type `/` in any formula editor, prompt editor, or message draft to open the column reference menu. Select the column and field you want to insert. Clay generates a dynamic variable reference that pulls the live value from each row when the formula or enrichment runs.

This is the standard way to reference data — avoid hardcoding column names or copying values manually.

## Where Dynamic References Work

### Formula Generator
Reference fields like names, domains, locations, or scores to build formulas that operate on row-level data.

### Prompt Editor (AI Enrichments)
Insert dynamic fields into AI prompts to customize research or content generation per row. Example: add the `Company Website` field so the AI researches each company's specific site.

The Prompt Editor includes a **Required to Run** toggle on referenced fields. When enabled, the enrichment skips rows where that field is empty — avoiding errors from incomplete data. This serves a similar purpose to [[conditional-runs]] but is configured per-field within the prompt.

### Message Drafting
Personalize outreach with fields like First Name, Location, Company, or Current Experience. Dynamic references are what make AI-generated messages personal rather than generic.

## Data Reference Levels

When referencing enrichment columns that return structured data, you can drill into multiple levels:

| Level | What You Get | Example |
|-------|-------------|---------|
| **Entire enrichment** | All data returned by the enrichment | All fields from a Website Summary |
| **Entire list** | All items in a list field | All employees returned by a people search |
| **Individual list item** | One specific item by index | First employee (Index 0) from the list |
| **Specific endpoint** | One field from one item | The URL of the first experience entry |

### Accessing List Items

Lists use zero-based indexing:
- Index 0 = first item
- Index 1 = second item
- etc.

To reference a specific field from a list item: select the list > expand the item by index > select the field (e.g., `experience[0].url`).

## Common Mistakes

### Forgetting to Quote Strings
When referencing columns in JSON bodies or formula contexts, string values need quotes. Numeric values do not. Missing quotes on strings causes parse errors.

### Referencing Empty Columns
If a referenced column hasn't been enriched yet, the dynamic reference returns null. This can break formulas or produce empty AI outputs. Use the **Required to Run** toggle or [[conditional-runs]] to gate execution.

### Referencing Renamed Columns
If you rename a column after referencing it in a formula, the reference may break. Re-open the formula and re-select the column using `/` to update the reference.

### Assuming Flat Data
Many enrichments return nested objects or arrays. Using "Insert all properties" dumps the entire structure. For specific fields, drill into the nested structure using the menu.

## See Also

- [[ai-formulas]] — formulas where dynamic references are most commonly used
- [[conditional-statements]] — in-formula logic that operates on referenced data
- [[conditional-runs]] — gating enrichments when referenced fields are empty
- [[claygent]] — AI prompts that heavily rely on dynamic column references
- [[prompt-engineering-at-scale]] — designing prompts that use dynamic data effectively
