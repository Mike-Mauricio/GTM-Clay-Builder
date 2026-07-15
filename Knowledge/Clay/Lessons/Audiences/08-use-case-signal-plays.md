---
title: "Use Case 3: Signal-Based Plays [Audiences]"
source: "https://university.clay.com/lessons/use-case-3-signal-based-plays"
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

![](https://www.youtube.com/watch?v=sfs5OsiOsXw)

About this lesson

00:00

## Use Case 3: Signal-Based Plays

Timing is the thing CRMs are worst at. You've got thousands of contacts, and at any moment some are changing jobs, moving into buying roles, or landing at ICP-fit companies, but you usually find out days or weeks too late, if at all, and by then someone else got there first. Signal-based plays fix that: Clay watches every contact continuously and routes them the moment something changes.

We'll assume your Salesforce contacts are already synced. That's the baseline. What you're adding here is the monitoring, an audience built on the results, and the actions that follow.

## 🎯 Step One: Define the Audience to Watch

Start from **All People**, your full CRM, and narrow to the group that matters: your champion contacts at current customers, or your ICP target list. Filter down to create that audience.

If the group you want isn't fully in your CRM yet, say you're sourcing senior data-science leaders in New York to recruit, source a targeted list first the way you did in TAM sourcing, commit the net-new contacts into your People audience, then watch them the same way.

## 📡 Step Two: Add a Signal

With your audience defined, go to **Enrich** in the top right, then **Signals**, then **Add Signal**, and pick **Job Change**. Setup feels like the rest of Clay: choose how far back the first run looks (3, 6, or even 12 months) and how often it recurs. A 3-month lookback is a good default when timing is everything, like a potential poach or hire, since you don't want to reach out too late. Hit **Save and Run**, and Clay applies the signal to every contact in the audience, whether that's 800, 8,000, or 80,000.

A few things worth knowing:

- **You can add it from the Data Hub instead.** Same setup, different entry point.
- **Put a spend limit on it.** Signals run continuously, so they carry a recurring cost; cap it with a credit spend limit, exactly like a bulk enrichment.
- **They recur.** This isn't a one-time scan. Set a Frequency and the signal keeps watching: the next scheduled run might be a month out, then the next, and so on.

## 🔎 Step Three: Review the Results

This is the part that makes signals so powerful. When a job change fires, Clay writes that data directly onto the contact's record as a permanent field, *not* just inside this audience. Because it lives on the person, you can open any other audience, add a filter for "has a job-change result," and those contacts appear, no matter which audience originally triggered the signal. **The signal follows the person, not the list.**

To make it easy, Clay also **auto-creates a new audience**: your original filters plus a filter for everyone who now has a job-change result. That's your ready-to-act list, built for you. As the signal runs, you'll watch contacts populate into it, and you can monitor the signal's performance, edit it, and confirm the last run completed at any time.

## 🎬 Step Four: Act on the Results

Treat that job-changers audience like any other. Run enrichments and actions on it: enrich the new company, title, and LinkedIn; route the contact to the AE who owns the new account; feed them into a Clay table for outreach; or fire a Slack alert.

And the best part: any new contact who enters your original audience and *then* changes jobs is captured and routed automatically. You're covering your entire CRM continuously, not just the handful of accounts a rep happens to be watching.

## 🗂️ Managing Signals Centrally

Beyond setting a signal up inside an audience like we just did, you can manage every signal from the **Data Hub → Signals** tab, and apply one signal to multiple audiences at once.

## 🚀 What's Next

You've now got continuous coverage, data that follows the person, and a ready-to-act list that builds itself.

In the last use case, we take these signals and turn them into actual outreach: AI outbound.

Next up