---
title: "Calling Functions for Reps [Clay MCP for Reps]"
source: "https://university.clay.com/lessons/calling-functions-for-reps"
author:
published:
created: 2026-07-14
description:
tags:
  - "clippings"
---
##### Clay MCP for Reps

Learn how to use Clay directly inside of AI chat tools like ChatGPT, Claude, and more to find contacts, research accounts, prep for meetings, and run full prospecting workflows without switching tools.

Progress

![](https://www.youtube.com/watch?v=USR7mmZyPF0)

About this lesson

00:00

## Calling Functions for Reps

This lesson covers what a Function is, the two kinds you'll run into, and how to call one just by asking.

## 🧩 What a Function Is

Think of a Function as a **saved, reusable action**. Someone on your team sets it up once, and then you can run it as many times as you want just by asking for it in natural language. You give it an input, like a company name or a contact, it does the work, and it hands you back the result right in the chat.

Here's why that matters: What might take **26 columns inside a Clay table** gets condensed into a **single column or workflow** that codifies the exact enrichments you use. **Many steps in, one clean result out.** You don't have to memorize any of the particulars; you just need to know how to call it from your chat tool.

## 🔧 Two Kinds of Functions

There are two kinds, and the difference is who builds them and what they're allowed to do.

|  | Managed Functions | Custom Functions |
| --- | --- | --- |
| Who builds them | Clay, out of the box | Your ops team, for your team |
| What they cover | Everyday data you reach for (work email, job openings, company industry, employee count, funding, location, web traffic) | Your company’s own logic and rules |
| Write back to your systems | No | Yes, like adding a contact to Salesforce |
| How you call them | Just ask; Clay picks the right one behind the scenes | By name; your ops team tells you what it’s called |
| Setup | None | Published by your ops team |

**Managed Functions** are Clay's out-of-the-box library. Clay builds them, Clay keeps them updated, and they cover the common data a rep reaches for. When you ask for something common, Clay just reaches for the right one. These are new, so if your team doesn't see them yet, they'll be in all workspaces soon.

**Custom Functions** are the ones your ops team builds for your team specifically. They hold your company's logic and rules, especially anything that writes back to your systems, and you call them by name. The building side lives in the [Functions course](https://university.clay.com/courses/functions) in Clay University, but as a rep you never have to go into Clay to see any of this. **Everything you're looking at, you can call from your chat tool in plain language.**

## 🧪 Calling a Managed Function

Let's call a managed Function. Say you want to know what a company is hiring for right now:

> "Get the current job openings at Stripe."

Clay picks the right managed Function (here, **company job openings**) and returns the roles, in this demo **296 open roles** for Stripe, rendered in the widget as they resolve. You didn't name a Function and you didn't set anything up. You just asked.

A note on being specific: you *can* name the Function to force it (for example, "use the company job openings managed Function"), which is handy when you want to be sure for a demo. **But you shouldn't have to.** Natural language should invoke the right Function on its own.

Let's do one more. Say you want to reach the product leaders at an account and need their work emails:

> "Find me 3 product leaders at Stripe who are VP level or above and find their work email using a managed Function."

Clay filters to three leaders and runs the **find work email** managed Function on them, returning verified emails right in the widget. From there you can add more enrichments straight from the widget if you want. This is the same work-email Function that ran when you enriched contacts last lesson, now on its own.

## 🧱 Custom Functions

The other kind is a Custom Function, one your ops team built. These are the ones that touch your systems, like adding a contact to your CRM. You call it by name, and your team's own logic and rules run from the same chat window: the right fields, the right destination, the way your team wants it done every time. Your ops team publishes these and tells you what they're called, so all you have to do is ask.

## 🚀 What's Next

You don't build Functions, and you don't need to know how they work under the hood. **You just need to know they're there, and that you call them by asking.** Managed Functions cover the common data automatically; Custom Functions run your team's own plays. Either way, you never leave the conversation.

Next, we take everything you've researched, found, and enriched, and turn it into outreach you can actually send.

Next up