---
title: "Build, Scale, and Deploy Claygents with Claygent Builder [AI-Powered GTM Automation]"
source: "https://university.clay.com/lessons/build-scale-and-deploy-claygents-with-claygent-builder"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=xY4UVSVYshk)

About this lesson

00:00

## Build, Scale, and Deploy Claygents with Claygent Builder

Clay's philosophy: use the best tool for the job — *even if that tool isn't Clay.*

In the past, we’d hop into ChatGPT or Claude mid-tutorial to iterate on prompts, then bring them back into Clay. Many people still do this, but **Claygent Builder** brings that entire iteration loop inside Clay with access to different models, free testing, and centralized deployment.

This lesson covers what Claygent Builder is and how to use it.

## 🧠 What Are Claygents?

Claygents are Clay's AI agents designed for judgment-based, nondeterministic work in your GTM stack — work that doesn't fit into formulas or waterfall enrichment.

Four main use cases:

- **Account research**
- **Account scoring**
- **Lead scoring**
- **Outbound copywriting**

We'll walk through lead scoring and outbound copywriting to demonstrate Builder's flexibility.

## 🚪 Getting to Claygent Builder

Click **Agents** in the left-hand navigation bar.

Three ways to start building:

- **From scratch** — blank canvas with text editor and Sculptor
- **With Sculptor** — describe what you want in plain language and Sculptor drafts the agent (fastest path)
- **From a template** — pre-built starting points for prospecting, scoring, and copywriting

We'll use Sculptor for both demos.

## 📊 Demo 1: Building a Lead Scoring Claygent

Click into Sculptor and type:

*"Build an agent that scores a lead against our ICP and outputs a score from 1 to 100 with a short rationale explaining the score."*

Hit build agent. Sculptor will:

- Define the prompt
- Set up variables (company name, contact title, industry)
- Format the output as score plus reasoning
- Create test cases

Run a test case and watch the Claygent stream its reasoning live.

### 🆓 Free Testing Without Burning Credits

Test runs inside Claygent Builder are free. Iterate as much as you want before spending credits.

To adjust weighting, tell Sculptor directly:

*"Adjust the scoring so company fit is weighted at 60% and persona fit at 40%. Also break out company size as its own factor."*

Sculptor rewrites the prompt. Run the test again to see the difference.

### 🚀 Deploying Your Lead Scoring Agent

Deploy directly from Claygent Builder, or add an AI column in any table and select **Saved Claygents**.

Select your lead scoring agent. Variables automatically map to your table columns. Save and run.

## ✉️ Demo 2: Building an Outbound Copywriting Claygent

In Builder, click into Sculptor and type:

*"Build an agent that writes short, personalized cold emails to a prospect using their ICP from* [*clay.com*](http://clay.com/)*."*

Hit build agent. Preview what an email will look like before generating anything. Testing is free.

### 📋 Understanding Business Context

The agent pulls information from **Business Context** — your company description, ICP, and buyer personas.

Clay auto-populates this from your workspace settings. If you haven't filled it in, go to Settings, enter your domain, and Clay will research for you.

Configuration options include:

- Let the agent find contacts and jobs
- Access full business context
- Attach documents like tone guides or example emails
- Connect existing MCP servers

### 📤 Deploying Your Email Writer

Save it, add an AI column in your table, and select the email writer from Claygent options.

Variables map automatically. Click Save and run.

Results stream back as personalized emails. To test different voices, change the model in Builder, rerun, and compare.

## 🎛️ Centralized Management: The Real Power

From Builder home, you can see every table where each agent is running.

If your ICP shifts and you need to re-weight your lead scoring formula, managing prompts column by column across tables would take hours and you'd miss some. **With Builder, change it once and it propagates everywhere.**