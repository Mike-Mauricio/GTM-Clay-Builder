---
title: "How Audiences Works [Audiences]"
source: "https://university.clay.com/lessons/how-audiences-works-import-enrich-action-export"
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

![](https://www.youtube.com/watch?v=IBqBC2g8C70)

About this lesson

00:00

## How Audiences Works

Every audience play you'll ever run comes down to one simple framework: Segment, Enrich, Act. This lesson walks it end to end by building one real play: finding product managers in New York who just changed jobs, writing them AI outbound copy, and sending it wherever you want.

## 🌊 The Framework: Segment, Enrich, Act

Every targeted play in Audiences follows the same three steps: **Segment, Enrich, Act. SEA, like the ocean.** It's the larger-scale counterpart to the FETE framework you may already use in Clay, and it takes even fewer steps.

One thing happens before SEA even starts: your **data syncs**. The sources you connected in the Set Up lesson keep importing new records in the background, and that's what feeds your audience, the universe of unified data behind everything in Clay. SEA is what you run on top of that universe when you're ready to act.

## 🎯 Segment: Slice Your Universe

Start with the data you already have. You don't need to pull in a fresh Find People or Find Companies table; you can act directly on your existing universe, in this example, 1.3 million people you've already touched, researched, or imported.

Create a new audience inside that universe and add your filters:

1. **Add a title filter** for Product Manager.
2. **Add a location filter** for New York.
3. **Name the segment** something clear, like `PM Job Changers New York City`.

Because Audiences handles millions of records, a segment can take a few seconds to load. When it settles, this one narrows 1.3 million people down to about **500**.

For a tighter match, build a filter group with every variation of "New York" and of "Product Manager," or add more ICPs the same way.

## ✨ Enrich: Add Data to the Segment

Enrich is where you add data to those records. This play uses both kinds of enrichment: a signal and a bulk enrichment.

### Add a Signal

First, add a **job-change signal**, then save and continue (your filters save to the audience at the same time). The signal does two things: it finds **who on your list has already changed jobs in the last three months**, and it keeps the segment dynamic, firing automatically whenever one of these contacts changes jobs going forward.

You can build far more robust versions of this: tracking champions who move companies, watching existing customers switch jobs, or catching new job listings at target accounts.

### Add a Bulk Enrichment

Next, add a **bulk enrichment** for the AI copy and name it something like `AI job changer copy`. You'll land in a familiar table view. **Run just 10 rows first** to confirm the output looks right before spending credits on the whole list. (Nervous about credits? That's the very next lesson.)

The enrichment is an AI column. The prompt writes a sentence like *Congrats on \[job title\] at \[company\]*, using the contact-level fields as input. Test it on the 10 rows, and if it reads well, keep going. For real outbound you'd normalize the titles, turning `Vice President, Product Manager` into natural language and dropping the seniority; for the demo, leave it. Normally you'd refine the prompt in the Claygent Builder, which has its own lesson.

### Map It Back and Run

A few things to notice on the run setup:

- **No credits are spent until you run.** The total rows run still shows zero.
- **One enrichment, many audiences.** This enrichment applies to this audience, but you can reuse the *same* enrichment across others. Separating your enrichment volumes from your segments means you stop rebuilding the same table logic over and over, the same modularity that makes Functions powerful.
- **Map the result to a field** so it shows up in your audience. Here, overwrite the `job change message` field.

Run it and watch the rows process in real time. Because the signal already makes this segment dynamic, you don't need a recurring enrichment. As all 501 rows process, you'll see each one queue and return **success**, and **any record that errors is automatically surfaced for you to troubleshoot**, so edge cases don't get lost in a mass run.

Your segment's work lives in a workbook nested under the PM Job Changers audience, so you can jump back up to the audience itself (or to the general all-contacts audience) anytime. Make the `job change message` column visible and you'll see the updated copy written across every contact.

## 🎬 Act: Send It Where It Needs to Go

Now the enriched records live in your unified data layer, ready to action. Where do you want them to go?

- The biggest use case today is **exporting to an ad platform**.
- You can also push to a sequencer, into Slack, or out to third-party tools.
- And your **CRM updates itself**. Because you set your Salesforce sync rules back in the Set Up lesson, the enriched data flows back automatically, with no per-play lookups.

That's the payoff of architecting your data infrastructure once, at the outset: you act on your data immediately, and your system of record stays current in the background instead of being something you have to think about every single time.

## 🔄 It's a Loop, Not a One-Time Workflow

Segment, Enrich, Act is the whole framework, but the real power is that it doesn't stop. Your data syncs keep feeding the universe, your segments stay live, your signals keep firing, and your actions keep running on every new record that qualifies. What you get is a self-maintaining data layer: your CRM stays current, your audiences stay fresh, your outbound keeps running, and nobody's babysitting the plumbing.

## 🚀 What's Next

You've now run a full play end to end: you segmented 1.3 million people down to about 500 product managers in New York, enriched them with a job-change signal and AI outbound copy, and set it to act and sync back to your CRM automatically.

Next, we'll tackle the thing everyone worries about once they see enrichment at this scale: Managing Credits in Audiences.

Next up