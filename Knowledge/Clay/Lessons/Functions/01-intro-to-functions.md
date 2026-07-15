---
title: "Introduction to Functions [Functions]"
source: "https://university.clay.com/lessons/introduction-to-functions"
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

![](https://www.youtube.com/watch?v=XrP6tASu2Bo)

About this lesson

00:00

## Introduction to Functions

This course covers Clay functions—what they are, how to build them, and how to create multiple working functions you can call from any table in your workspace.

## 😤 The Problem

You've probably rebuilt the same Clay table more than once—the same data sources, lookups, and logic—either rebuilding from memory or copying columns from an old table.

Worse, when you have the same workflow across ten different tables and need to update one provider in an email waterfall, you must go back to each individual table and make the change. That's the problem functions solve.

## 🔧 What Is a Function?

A function is a reusable workflow built from any set of columns in Clay. Define it once, set the inputs (domain, enrichments, etc.), define the outputs, and save it. From that point on, anyone in your workspace can call the function into their table.

Think of it like a recipe in a restaurant's kitchen. The head chef writes the recipe once, and every line cook follows it. If the chef switches from mangoes to papayas, the line cooks automatically make those changes too.

### How Functions Work Behind the Scenes

Your function spins up its own mini table running in the background, does all the work there, and pipes the results back into your main table. Your main table stays clean and organized, returning one column instead of fifteen.

Functions live in the left-hand sidebar of your Clay homepage, along with your tables and Clayents.

## 🆚 How Functions Differ from Templates

Templates are reusable—you build once and copy. But once pasted into a new table, it's its own thing. To update logic or swap a data provider, you must find every table using that template and manually make the change.

### The Lead Scoring Example

Imagine the same lead scoring workflow copied across 20 tables. Your ICP shifts, and you need to score company headcount differently. You must open every table, find the right column, and update the formula—taking days or weeks, and you'll still miss some tables.

### The Functions Advantage

With functions, you call rather than copy. One version of the logic lives in one place. When you update it, every table calling that function gets the updated version automatically.

- **Templates** add columns directly to a table
- **Functions** run outside your table and return a single column, keeping complexity in the background

## ✅ When to Use Functions

Four clear signals indicate when functions are the right tool:

### 1\. Repeated Enrichment Logic

When you're running the same enrichment logic across more than one table. If you've built it more than once, turn it into a function.

### 2\. Column Limit Constraints

When approaching column limits on heavy enrichment tables. Functions move complexity out of the table entirely, returning one simple column.

### 3\. Empowering Non-Technical Teammates

When you want non-technical teammates to run complex workflows without building from scratch. Build once, and anyone in the shared workspace can call that function without being in the weeds.

### 4\. Governance and Consistency

When you need every team using the same qualification logic and enrichment criteria. Functions enforce one source of truth, preventing situations where the SDR team scores leads one way, AEs score differently, and the partnership team uses a third version.

## 🚀 What's Next

Functions are available on all paid Clay plans at no additional cost.

In the next lesson, you'll build your first function end to end.

Next up