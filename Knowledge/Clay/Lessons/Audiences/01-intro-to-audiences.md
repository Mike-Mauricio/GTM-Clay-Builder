---
title: "Introduction to Audiences [Audiences]"
source: "https://university.clay.com/lessons/what-is-clay-audiences"
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

![](https://www.youtube.com/watch?v=NbJi1oJbLy0)

About this lesson

00:00

## Introduction to Audiences

Audiences is the new unified data layer in Clay: one always-current home for all your sales data that enriches itself, keeps your lists live, and turns signals into actions. Before we explain a single concept, here's what it actually does.

## 🎬 A 60-Second Tour

Here's the whole workflow we cover in the video above. Use the step-by-step bullet points to follow along:

1. **Open your Clay workspace.** Two new options sit in the left sidebar: **Audiences for people** and **Audiences for companies**.
2. **Look at the record count.** We've blown past the old 50,000-row limit. This database holds **17.5 million records**. Think of Audiences as the centralized layer behind everything you do in Clay.
3. **Slice it into an audience.** You'd never want to action 17.5 million records at once. In the sample email audience, filter job title to contain **Vice President** and location to **New York**, and the count drops from 17.5 million to **1,500**: specific and targeted enough to act on.
4. **Run an enrichment on the slice.** Add a bulk enrich action across all 1,500 rows. Open it up and it's a regular email AI column generating draft copy for every record (basic, demonstrative copy here, not finished outreach).
5. **Sync it back.** Those new fields map back to your audience's core dataset and sync to your CRM automatically.
6. **Send it to an action.** From here the full 1,500 can flow into **Workbooks** (where you work on data, still under 50,000 rows) or into **Ads** (covered in a separate course). Workflows is in beta, so we'll skip it here.

That's the whole loop: 17.5 million records in, a targeted 1,500-person slice out, enriched and synced back to your CRM. Now let's back up and explain why Audiences exists.

## 🗂️ The Three Problems Audiences Solves

Audiences exists to fix three problems that only get worse as your company grows.

1. **Your CRM decays the moment data lands.** It's supposed to be the source of truth for your sales team, but a record starts going stale the second it's created.
2. **Signals happen in real time; your CRM finds out too late.** A champion changes jobs, a target account raises a round, a company starts hiring fast. Your CRM has no idea until someone updates it by hand, and by then the window's already closed. Trying to catch every signal by building a thousand separate Clay tables gets gnarly fast.
3. **The bigger your database, the worse it gets.** RevOps teams spend months just keeping old data usable: reimporting lists, running enrichments, hunting down duplicates. It's maintenance that never ends. You need systems that scale as your company grows, not manual work that scales with it.

## ⚙️ The Four Things Audiences Does

Here's what Audiences does about all of that. Four things.

1. **Enriches and cleans your database automatically.** Gaps fill as they appear. A contact syncs in with no title, Clay enriches it. An email goes stale, Clay updates it. You're not kicking off a job, it just happens.
2. **Audiences update themselves.** An audience is a saved, live filter sitting on top of your full database (say, VPs at funded SaaS companies who changed jobs in the last 30 days), not a one-time CSV export. You build the filter once and it stays current as people drop in and out.
3. **Signals become triggers.** The signal fires and the action follows, automatically. A champion changes jobs and the right rep gets notified. An account raises money and it enters your outbound sequence.
4. **It works at much higher scale.** Millions of records at the same speed, not 50,000 per table.

**Put those together and that's what Audiences really is: the GTM data layer in Clay.** All your contacts, accounts, enrichment, and signals in one place that keeps itself current.

## 🔀 Audiences vs. Clay Tables

People ask how this relates to Clay Tables. Tables aren't going anywhere: they're still a core primitive. The simple framing is that Tables are how you *work on* data, while Audiences is where your data *lives* and where you slice the whole dataset. Under the hood, Audiences even uses table infrastructure to test your workflows across a few edge cases before you run them at scale.

|  | Clay Tables | Audiences |
| --- | --- | --- |
| Best for | One-off, one-time workflows | “Always-on” workflows that keep running |
| Role | How you *work on* data | Where your data *lives* |
| Scope | A specific working set you build and run | A slice across your entire dataset |
| Connections | Built per workflow | Continuously synced to your CRM, warehouse, and other sources |
| Scale | Up to 50,000 rows | Millions of records |

They work together. You still build and run workflows in Tables, they just pull from a cleaner, richer, always-current foundation now.

## 👥 Who It's For

Audiences was built for:

- **RevOps teams buried in data maintenance**, whose weeks fill up with reimporting lists, chasing duplicates, and running enrichments.
- **Teams with large CRM databases** that have grown past what anyone can keep usable by hand.

## 🚀 What's Next

You now know what Audiences is: the unified, self-maintaining data layer that sits behind your whole Clay workspace, and how it differs from the Tables you already use.

Next, we'll get your data into Audiences: connecting your CRM and deciding what flows in and what syncs back out.

Next up