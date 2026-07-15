---
title: "Use Case: Email Copywriting [Functions]"
source: "https://university.clay.com/lessons/use-case-email-copywriting"
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

![](https://www.youtube.com/watch?v=jPP9-do-GXc)

About this lesson

00:00

## Use Case: Email Copywriting

In the last lesson, we covered two enrichment Functions: firmographic enrichment and company hierarchy.

This Function writes personalized outbound emails. You pass in an email address and get back three ready-to-send message variants.

You'll see how to use Functions not just for enrichment, but for taking action on that data.

## 📥 Step One: The Input

The Function takes one input: a contact's email address. Everything else gets looked up.

## 🔍 Step Two: Data Enrichment

The Function pulls intelligence about the contact from two directions.

First, a Get Contact step looks the person up in Salesforce to get their basic contact record and Account ID, which connects the person to their company.

Then two Snowflake queries run.

**Contact Intelligence** pulls first-party person-level data:

- Product usage patterns like workspace opens, table activity, and enrichment usage
- Conversation history from recorded calls
- Job change information and employment timeline
- Previous Clay experience
- Engagement scores and contact stage

**Account Intelligence** pulls first-party company-level data:

- Firmographics like industry, size, revenue, business model
- GTM motion and company segment
- Account-wide conversation data across all contacts at the company
- Pain points mentioned in calls
- Features discussed and feedback shared
- Competitor mentions
- Multi-threading opportunities

From one email address, the Function now has product usage data, CRM data, call transcripts, and competitive intelligence.

## 🧠 Step Three: Analysis

The Function takes all that data and makes sense of it.

A **Persona Analysis** step uses Claude to determine the prospect's persona: Sales, Marketing, Operations, RevOps, Growth, Executive, and so on. It identifies their seniority level, pain points, and the best messaging approach.

A **Context Summary** step creates a four to six sentence brief for the SDR. This prioritizes the strongest personalization angle, references conversation context, surfaces likely objections, and flags multi-threading opportunities.

## ✍️ Step Four: Message Generation

The Function generates three message variants.

**An Insight-Led Message.** Three to four sentences. Opens with a specific, personalized insight about the prospect, ties it to a relevant Clay capability, and ends with a soft conversational CTA.

**A Value Nugget Message.** Leads with a concrete, tactical insight and focuses on immediate value delivery.

**A High-Signal Message.** Two to three sentences. Leads with the highest-value qualifying signal: a job change, previous Clay experience, a competitor mention, a pain point from a recorded call, or recent product engagement. If none exist, it returns "NO HIGH SIGNAL - USE STANDARD MESSAGES."

## 📤 Step Five: Output

The "Send data back" action writes all three messages back to the original table as a JSON object. The SDR picks the variant that fits the situation, or uses an agent to make that choice and route the message to a Slack channel or directly into a sequencer.

One email address in, three personalized messages out.

## 🔮 What's Next

We've gone from enrichment Functions that pull data in, to a copywriting Function that writes targeted emails using product usage data and conversation history at scale.

In the next lesson, we'll cover signal detection and lead qualification.

Next up