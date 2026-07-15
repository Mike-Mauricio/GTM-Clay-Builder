---
title: "Lead Routing [Automated Inbound]"
source: "https://university.clay.com/lessons/lead-routing-inbound-automation"
author:
published:
created: 2026-07-14
description:
tags:
  - "clippings"
---
##### Automated Inbound

Learn how to automatically enrich, score, and follow-up with inbound leads with Clay's inbound automation engine for lightning-fast speed-to-lead.

Progress

![](https://www.youtube.com/watch?v=4fvDht5gwsY)

About this lesson

00:00

## Lead Routing

## 📬 Lead Routing with Clay: Getting the right leads into the right hands

Welcome to lesson six of Inbound Automation, lead routing.

So far in this course, we’ve gone over how to capture inbound leads, enrich them with data, and score them to figure out who’s worth prioritizing.

After identifying your best leads, there’s another crucial step: making sure those leads get surfaced to the right people in your sales org as quickly as possible.

That’s where lead routing comes in. It allows you to:

- Balance workloads across your sales team
- Respect territories or specializations
- Maximize speed-to-lead
- Stay flexible as your team and priorities develop

In this lesson, we’ll walk through how to set up a dynamic lead routing system right inside Clay.

## 🔃 Lead Routing with Clay: Round Robin

Right now, the best way to do lead routing in Clay is to use a rep table as your live source of truth.A rep table should contain fields like rep name, email, status (active, on vacation, etc.), any other criteria you want to include, and weights.

If you’re using Salesforce, you can query your rep data directly with an SFDC import. You can set that import on a schedule so your table stays up to date.

Use Clay’s **Distribute Leads Round Robin (Weighted)** action that can be found by searching in enrichments. Then, map it to the rep table you created.

Higher weights increase the rate at which the rep is selected. As an example, imagine you have reps with the following weights: 2, 2, 1. Then they will each receive 40%, 40% and 20% of the incoming lead assignments respectively. If weights are unspecified, all reps will default to a weight of 1 for an even lead distribution.

This native routing feature should cover most basic lead routing use cases. It works beautifully if all your routing data lives in Salesforce.

Things can get a bit trickier if you want to incorporate signals that aren’t stored in Salesforce. If your routing logic starts to get very complex or niche, you might consider additionally investing in a dedicated routing tool like Default to handle those advanced edge cases.

Even with Clay’s basic weighted round robin, you’ll see huge improvements in speed-to-lead and workload balancing among reps.

As your team scales and your routing rules become more sophisticated, you can gradually layer on more logic or evaluate specialized tools if needed.

## ✅ That’s a wrap!

With this approach, you’re getting your best-fit inbound leads into the right hands as quickly as possible.

Stay tuned for our next lesson, where we’ll cover personalized outreach to leads, leveraging all the data we’ve already collected. Happy routing!

Next up