---
title: "Deep Dive: Clay Sequencer [Automated Outbound]"
source: "https://university.clay.com/lessons/deep-dive-clay-sequencer-automated-outbound"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=QBaKMSCuf4c)

About this lesson

00:00

## Deep Dive: Clay Sequencer

In this lesson, we'll explore one of Clay's newest and most powerful features: our own native Sequencer, built directly inside of Clay. You can now create and run email campaigns directly inside Clay, without ever leaving the platform.

Instead of the traditional workflow where you enrich data in Clay, export it to Outreach or Salesloft or HubSpot, and then run your campaigns, you can now enrich, sequence, and measure everything inside the Clay environment.

For RevOps teams, this means you don't need to export enriched leads from Clay into other sequencing tools. For SalesOps, no more CSV juggling or CRM exports. For marketers running ABM campaigns, no more waiting for marketing ops or engineering. You can instantly build personalized sequences and trigger campaigns when Clay enrichment detects certain signals, going from idea to execution in minutes.

## 🚀 Two Ways to Start with the Sequencer

There are two ways to start with the sequencer:

The first and easiest way is through the Campaigns tab. Here you'll see all your campaigns and their status, which is either running or inactive.

The second way is if you want to build a campaign from a pre-existing table of leads. To do that, you'd go to the Actions tab and either create a new campaign or launch Clay Sequencer.

For now, we'll start from the Campaigns tab.

## 📋 Campaign Setup Process

When you click New Campaign, Clay provides a template campaign. This is the simplest possible setup to get you started, and it has three steps:

**Step 1: Sourcing Leads**

For now, we'll pull in leads from your target market. Once these leads get added, we move to Step 2.

**Step 2: The Contacts Table**

In the contacts table, you'll see the leads are automatically pushed in with a pre-configured work email waterfall. The key column in this table is the Send Table Data action. This action syncs your lead data from your parent table into the campaign. This is crucial; it's the main way data flows from your enrichment tables into your sequencing campaigns.

The best part: if you add additional columns or enrichments, those will automatically sync to your campaign via the Send Table Data action.

**Step 3: The Campaign Interface**

Once your data syncs, you'll see the campaign interface, which looks familiar if you've used Clay tables before. ALL the lead data from your contacts table is now available here for your campaigns, and any edits in the campaign table will automatically sync.

## ⚙️ Campaign Settings and Email Configuration

You'll want to choose an internal name that makes sense for tracking. Most importantly, you need to select the correct email address column. We try to auto-detect this, but it's what determines where your emails actually get sent.

You also have an HTML option here. While this enables inline images and links, I'd recommend keeping it off for outreach campaigns because HTML hurts deliverability. Plain text performs better for cold outreach.

## ✍️ Drafting Your Message Sequences

Here's where things get really powerful. Clay's AI can draft messages using your business context, which scrapes information about your company and ideal customer profile from your website, and then uses it in your campaign.

The AI snippets feature is particularly useful. You can generate personalized copy using job titles, names, company data, or any other enriched fields. You can preview how this output looks across different leads in real-time, so you know exactly how your personalization will appear. Then you can click into the snippet and tweak the configuration parameters however you see fit.

For follow-ups, you can add additional messages either as new threads or continuing the same thread, and schedule them with specific delays - like 3 days later.

The message drafting includes some sophisticated features:

- Clean variables provide safe substitutions with fallbacks - so if a company name is missing, it won't break your email
- Spin-tax lets you rotate phrases to avoid spam filters - things like alternating between "hi," "hello," and "hey"

## 📤 Sender Setup and Scheduling

For sending, you have two main options. You can use SMTP for direct account integration, or Google OAuth if you're using Workspace. If you open up the SMTP settings and have no idea what you're looking at, then you should probably use Google OAuth. Note that using Google OAuth does require admin authorization.

Scheduling is straightforward and flexible:

- You can set timezone and business hours like Monday through Friday 9 to 5
- Set spacing between emails - Clay recommends about 20 minutes between sends, which gets you roughly 24 emails per day
- Set delayed start dates if you want to prepare campaigns in advance

When you launch, certain elements get locked in: Your AI snippets and core campaign settings can't be changed after launch. But you can pause campaigns to edit copy, or complete them to permanently end the sequence.

## 📊 Analytics and Reply Management

Once launched, the Analytics tab shows live stats that you can refresh to see current performance.

The Clay Sequencer includes Reply Management. Every meaningful campaign event gets captured in a Campaign Events table: emails sent, replies received, and categorization of those replies.

Clay provides two pre-built actions:

- The Reply to Lead action can automatically generate AI responses to replies
- The Add Email to Blocklist action handles unsubscribe requests automatically

For the AI replies, I'd recommend setting up an approval flow so you have a human in the loop. For example, you could use Clay's Slack approvals enrichment. The AI drafts a reply, sends it to you in Slack for approval, and only sends it back to the lead if you authorize it.

## 📨 Global Inbox

There's a Global Inbox where you can monitor all your campaigns at once. You can see replies across all campaigns, manage responses centrally, and maintain full human control over what gets sent.

## 🎯 Conclusion

This is still early days for the Clay Sequencer, with more features coming. But the goal is clear: to make this one of the best sequencing experiences on the market while bringing you all the power of Clay's enrichment and automation capabilities.

You now have the full power of Clay's data enrichment feeding directly into sophisticated email sequences, all in one unified platform.