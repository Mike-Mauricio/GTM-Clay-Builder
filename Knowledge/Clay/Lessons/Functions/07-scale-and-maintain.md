---
title: "Scale and Maintain Your Function Library [Functions]"
source: "https://university.clay.com/lessons/scale-and-maintain-your-function-library"
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

![](https://www.youtube.com/watch?v=e_pSfRvtRtk)

About this lesson

00:00

## Scale and Maintain Your Function Library

Once your team starts using functions, your library will grow quickly. With 20, 30, 40 functions and no naming system or credit tracking, that library will work against you.

## 🔧 The Workshop Analogy

Think of your function library like a workshop.

With just a hammer and screwdriver, you can toss them anywhere and still find what you need. Once you've got tools scattered on the floor with no labels, you'll waste 10 minutes hunting for a socket wrench.

You don't need anything fancy—just a simple toolbox or pegboard with labeled hooks. Same goes for functions: you just need a bit of organization.

This lesson covers three parts:

1. Your naming system
2. Credit visibility
3. Scaling past limits

## 📝 The Naming System

Name your Functions so a stranger knows what they do. Here's the specific format:

**“Workflow type + outputs + version”**

For example:

`Contact Enrichment: Email Plus Phone V1`

This tells you what it does, what it returns, and its version. This makes alphabetical sorting useful—all contact Functions group together, all account Functions group together.

**For teams with more than ten Functions, create a simple internal catalog.** A shared doc listing each Function, what it takes in, what it returns, who owns it, and what it costs per row.

## 💳 Credit Visibility

The credit cost breakdown doesn't show up in the calling table—it lives on the function view itself. When a teammate adds a run function column, they won't see the per-step costs.

If your contact enrichment function costs four credits per row and someone runs it across a 10,000-row list without knowing, that's an expensive surprise.

Include credit costs in your catalog. It's a two-minute task that prevents bad days.

## 📈 Scaling Past Limits

Functions clean up your table by returning one column instead of 15, which solves column limits.

**Complex enrichment workflows burn through columns fast, but all that logic lives inside a function running in the background, and none of those columns count against your table.** You can keep adding providers and scoring dimensions without your main table getting wider.

**The old 50,000-row limit is also gone.** Functions now work at scale through pass-through with no row cap. Enterprise teams can run enrichments across entire databases through a single function column.

## 🚀 What's Next

You've got an organized library and the scaling infrastructure to handle large data sets.

Next, we'll put this into practice with three real-world use cases.

Next up