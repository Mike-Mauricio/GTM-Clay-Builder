---
title: "Use Case 1: CRM Enrichment [Audiences]"
source: "https://university.clay.com/lessons/use-case-1-crm-enrichment"
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

![](https://www.youtube.com/watch?v=daCGDe6-iew)

About this lesson

00:00

## Use Case 1: CRM Enrichment

CRM enrichment is the first of the four use cases, and it's the one Audiences changes most. This lesson builds a loop that fills the gaps in your CRM automatically and writes the clean data back to Salesforce, so your reps work from current records without anyone running a manual pull. It's just the four steps, Data, Audience, Enrich, Action, pointed at your own CRM.

## 🧠 Your CRM Is the Destination, Not the Pipeline

CRM enrichment used to be cumbersome. You'd export a list from your CRM, import it into a Clay table (capped at 50,000 rows), map every field you wanted updated, write conditional formulas so you only enriched what was missing or stale, combine it all into one column, then map that back to the right Salesforce or HubSpot fields. It was very easy to get wrong, and a more polluted CRM is the last thing anyone wants.

Audiences flips the mental model. Instead of Clay being a pipeline *into* your CRM, **your CRM becomes the final destination and Audiences becomes your unified data layer**. Almost all of your data lives in Audiences, so you'll usually have more data in an audience than in your CRM. The CRM becomes just the place you send the clean, final results for your team to action.

The best way to dive into this case study is to watch the video above. Use the written content to help follow along.

## 📥 Step One: Import Your CRM Records

You did the heavy lifting in the Set Up lesson: connect your Salesforce contacts and accounts, and the first connect pulls all of them in. Map your fields, and your entire CRM is now sitting in Clay as audiences, with no 50,000-row cap.

## 🎯 Step Two: Build an Audience of the Gaps

Now target exactly the records that have gaps. Filter down to what needs work, for example all contacts where account type is prospect *and* email is blank, or all accounts where revenue is missing. The Data Hub helps you spot where to aim: it shows the fill rate on every field, so when you see email sitting at, say, **9% filled**, you know exactly what to build an audience around.

Targeting first keeps your enrichment focused and credit-efficient: every enrichment costs credits, so you don't want to enrich records that are already complete. **Define the audience before you enrich.** In Clay tables, scoping first was required, so the table made you do it; in Audiences it's optional, and that flexibility is exactly how you rack up runaway credit spend without meaning to.

## ✨ Step Three: Add Your Enrichments

When you add an enrichment, Clay opens a **bulk enrichment table**. It looks and feels just like a Clay table, except this one runs across 50,000+ rows at once. Start with something like **Enrich Person** and choose the fields you want: name, title, organization, follower count.

**Run a test batch of 10 first**, confirm the output looks right, then scale to the full audience. And set a **credit spend limit** on the table, say 1,000 credits, so a big enrichment can't run away from you. If you hit the cap and want more, just bump the limit.

## 🗺️ Step Four: Map the Data Back

Mapping is the step that actually *saves* the data. In the mapping panel, choose which enriched column maps to which audience field. If the field doesn't exist yet, create it right there. Hit **Start Run**, and that new field is written to every record in your audience.

A few things this unlocks:

- **Every field you map back becomes filterable**, so you can layer enrichments: enrich, filter on the result, then enrich again.
- **Mapping is optional.** If you only want to run an action and don't care about saving the data, turn mapping off and skip the write-back. (We'll use that in the AI outbound lesson.)
- **One enrichment can feed multiple audiences.** From the Data Hub, point the same enrichment at several audiences at once instead of rebuilding it for each.
- **Make it self-maintaining.** In Run Settings, turn on **Continuous Enrichment** to enrich new records the moment they're added, or set a **schedule**: daily, monthly, or custom, where you control the exact time and which days of the month it reruns. Set it once and the loop just runs.

## 🎬 Step Five: Take Action and Sync Back to Salesforce

Enrichment without an action is just cleaner data sitting there. The action is what turns it into pipeline. Build an audience of your newly enriched records (say, work email was just filled and the confidence score clears your bar) and trigger something downstream: **send them into a sequencer**, or **Slack the AE who owns the account**.

Often the action is simply letting the data **sync back to your system of record**. Write-back is one of the actions, and you decide which fields go back, since some data is great for filtering inside Clay but doesn't need to live in Salesforce. To write a field back:

1. **Map the audience field to a Salesforce field.** Pick the audience field, then the Salesforce field to sync it to. If it's net-new data, have your Salesforce admin create that field first, and match the type (an email *value* may need a text field, not a Salesforce email-address field).
2. **Set the export rule per field.** Starting a fresh data architecture? Use **Always Write** so all of your correct audience data flows in. Layering onto an existing, patchy CRM? **Write If Empty** is safer, but know the tradeoff: if a record has stale data in Salesforce and fresh data in your audience, Write If Empty won't replace it. Test a few records and check both sides before committing a rule field by field.
3. **Turn on Create New Salesforce Records** so net-new accounts and people get added to your CRM, and **continuously sync**, which runs every 24 hours.

For example: you spot in the Data Hub that email is only 9% filled and still set to Never Write. You switch email to Always Write, build an "email fill" audience filtered to email is blank, run a bulk email enrichment (test 10, set a credit limit, run), and because the rule is set, the results sync straight back to Salesforce.

## 🗄️ Reviewing Past Runs

Need an audit or recovery trail? Open any enrichment and check the **Archived Run** view: it holds all the data that passed through that bulk enrichment in the past, ready to look at or export. If anyone ever needs to see what happened to their data, or recover it, it's right there.

## 🔄 The Result

Gaps close automatically as records flow into the audience. Your reps get the contact info they need right inside Salesforce, with no separate tools and no asking RevOps for a data pull. Because enrichment happens on the CRM record itself, attribution stays clean. Salesforce stays your record of truth, and Clay quietly keeps it current. Your data residency shifts from the CRM to the audience, and the CRM goes from something you maintain, clean, and debug to the final resting place for the data you actually care about.

## 🚀 What's Next

You've now built a CRM-enrichment loop: import your records, target the gaps, enrich them, map the data back, and sync the clean fields into Salesforce on rules you control, all running on its own.

Next up, instead of cleaning the records you have, we go find the ones you don't: use case two, TAM sourcing.

Next up