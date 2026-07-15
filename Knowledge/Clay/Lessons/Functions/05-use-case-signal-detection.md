---
title: "Use Case: Signal Detection & Lead Qualification [Functions]"
source: "https://university.clay.com/lessons/use-case-signal-detection-lead-qualification"
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

![](https://www.youtube.com/watch?v=rnaj6sAZnX0)

About this lesson

00:00

## Use Case: Signal Detection & Lead Qualification

Beyond enrichment and copywriting, Functions excel at identifying and acting on buying signals.

Teams build Functions for job change detection, job anniversaries, headcount growth, hiring location monitoring, and ICP qualification. Some run large fleets of signal agents as Functions.

Functions ensure consistency. When SDR and marketing teams use different detection methods, they get different results for the same contacts. A Function standardizes detection logic across your organization.

## 📋 The Use Case: Job Change Detection

This Function answers: is this person still working at the target company—at scale?

## 🔢 The Inputs

The Function requires a contact's full name, first name, last name, and account name (the target company you're checking their relationship with).

## 📊 Step Two: Enrich LinkedIn Data

We pull complete profile information from that LinkedIn URL: job history, current position, and education.

## 🧠 Step Three: Analyze Employment Status

An AI step with web research capabilities analyzes the enriched data and determines:

- Are they still employed at the target company?
- What's their current job title?
- What's their current company?
- If they left, when did they leave?
- What's their current relationship to the target company?

The relationship context matters—someone might have joined a partner organization or moved to a subsidiary, helping your team decide how to handle the contact.

## 🌊 Step Four: Backup Waterfalls

Backup waterfalls activate when the LinkedIn lookup fails:

**Domain Waterfall** tries three methods to find the company's website: Claygent, HG Insights, Google.

**Work Email Waterfall** runs eleven providers: LeadMagic, Findymail, Prospeo, Dropcontact, Hunter, Datagma, Wiza, PDL, Enrow, FullEnrich, BetterContact. If one finds the email, we work backwards to the LinkedIn profile.

**LinkedIn Profile Waterfall** tries twelve methods to find a LinkedIn URL from the email: LiveData, PDL, Clay enrichment, Reverse Contact, and more.

These waterfalls provide high coverage across thousands of contacts.

## ↩️ Step Five: Send Results Back

The Function packages all findings and writes them back to the original table.

Add one column, pass in a name and company, and receive a full employment status check with backup enrichment built in. Your team gets the answer without needing to understand the underlying waterfalls.

## 🚀 What's Next

We've covered three Function categories: Enrichment Functions that pull data in, a copywriting Function that takes action on data, and a signal detection Function that identifies triggers across your contact list.

In the next lesson, we'll wrap up the course and tie everything together.

Next up