---
title: "Use Case: Contact & Account Enrichment [Functions]"
source: "https://university.clay.com/lessons/use-case-contact-account-enrichment"
author:
published:
created: 2026-07-14
description:
tags:
  - "clippings"
---
##### Functions

Learn how to build reusable enrichment workflows in Clay — called Functions — so you can standardize your best logic, eliminate duplicate work, and propagate changes across every table the moment you make them.

Progress

![](https://www.youtube.com/watch?v=MFgVvJwsrvw)

About this lesson

00:00

## Use Case: Contact & Account Enrichment

This lesson walks you through two real-world Functions you can build and use immediately: company firmographic enrichment and company hierarchy enrichment, both ready to call from any table.

## 🎨 What Teams Are Actually Building

Beyond basic email enrichment waterfalls, teams are building sophisticated Functions: account enrichment for HQ, industry, and employee count; external API pulls; contact enrichment with regional variants that change logic based on location. One team built a full account research sequence into a single Function: website to ICP fit to decision maker to work email, one call.

Here are two Functions that demonstrate what's possible.

## 📊 Use Case One: Company Firmographic Enrichment

Click here to [create this function using a template](https://app.clay.com/shared-table/share_0tb2z2z482RrNqVsxWi).

This Function takes a company domain and returns three data points: revenue, employee count, and monthly website traffic.

No single data provider has all three for every company, so we've built three separate waterfall sequences—one per data point. Each waterfall tries multiple providers in order until one returns a result, maximizing fill rate without overpaying for redundant lookups.

### Inputs

Four inputs: Company Domain, Company Name, Company LinkedIn URL, and CPJ Employee Count. The last one matters—if you already have an employee count, the Function checks for it before running the waterfall to avoid wasting credits.

### Revenue Waterfall

Four providers in sequence: HG Insights, People Data Labs, Pubrio, then RocketReach. As soon as one succeeds, we stop.

### Employee Count Waterfall

First, checks if CPJ Employee Count is populated. If yes, uses it and skips the rest.

If not, pulls from HG Insights, People Data Labs, Pubrio, RocketReach, then falls back to Clearbit and SMARTe. Six providers total before giving up.

### Monthly Website Traffic Waterfall

Four providers: Semrush, SerpStat, Datagma, then Store Leads. Same pattern: go down the list, stop when you get a result.

### How It All Comes Together

A "Send data back" action takes all enriched data from the three waterfalls and writes it back to the originating table.

From your main table: add one Run Function column, map in company domain and name, get back revenue, employee count, and web traffic. Three waterfalls, twelve total provider lookups, one column.

## 🏢 Use Case Two: Company Hierarchy Enrichment

Click here to [create this function using a template](https://app.clay.com/shared-table/share_0tcf4mf73y8JtbXGf3U).

This Function solves a genuinely difficult problem: mapping the full corporate family tree. Who's the immediate parent? Ultimate parent? Immediate subsidiaries?

This gets complicated with franchises, individual practitioners, and international entities. Is this Starbucks the corporation or a licensed franchise owned by a regional operator? This Function figures it out.

### Inputs

Company name, domain, and/or location. You don't need all three, just whatever you have.

### Phase One: Deep Research

**Company Overview**: AI agent researches company description, business model, customers, and gathers clues about corporate structure (franchise, subsidiary, publicly traded). This context feeds into hierarchy mapping.

**Company Addresses Research**: Finds all physical locations—headquarters, offices, franchises, warehouses. A company with one Denver office differs vastly from one with 200 Southeast franchise locations.

**EMEA/HG Hierarchy**: Pulls pre-existing hierarchy data from external providers. HitHorizons handles European companies, HG Insights handles everything else. If the hierarchy is already mapped, we start there.

### Phase Two: Intelligence Synthesis

**Hierarchy Scrape**: Main AI research agent searches the web for parent companies, ultimate owners, franchise relationships, and immediate subsidiaries. Sources include corporate filings, press releases, and about pages.

**Hierarchy Data Gap Fill**: If critical information is missing (domains or addresses for discovered entities), this runs targeted follow-up research to complete the picture.

### Phase Three: Final Consolidation

**Hierarchy Consolidation**: Takes all research, resolves conflicts between sources, applies business logic, and outputs a clean, structured hierarchy. If one source says the parent is X and another says Y, this step determines which is the immediate parent versus ultimate parent.

### Package and Return

The Function extracts specific parent and subsidiary entities into separate fields and runs "Send data back" to return all enriched hierarchy data to the originating table.

From your main table: add one column, pass in company name and domain, get back the full corporate family tree—immediate parent, ultimate parent, immediate subsidiaries.

## 🚀 What's Next

You've now seen two advanced Functions: firmographic enrichment running three parallel waterfalls across twelve providers, and hierarchy enrichment using AI agents to map corporate family trees from scratch.

Next lesson: email copywriting.

Next up