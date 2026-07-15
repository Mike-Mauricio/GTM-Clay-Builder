---
title: "Managing Credits in Audiences [Audiences]"
source: "https://university.clay.com/lessons/managing-credits-in-audiences"
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

![](https://www.youtube.com/watch?v=O2Ok29e_0mY)

About this lesson

00:00

## Managing Credits in Audiences

Audiences let you run massive plays across your entire unified data layer, which is exactly why the first worry everyone has is the same: am I about to burn tens of thousands of enrichments without meaning to? Clay builds in safeguards so you don't. Two of them do most of the work, and this lesson covers both, plus the dashboard that shows you where your data stands.

## 📊 Start With the Data Hub

Before you optimize spend, get a read on where your data actually stands. From any audience (we'll use the People audience, since that's where most of our work has been), open the **Data Hub**.

The Data Hub shows the **fill rate for every field across your entire audience**. Think of it as a health monitor for your CRM data. Is it a problem that only 5% of your first-name fields are filled? Maybe, maybe not, but now you can see it and decide. For most workspaces the fields that matter are the crux of your records: name, title, location, and LinkedIn URL.

## 🔁 Safeguard One: Reuse Enrichments Across Audiences

Your bulk enrichments behave like functions: build one, then point it at more than one audience. Reusing an enrichment instead of rebuilding it is the first big way you save credits.

Say you want to take the **AI job changer copy** enrichment from the last lesson and apply it to a different segment. Here's the flow:

1. **Open the enrichment to edit it.** If it's live, you can't change its audience, its logic, or its field mapping yet, because it's running.
2. **Pause it.** Confirm and pause. Pausing only means new signals and data won't auto-update while it's paused; when you resume, every field gets caught back up.
3. **Point it at a new audience.** If you don't see the option to swap the audience directly, click **Reset** first. Despite the name, Reset doesn't delete or rewind any of your data; it just clears the rows so the workflow can re-point. Then select the new audience, say a People audience with 940 people instead of your original 501.

Now the credit magic. If those two segments overlap, say 300 of the records sit in both, **Clay never runs the same record for the same field twice**. Everything is unified at the total audience layer in the background, so the overlap is deduped automatically and you only pay once. Use your enrichments discerningly and trust the back end to optimize the rest.

## 🚦 Safeguard Two: Set a Credit Spend Limit

The second safeguard is a hard cap. On any bulk enrichment, you can see the **remaining rows to be enriched**, and you can set a **credit spend limit**.

Say you never want to run your AI job-changer copy on more than 1,000 leads at a time. Set the limit to **1,000**. At roughly one credit per AI enrichment (sometimes less on a cheaper model), that enrichment will never spend more than 1,000 credits at the workspace level. If you hit the limit, you get a notification, so you can go manage the enrichment, decide whether you actually need the extra data, or dig into why you're hitting it so fast.

If you've estimated your spend well (credits per row, times frequency, times the size of your segment), a per-enrichment limit safeguards every table from quietly running over.

## 🚀 What's Next

You've now got the two levers that keep credit spend under control: reusing enrichments so overlapping records dedupe automatically, and setting a hard spend limit on each enrichment.

That covers the core of Audiences, the features and the navigation. Next, we'll get into the four main use cases, starting with CRM enrichment.

Next up