---
title: "Audiences FAQs and best practices"
source: "https://university.clay.com/docs/audiences-faqs-and-best-practices"
author:
published:
created: 2026-07-14
description: "Common questions and best practices for using Clay Audiences."
tags:
  - "clippings"
---
Overview

Clay Audiences is the unified data layer in Clay — one always-current home for all your sales data that enriches itself, keeps your lists live, and turns signals into actions. This page covers best practices for getting the most out of Audiences and answers to frequently asked questions about how it works.

## FAQs

## When should I use Audiences vs. a table?

Use Audiences by default for anything you want to reuse, segment on, or build automations on top of. Use tables for one-off workflows, integrations Audiences doesn't yet support natively, or cases where data doesn't need to persist beyond a single run.

The simplest framing: Tables are how you *work on* data. Audiences is where your data *lives*. They work together — you still build and run workflows in Tables, they just pull from a cleaner, richer, always-current foundation.

|  | Clay Tables | Audiences |
| --- | --- | --- |
| **Best for** | One-off, one-time workflows | "Always-on" workflows that keep running |
| **Role** | How you *work on* data | Where your data *lives* |
| **Scope** | A specific working set you build and run | A slice across your entire dataset |
| **Connections** | Built per workflow | Continuously synced to your CRM, warehouse, and other sources |
| **Scale** | Up to 50,000 rows | Millions of records |

## What if my integration isn't supported yet?

Use the `Upsert Audiences Record` table enrichment as a bridge. Bring your data into a Clay table from any source, then use Upsert to push those records permanently into your Audience. This works for any source Audiences doesn't yet natively support.

## My CRM is messy. Should I clean it up before setting up Audiences?

You don't need a clean CRM to get started — CRM cleanup is often the first use case Audiences enables. A common approach: sync your existing CRM, run LinkedIn enrichments to refresh contact data, use the enriched identifiers to surface duplicates, then build further enrichments from there.

## Does Audiences update automatically?

Yes. Segments update in real time as records enter or exit your filter criteria. The refresh frequency depends on your plan:

- **Enterprise plan:** CRM and data warehouse syncs run every 15 minutes, and segments update continuously.
- **Growth plan:** CRM and data warehouse syncs run daily, and segments update based on that daily refresh.

Enrichments configured with `Continuous Enrichment` enabled automatically process new records entering a segment, typically within 15 minutes.

## How does matching work in Audiences?

When you import a source, you choose a single identifier to match on — it's not a prioritized list that Clay falls through automatically. You pick one and Clay deduplicates and merges on that. For people records, you can match on **LinkedIn URL**, **email**, **phone**, or **name + state**. For company records, you can match on **domain** or **LinkedIn URL**.

When a match is found, Clay merges those records into a single unified profile. The more of these fields you map when importing a source, the more accurate your overall matching will be.

**Caution:** Choose a truly unique identifier. Any records that share the same value on your chosen identifier will be merged — and this includes duplicate records within a single source, not just matches across sources. To avoid unintentionally merging distinct records, match on a field that is reliably unique to each person or company.

## Best practices

### Import before you export

Turn on import first, validate Clay's data quality, then enable write-back once you trust what you're seeing.

### Filter before enriching

Define your audience filters before running Bulk Enrich. Credits are charged per record enriched — if you enrich `All People` instead of a filtered segment, you pay for every record in your database. The narrower your audience, the more targeted and cost-efficient your enrichment run.

### Test enrichments on 10 rows before running at scale

Before running across your full segment, click `Run on 10 rows` and confirm the output is correct and field mapping is configured as intended. Given the credit implications of a misconfigured enrichment across millions of records, treat this as a standard step every time.

### Check your field mapping intent before hitting Start Run

Field mapping is on by default. If you want enriched data to write back to Audiences, confirm your column mappings are configured. If you're running an enrichment purely to trigger an action without saving data, explicitly disable field mapping so the run behaves as expected.

### Work backwards from the use case when building segments

Don't start with the data and ask what to filter. Start with the finish line: what action will be taken on this segment, and by whom? Segment by rep assignment for outbound, by product signals for PLG, by deal stage for pipeline plays.

### Use CPJ draft mode to qualify records before committing

Records from People Search land in draft state before entering `All People`. Use this window to apply additional filters, run a quick enrichment, and verify quality before clicking `Commit` — credits for downstream enrichments and actions are not spent until records are live.

### Schedule large initial syncs at end of day

For enterprise customers where Salesforce is live and operational, start large initial syncs near end of business EST. If the sync generates high load, it won't interfere with critical business functions.

### Do the API math with nervous admins

Divide your total record count by 50,000 (import batch size) to estimate import API calls, or by 10,000 for export. For most enterprise customers, the math makes this a non-issue — a 5M-record CRM generates only 100 import API calls against a Salesforce limit typically around 150 million records per day.

### Start narrow, then expand

Start with one scoped use case, demonstrate value, then expand. Customers who see one use case working naturally discover the next — signals lead to TAM sourcing, TAM sourcing leads to account matching. Trying to configure everything at once often stalls progress.

Table of contents[FAQs](#faqs)[When should I use Audiences vs. a table?](#when-should-i-use-audiences-vs-a-table)[What if my integration isn't supported yet?](#what-if-my-integration-isnt-supported-yet)[My CRM is messy. Should I clean it up before setting up Audiences?](#my-crm-is-messy-should-i-clean-it-up-before-setting-up-audiences)[Does Audiences update automatically?](#does-audiences-update-automatically)[How does matching work in Audiences?](#how-does-matching-work-in-audiences)[How does Clay handle Salesforce Lead-to-Contact conversions?](#how-does-clay-handle-salesforce-lead-to-contact-conversions)[What's the difference between automatic Lead/Contact merging and deterministic matching?](#whats-the-difference-between-automatic-leadcontact-merging-and-deterministic-matching)

[

Best practices

](#best-practices)[Start with RevOps, not marketing or sales](#start-with-revops-not-marketing-or-sales)[Import before you export](#import-before-you-export)[Import more fields than you think you need](#import-more-fields-than-you-think-you-need)[Filter before enriching](#filter-before-enriching)[Test enrichments on 10 rows before running at scale](#test-enrichments-on-10-rows-before-running-at-scale)[Check your field mapping intent before hitting Start Run](#check-your-field-mapping-intent-before-hitting-start-run)[Work backwards from the use case when building segments](#work-backwards-from-the-use-case-when-building-segments)[Use CPJ draft mode to qualify records before committing](#use-cpj-draft-mode-to-qualify-records-before-committing)[Schedule large initial syncs at end of day](#schedule-large-initial-syncs-at-end-of-day)[Do the API math with nervous admins](#do-the-api-math-with-nervous-admins)[Start narrow, then expand](#start-narrow-then-expand)