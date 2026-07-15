---
title: "Transform with AI Formulas (and Optimize Credits) [AI-Powered GTM Automation]"
source: "https://university.clay.com/lessons/transform-with-ai-formulas-and-optimize-credits"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=zk8fcnt-DIs)

About this lesson

00:00

## Transform with AI Formulas (and Optimize Credits)

In the last lesson, we talked about the two ways you can use AI to transform data: deterministic and generative. Now we're going to focus on the first one: **deterministic transformations** using **AI Formulas** in Clay.

These are perfect for data cleanups, text extraction, and other repeatable operations where you want consistent, rule-based output.

## 🧮 When to Use AI Formulas

Anytime you're manipulating or calculating existing data in a structured way like:

- Totals
- Patterns
- Extractions
- Cleanups

You should use **AI Formulas**.

## 🔍 Ideal Use Cases for Deterministic Tasks

These are ideal for deterministic tasks when:

- You know exactly what kind of result you want
- You're applying the same logic to every row
- You don't need the AI to make a judgment call

Here are a few classic examples. You want to:

- Extract all the companies someone has worked at into a **comma-separated list**
- Calculate the **total years of work experience** someone has
- Get the **tenure in their last role**, expressed in years and months

This kind of transformation would normally take a bunch of custom formulas or scripting. AI Formulas make it simple.

## 🛠️ Step-by-Step Implementation

Let's walk through how to extract a CSV list of companies from someone's work experience using AI Formulas:

1. **Start with data from social media**
	- Begin with a table containing social media domains
		- Use the Enrich Person feature to get detailed profile information, including work experience
2. **Access Experience Data**
	- Open cell details for any person
		- Scroll down to the "Experience" section
		- You'll see a list of all the companies they've worked for and roles they've held
3. **Create the AI Formula**
	- From the Experiences list, you can click "Take action on list" and then select "Formula" to open the AI Formula builder
4. **Write the Formula**
	- Enter a prompt like this: "Create a CSV of companies worked at, with these rules:
		- Include company names only
				- Exclude job titles and other details
				- Skip placeholder companies (like “stealth'” or “new company”)
				- Remove any duplicates"
5. **Review and Apply**
	- Generate the formula
		- Check the output
		- If it looks correct, accept and apply to all rows

## 📝 Additional Use Cases for AI Formulas

That's one simple use case for AI Formulas. You can also use it for:

- Formatting dates or numbers
- Extracting text patterns (like pulling a domain from an email)
- Cleaning up inconsistent inputs like job titles or locations
- Doing math, like adding up years of experience or calculating tenure

If it's structured and consistent, AI Formulas are your best bet.

## ⚡ Why AI Formulas Optimize Your Credits

AI Formulas are particularly valuable because they:

1. Don't consume Clay credits; they're free to use
2. Process faster than API-based enrichments
3. Maintain consistent output formats
4. Can be reused across multiple tables and workflows

By using AI Formulas for deterministic tasks instead of credit-consuming enrichments, you can reserve your credits for more complex operations that truly require generative AI.

## 🔮 What's Coming Next

In the next lesson, we'll cover the other side of the Transform equation. We’ll use **generative AI** to take messy or unstructured inputs and turn them into clean categories or classifications.

The combination of deterministic transformations (AI Formulas) and generative transformations gives you a complete toolkit for preparing your data for the final step in the FETC framework: Create.

Next up