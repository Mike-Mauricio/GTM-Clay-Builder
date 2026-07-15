---
title: "Roll Functions Out Across Your Team [Functions]"
source: "https://university.clay.com/lessons/roll-functions-out-across-your-team"
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

![](https://www.youtube.com/watch?v=UAToPHO3EP8)

About this lesson

00:00

## Roll Functions Out Across Your Team

In the last lesson, you built your first function end to end. You took a workflow, saved it as a function, and called it from a new table.

But right now, that function only helps you. This lesson covers how to roll functions out across your entire team so everyone's running the same logic, nobody's rebuilding from scratch, and you can control what's happening in your workspace.

## 🏈 The Playbook

Think of your org using functions like a football playbook versus one player's notes. Your notes help you remember your job on a given play. The playbook belongs to the whole team. When you have the playbook, everyone lines up the same way and runs the same play. When the coach changes the playbook, the whole team runs the updated version.

Functions are playbooks that help the whole org, not just you.

## 🏢 Functions Belong to the Workspace, Not Just You

When you save a function, it lives at the workspace level. Every person on your team can call it from any table they're working on.

That goes for:

- Your account scoring model
- Your enrichment waterfall
- Your ICP qualification logic

All of that becomes shared infrastructure instead of living privately in someone else's table.

## 👥 Enabling Teammates Who Aren't Clay Power Users

This enables teammates who might not be Clay power users. Most teams have this problem: the best enrichment logic lives inside one person's head, buried in a table that only they understand.

When that person is out of office or moves to a different role, nobody knows how to replicate what they've built. Everyone rebuilds from scratch or pings around asking for help in Slack.

Functions flip that. The ops person becomes the architect. Sales reps, marketing coordinators, SDRs—they become the callers who bring the function into their own Clay tables. They don't need to know how the waterfall works or which data providers are being queried. They add one column, map their inputs, and get clean, structured data back.

Not everyone is going to want to become a power user, and that's okay. You're asking them to add one column—the complexity is hidden inside the function.

Onboarding gets faster too. Instead of walking a new teammate through building an entire enrichment sequence from scratch, you point them to the function library, they add the column, map their inputs, and they're done.

## 💳 Building Compliance and Cost Controls Into Functions

Here's a question that comes up all the time: credits. What happens when someone accidentally runs an expensive enrichment on 1,000 rows and burns through all your credits?

Functions can handle governance. Two patterns to build from the start:

### Pattern 1: Conditional Enrichment Using a Checkbox Input

Phone number lookups cost more credits than email lookups. Build a function where phone enrichment only runs when a checkbox is set to true. The person calling the function has to explicitly opt in. They can't accidentally trigger it on 1,000 rows.

You've applied best practices and protected your team's credit budget without policing it manually.

### Pattern 2: Compliance Gating

If your team operates in regions with enrichment restrictions like GDPR, add a conditional logic step that checks the contact's region before enrichment runs and stops the workflow if it hits restricted geography.

Because that check lives inside the function, it runs every time for every person who calls it. Nobody can skip it.

Both patterns you set once inside the function, then they apply everywhere it's called.

## 📚 Setting Up a Function Library Your Team Will Actually Use

A few practical things to help you roll out functions effectively:

### Name Your Functions Clearly

Name your functions so a stranger knows what they do. Include what the function takes in and what it outputs.

For example, "Account Scoring: ICP Fit + Segment Tag"—useful. "Enrichment V2\_final\_final"—not useful.

You don't want a function library that looks like a folder of unnamed, unwanted tables.

### Document Your Inputs

When you define the input fields inside a function, those labels are the only instructions someone has when they call your function months later. Make them obvious.

### Start with Your Top 3-5 Workflows

Start with your top three to five workflows that your team rebuilds most. Convert those first, get them working, and let the library grow from there.

## 🚀 What's Next

In the next lesson, we'll work on scaling functions to high volume workflows and keeping them maintained as your use cases grow.

Next up