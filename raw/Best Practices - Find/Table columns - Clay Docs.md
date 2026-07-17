---
title: "Table columns - Clay Docs"
source: "https://university.clay.com/docs/table-columns-overview"
author:
published:
created: 2026-07-14
description: "Learn how to navigate columns in your Clay table."
tags:
  - "clippings"
---
Overview

## Column data types

There are a data types you can specify for your column. Here’s a high level overview of each one:

- **Text:** Accepts text inputs. You can use this for text fields, summaries, or descriptions
- **URL:** Takes in links and will open the link if you click on the cell.
- **Checkbox:** A true/false field that displays a checkbox. Ideal for conditional runs.
- **Select:** Select from a list of predefined tags. This is useful for categorizing your contacts and companies.
	- You can also split into views: create a view for each Select option with one click to slice your table by things like Account Tier or Segment.
- **Multi-select:** Select multiple options from a list of predefined tags. Similar to Select, but allows choosing more than one tag per cell.
- **Number:** Allows numerical values to be entered, ideal for ISO time measurements, lead scores, or revenue measurements.
- **Date:** Accepts a date and time range.
- **Currency:** Express your values in currency amounts.
- **Assigned To:** Tag anyone in your Clay workspace.
- **Email:** Accepts any email address input.
- **Image from URL:** Upload image URLs for easy retrieval.

## Add columns

You can add a new column to your table in a few ways:

- Scroll to the right of your table and select `Add column`.
- Open the dropdown menu for an existing column and choose `Insert right` or `Insert left` to access the column creation dropdown.
- In the column creation dropdown, you can either:
	- Specify the **data type** for your new column (e.g., Text, Number, Date).
		- Perform advanced actions, such as:
		- **Use AI** for AI data processing or research
				- Select **Message drafting**, **Enrichment waterfall**, or **Formula** for specific calculations or actions.
				- **Merge columns** to combine data from multiple columns.

### Switching column data type

You can switch the data type of your column within your table. To do this:

1. Click on the column title.
2. Hover over the current data type to see the dropdown of other options.
3. Select your new input type.

## Column input types

There are two types of input formats available for columns:

- Text with tokens
- Formulas

By default, columns are set to the **Text with tokens** input format.

### Switching column input types

You can switch the data type of your column within your table. To do this:

1. Click on the header of the column you want to edit to access the dropdown menu.
2. Select `Edit column` from the dropdown.
3. Click on the gear icon and select your new input type.
4. Press `Save settings` to save your changes.

## Column limits

- Clay tables have a default column limit of **100**.
- Clay tables have a default enrichment column limit of **40**.
- Tables using phone or email waterfalls can have this limit raised to a maximum of **60** (for that table only).
- Note: Enterprise Plans may have custom column limits.

## Create child columns from a parent column

When you enrich data within Clay, your results will be presented as arrays of data, which sometimes includes nested endpoints. You can create individual child columns by mapping specific endpoints from the parent column’s enrichment.

### Add a new child column

To create a new column with an endpoint from an enrichment (parent column):

1. Click on the cell of the enrichment containing the endpoint you want to use. This will open the **Cell details** panel on the right.
2. Hover over the endpoint you want to map out and to the right click `Add as column`.
3. In the **Add description as new column** section, enter your column description and click `Create column` to generate a new column.

### Map child columns to an existing column

To create a new column with an endpoint from an enrichment (parent column):

1. Click on the cell of the enrichment containing the endpoint you want to use. This will open the **Cell details** panel on the right.
2. Hover over the desired endpoint and click `Add as column` on the right.
3. Under **Map to an existing column**, click on the column you want you map this enrichment endpoint to. Note that this will overwrite the existing values within the destination column.

### Find the parent column of your child column

You can identify the parent column of a child column to better understand its data context. Follow these steps:

1. Click on the child column to open the dropdown menu.
2. Within the menu, select `Go to parent column`.

## Hiding columns

You can hide a column to help simplify your table view. This is helpful when you want to hide parents columns.

To hide a column:

1. Click on the header of the column you want to hide to access the dropdown menu.
2. Within the menu, select `Hide`.

## Merge columns

You can merge data from multiple columns into a new column.

1. Click `Add column` → `Merge columns`.
2. Select a `Data type` from the dropdown.
3. Write a formula, including any columns you want to add with `/`.
4. Click `Save settings`.

## Dedupe columns

You can also dedupe your rows based a specific column’s values.

To dedupe a column:

1. Click on the header of the column you want to dedupe to access the dropdown menu.
2. Within the menu, select `Dedupe`.
3. Confirm the duplicate values you want to remove and select `Delete`.

A few rules to keep in mind for column deduplication:

- Deleted rows cannot be recovered, so proceed with caution.
- Duplicates are identified based on exact string matches.
	- Deduplication is case-sensitive, meaning `Clay` and `clay` are treated as different.
		- Extra whitespace is considered, so `Clay (with a space)` and `Clay` are not the same.

## Rename columns

You can rename your columns to make them easier to identify. To rename a column:

1. Click on the column header you want to rename.
2. Select the `Rename` option from the dropdown menu.
3. Enter the new column name and press Enter to save it.

## Pin column

If your table has many columns, you can pin specific columns to keep them easily viewable. To pin a column:

1. Click on the column header you want to pin.
2. Select the `Pin` option from the dropdown menu.