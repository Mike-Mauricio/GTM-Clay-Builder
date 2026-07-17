---
title: "Formulas - Clay Docs"
source: "https://university.clay.com/docs/formula-generator"
author:
published:
created: 2026-07-14
description: "Generate formulas with AI to transform your data."
tags:
  - "clippings"
---
Overview

Clay formulas use JavaScript expressions to transform your data. The formula generator opens in a sidebar, allowing you to see your table while building formulas. When you reference a column like `{{Email}}`, Clay automatically passes the value from that column into your expression.

## Generate formula with AI

Clay's formula generator opens in a sidebar, allowing you to see your table and reference column data while building formulas.

To generate a formula with AI:

1. Enter your formula instructions. Type `/` to insert a column reference.
2. Click `Generate formula` to create your AI formula.

The sidebar highlights your formula column and any referenced columns, helping you validate your logic against real data. Click entries in referenced columns to jump to them in your table.

## How Clay formulas work

What's available in formulas:

- **Standard JavaScript:** All standard JavaScript objects and methods including `Math`, `String`, `Array`, `Date`, `RegExp`, `Number`, `Object`, and more.
- **Lodash:** Access the Lodash library using `_` for advanced data manipulation.
- **Moment.js:** Use Moment.js with `moment` for date and time operations.
- **Excel and Google Sheets functions:** Hundreds of familiar spreadsheet functions like `VLOOKUP`, `IF`, `SUM`, and `CONCATENATE` through the FormulaJS library.

## AI formula generator examples

Here are examples of formulas you can create with the formula generator:

- Extract the domain from `{{Email}}`.
- Use `{{LinkedIn URL}}` if available; otherwise use `{{LinkedIn Profile}}`.url.
- Extract the text after @ in `{{Twitter Handle}}`.
- Split `{{city}}` by comma, keep everything before the first comma, remove "Area" if present, then add quotes.
- Extract the first word from `{{Column_1}}`, combine with `{{Column_2}}`, then remove all non-letter characters.
- Calculate the number of days between `{{Created Date}}` and `{{Closed Date}}`.

## Conditional run formulas

Conditional run formulas control when enrichments execute, helping you save credits by running actions only when specific conditions are met.

**Where to find them:** In any enrichment panel, scroll to `Run Settings` and look for the `Only run if` option.

**Common use cases:**

- Only run email enrichment if title contains "VP".
- Only run headcount growth enrichment if company size is over 100 people.
- Only run AI column if a news article was found.

To create a conditional run formula:

1. In the enrichment panel, scroll to `Run Settings`.
2. Click `Use AI` next to `Only run if`.
3. Type your condition using `/` to reference columns (e.g., "Only run if headcount is greater than 40").
4. Click `Generate formula`.

You can also write conditional formulas manually using JavaScript expressions that evaluate to `true` or `false`.

## FAQs

### Can I create or change my formula without running it?

Yes. When editing a formula, you'll see the option to `Save and don't run enrichments`. Clicking this prevents your formula from running on enrichment columns that cost credits. These columns will appear greyed out to indicate they're out of date.