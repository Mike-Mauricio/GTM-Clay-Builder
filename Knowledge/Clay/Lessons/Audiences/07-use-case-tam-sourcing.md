---
title: "Use Case 2: TAM Sourcing [Audiences]"
source: "https://university.clay.com/lessons/use-case-2-tam-sourcing"
author:
published:
created: 2026-07-14
description:
tags:
  - "clippings"
---
##### Audiences

Learn how RevOps teams use Clay Audiences to build a unified data layer so you can sync your CRM, create dynamic segments, and activate your data at enterprise scale.

Progress

![](https://www.youtube.com/watch?v=0qNyIiqR2eY)

About this lesson

00:00

## Use Case 2: TAM Sourcing

CRM enrichment cleaned up the records you already have. TAM sourcing builds all the records that *should* be in your CRM but aren't yet: your total addressable market. You pull net-new companies out of Clay's company, people, and jobs database, filter them to your ideal customer profile, and push verified, enriched accounts into Salesforce for the first time. It's the same four steps, Data → Audience → Enrich → Action, just running in the opposite direction.

## 🎯 Step One: Define Your ICP Filters

Go into Clay's company database and narrow to your ideal customer profile: industry and sub-industry, an employee-count range, and geography (HQ country, state, or metro). If you'd rather not stack filters by hand, use **Sculptor** and describe your ICP in plain language. Either way, hit **Continue** and save to companies or people.

For example, search for software companies headquartered in New York with 51 to 200 employees. Sculptor may overshoot a boundary, so trim what you don't want (drop the 201 to 500 band) and add the New York location, landing at around **2,776 companies**.

## 🔎 Step Two: Refine in Draft

Draft is your safety check before anything locks in. Preview the audience, see exactly how many records your filters return, and confirm the logic is doing what you think. This is where you catch the classic mistake: filters too loose, pulling **800,000 companies when you expected 80,000**. Catch it here and tighten with enrichments or signals, like a tech-stack filter or a hiring signal, until the list is right.

The draft is also where **entity resolution** proves its worth. When you save a search to your companies audience, Audiences automatically excludes anything already in it. Re-run a search you've already sourced and you'll see almost nothing new: in the demo, re-running that New York software-companies search surfaced just **9 genuinely new companies**, with nearly everything else already in the audience. You can also check the history of enrichments already run on those records, so you never pay for the same enrichment twice. Nothing is committed yet; the draft holds the results until you move them in.

## ✅ Step Three: Commit the Draft

Committing locks the records in: they're added to Audiences, enrichment kicks off, and credits start being used. What you're left with is a list of accounts your team genuinely has no relationship with yet.

## ✨ Step Four: Enrich Your TAM

You don't really do anything here. On commit, Clay **automatically enriches** each account in whatever audiences it qualifies for. No manual triggering.

## 🎬 Step Five: Activate

This is where the TAM becomes useful, and you've got a few options:

- **Sync to Salesforce as net-new accounts.** Your CRM goes from reflecting only the accounts you've touched to reflecting your entire addressable market. For the write-back rules, use the sync and export criteria you set in the [CRM Enrichment lesson](https://university.clay.com/lessons/use-case-1-crm-enrichment).
- **Run outreach with the sequencer of your choice.** Enrich, then hand off to your sequencer, with no CSV exports and no manual list-building.
- **Route by territory.** Because your audience is already built on geography, industry, and company size, use those same dimensions to route accounts to the right AEs with an enrichment on the audience. Every rep gets a **dynamic list** of high-fit targets in their patch that updates itself as new companies qualify.

## 🔄 Why This Beats a Manual TAM

The old way was painful. Clay tables capped you at 50,000 rows, so any real TAM meant breaking it into separate searches, stitching them back together through your CRM or a workbook, and hunting down the overlap between searches (it's exactly why Clay added the ability to exclude prior searches). And a CSV from a one-click data tool is a point-in-time snapshot, stale the second you download it.

Audiences gives you a living view instead: the audience tracks your ICP filters continuously, entity resolution keeps your existing accounts excluded automatically, and enrichment runs on every new company that qualifies. A clean, enriched, always-current view of every company you *could* be selling to.

## 🚀 What's Next

You've now built a living TAM: net-new accounts sourced to your ICP, auto-enriched on commit, and ready to sync to Salesforce or route to the right reps, all of it staying current on its own.

Next up, use case three: signal-based plays, where we solve timing.

Next up