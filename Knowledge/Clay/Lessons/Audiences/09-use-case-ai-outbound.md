---
title: "Use Case 4: AI Outbound [Audiences]"
source: "https://university.clay.com/lessons/use-case-4-ai-outbound"
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

![](https://www.youtube.com/watch?v=h4IBoKW19Ik)

About this lesson

00:00

## Use Case 4: AI Outbound

The last use case is where everything pays off: AI outbound. You combine signals with automated personalization to turn them into outbound sequences that actually convert. If you've done AI outbound in Clay before, the moves are familiar. What Audiences changes is the data layer around it, how you bring records in, segment them, and send them out, so you're just doing it faster.

## ⭐ The Star of This Use Case: The Action Step

The Action step is what hands your enriched contacts to a sequencer. Clay's native Sequencer works, and so does whatever you already use: SmartLead, Instantly, Outreach, or Salesloft.

## 🔄 How It Works, Step by Step

1. **A trigger occurs.** A signal fires, an enrichment runs, or a first-party system updates, and prospects who newly meet your criteria enter the audience.
2. **Auto-enrichment runs.** Clay fills in any missing contact data. **Field mapping is optional**, so you can run a bulk enrichment purely to fire an action, like kicking off a sequencer campaign, without saving any data back to Audiences.
3. **Sequencer handoff.** The contacts move into a campaign.
4. **AI personalization.** Clay's AI writes the messages from the enriched data right in the sequencer, pulling from the signal, recent company news, the job context, whatever you've got. Then it sends.

## 💼 Walking Through an Example

Let's pick up the senior data-science leaders audience from the signals lesson and turn it into outreach.

1. **Filter to the contacts who actually fired the signal.** Add a filter on the people signal for a job change in the last 90 days. That narrows the audience to the handful who genuinely changed jobs (three, in the demo). Save the filters as a new audience so it stays accurate.
2. **Add a bulk enrichment for the copy.** Go to **Enrich**, add a bulk enrichment, name it something like `DS Job Changers AI Outbound`, and continue. You'll land in the familiar table view, with the record ID, the imported audience record, and the linked company record already wired up.
3. **Write the AI message.** Keep it simple: tell the AI to write one sentence from the record, people, and job-signal data, like *"Saw that you just became \[title\] at \[company\]. Sad to see you go from \[previous company\], but excited for your next journey."* Feed in the record's fields and signals. You don't need web access, since all the data is already on the record.
4. **Test before you scale.** Run a few rows first (three, here), check the output, and refine; for real sends you'd make it more casual and readable. Nothing is charged until you run: completed rows show 0, remaining shows 3. Set a credit spend limit (say 1,000 a month) so it stays in bounds, and turn on auto-run if you want new job-changers outbounded automatically as they appear.
5. **Decide whether to save the copy.** To keep the copy in your audience, map the column to a field. Often you won't: this copy is specific to one play, and you may not want it sitting in your CRM polluting fields you care about. Leave **field mapping** off and the data just powers the action without persisting. (Only fields visible in the table are available to map, and you can always map it back later.)
6. **Add your sequencer.** Add the sequencer as an action and pick your tool, Clay Sequencer, SmartLead, or Instantly, connect your account, and map your variables. The full sequencer setup is its own course.
7. **Start the run.** With mapping off, the "update audience record" step is skipped, the copy still generates, and if a sequencer step is attached, the copy and contacts flow into your sequencer and the emails send. Processed rows drop out of the queue view to keep it clean (the data isn't gone); open the **Archived Run** anytime to see every row you've processed.

## 📈 Results

- **Pipeline from your highest-signal accounts**, without adding headcount or piling research onto reps.
- **Consistent outreach quality.** Every rep works from the same enriched data and the same AI messaging framework.
- **Speed.** Prospects get reached within hours of a signal firing, not days.

## ⚠️ Caveat One: Not Every Team Is Ready for Full Automation

Test in small batches and verify before you automate at scale. Clay gives you a **review step** between the AI personalization and the sequencer handoff, so a rep can approve, edit, or skip each message before it ever reaches a prospect. That's automation speed with a human in the loop, reviewing messages grounded in real data instead of writing from scratch.

Over time, drop the review step for audiences that have proven themselves: a job-changer audience with a framework you trust might run fully automated, while a brand-new persona stays in review longer. **You set the automation level yourself, per audience.**

## 🔌 Caveat Two: This Works With Any Sequencer

You don't have to rip out the tools you already use. You can use Clay Sequencer or any third-party tools (Outreach, Salesloft, Exportly, SmartLead, Instantly). That "field mapping optional" toggle is exactly what lets a bulk enrichment just run the action. Context flows automatically from your audiences into your sequencer either way.

One practical note: for high-volume sends, many teams use SmartLead or Instantly. Clay's native Sequencer is great for lower volumes, roughly a few dozen to a few hundred emails a day, where you're comfortable handling your own inbox warmup and rotation.

## 🚀 What's Next

That's the four use cases and the core of Audiences. You've seen what it is and why it exists, gotten your data in, toured the Audiences page and the Data Hub, walked the Segment, Enrich, Act framework, and built four real plays on top of it: CRM enrichment, TAM sourcing, signal-based plays, and AI outbound. You now have everything you need to build a self-maintaining data layer and run plays off it.

A full Sequencer deep-dive and ad-platform sync each get their own walkthrough. Audiences is also in active beta, so expect a bonus section on newer features, plus more use cases and updates over time. For now, it's your turn.

Happy Claymaking!

Next up