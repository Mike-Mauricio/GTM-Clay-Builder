---
title: "Build Your First Function [Functions]"
source: "https://university.clay.com/lessons/build-your-first-function"
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

![](https://www.youtube.com/watch?v=B5el-eGMz8E)

About this lesson

00:00

## Build Your First Function

By the end of this lesson, you'll be able to create working functions that you can call from any table in your workspace.

## 🔨 Creating the Function

We'll create a function for a simple waterfall enrichment to find a person's work email.

**First, verify that the workflow works.** Check that the waterfall is working properly before saving it as a function.

When ready to create the function:

1. **Select the columns** that will be part of the function
2. **Right-click and choose "Save as function"**
3. **Give it an easily identifiable name** - Avoid having a function library full of unnamed functions, similar to a workspace full of unnamed tables.

The function will automatically map the inputs. Select the outputs, then toggle on **replace the columns with this function**.

When selected, the columns get deleted, leaving one clean column calling the function. You can also create and open the function from the function library. Click in to pull out the validated work email, and it'll start to populate.

## 🔄 Calling a Function from Another Table

Functions can be called from different work tables. Additionally, any edits to a function propagate through all tables that reference it.

To call a function from another table:

1. Find the function you created
2. Configure the inputs, e.g. map domain, name, etc.
3. Set any conditionals on running the function
4. Click Save

The function is now running in this different table.

## ✏️ Editing a Function

Find your **function library in the left side nav** and search for your function.

**Any edits to this function propagate to all tables where it's called.**

You can:

- Delete providers
- Move around providers
- Change inputs

When you save changes, they automatically propagate to every table using that function.

## 🚀 What's Next

You now know how to build, save, and call a function. In the next lessons, we'll deploy functions across a team, scale them to high volume workflows, and maintain them as your use cases grow.

Next up