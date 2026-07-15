---
title: "Lead Scoring for Inbound [Automated Inbound]"
source: "https://university.clay.com/lessons/lead-scoring-inbound-automation"
author:
published:
created: 2026-07-14
description:
tags:
  - "clippings"
---
##### Automated Inbound

Learn how to automatically enrich, score, and follow-up with inbound leads with Clay's inbound automation engine for lightning-fast speed-to-lead.

Progress

![](https://www.youtube.com/watch?v=c8X9b_RnRYs)

About this lesson

00:00

## Lead Scoring for Inbound

## 💯 Intelligent Lead Scoring: Prioritizing Your Best Prospects

Welcome to lesson five of Inbound Automation! In previous lessons, you learned how to import inbound lead data, enrich it, as well as clean and transform it.

Now, we're going to put all that enrichment data to use with lead scoring.

Lead scoring assigns a numerical value to every lead, indicating their likelihood of converting and becoming a customer. It eliminates the guesswork for your reps, pushing the most promising, high-value prospects to the surface. Making sure you get to these top sales qualified leads (SQLs) as soon as possible requires efficient, accurate scoring. Having a system with room for flexibility is also key - every company has different, ever-changing criteria to determine what makes a lead a quality lead for them.

We'll walk through how to use Clay to build a complete lead scoring model that combines native functions with the flexibility of AI to help you prioritize your inbound leads and focus your sales efforts, minimizing speed to lead especially for those high-priority prospects.

## 🏁 Introduction to Lead Scoring in Clay

Before we dive into building our own scoring logic, it's worth noting that Clay has a native lead scoring capability, which can automatically generate scores from factors like company headcount, seniority, etc.

You can find this in Add Enrichment → Score Row in Clay. From there, you can set the number of scoring criteria up to a max of 15, the factors you want to score, comparison type, keywords if applicable, and the numerical scores you want to assign. Clay will then automatically generate a numerical score, as well as reasoning for the score.

For this lesson, we'll focus on building custom scoring logic since it's a great application of using AI formulas. Lead scoring can be a pretty unstandardized, imprecise practice but Clay allows you to score accurately and efficiently based on custom criteria, enabling easy, clean prioritization.

## 👵🏻 Seniority scoring

You might want to score more senior individuals at a company higher to reflect their decision-making power as buyers.

For this example, we’re going to dive into the AI formula approach since it showcases just how much control you can have:

- Add a new formula column
- Describe the formula you want. In our case, we can say something like:
	- "Based on this person's job title (map the job title column here), assign a seniority score from 1-10. Consider: C-level executives (9-10), VPs and Directors (7-8), Managers (5-6), Individual contributors (3-4), Interns/Entry-level (1-2).
- Then click Generate.

If there are some edge cases like Growth Hacker that might not fit well into standard seniority keyword matching, you can additionally leverage AI to address those edge cases and find more accurate data without unnecessarily blowing through credits.

## 👩🏻💻Tech stack

A company’s tech stack can be a powerful indicator of whether they’re a good fit customer. For example, let’s say they use a CRM or data tool that your software integrates with or complements. Alternatively, it’s possible that your team has had a lot of success driving customers off certain legacy platforms into using your tool. Or, maybe you’ve noticed that most of your existing customers tend to have a more mature or complex stack with lots of different tools in a specific category.

Here's how to set that last example up:

- Click Add Column and choose Formula.
- Describe the formula you want. In our case, we can use this:
	- Assign a company score based on tech stack:
		- Score 10 if number of data tools is more than 5
				- Score 5 if number of data tools is between 3 and 5
				- Otherwise, score 2
- Then click “Generate” and let Clay create the formula for you.

## 🏭 Advanced example: Industry scoring

You might want to prioritize leads from certain industries based on their fit with your product or service.

This is actually part of the workflow Anthropic used, which helped them 3x their enrichment coverage.

Most companies rely on generic industry filters, which often miss the mark. Standard industry categories, like those on Linkedin, are unreliable and overly broad. For example, Ulta Beauty and Nike are both broadly categorized as “Retail,” rather than cosmetics and apparel. Adding to the confusion, different data providers use inconsistent terminology like IT, Software, or Internet technology for the same sectors.

To tackle this headache, Anthropic implemented Claude within Clay to accurately categorize prospects into their own custom industry list. The result is an automated industry classification system that continuously keeps their data organized and up to date.

Let’s walk through how to set this up:

- Add a new column and select "Use formula"
- Type in a prompt like:
	- You will be provided with an industry value. Map this value to the list of industries below in \<List of Industries>\</List of Industries> tags, and select the best match from the available list. Only return values from the list and do not generate any new ones. If you are unable to find a reasonable match, select “Other”.Some example classifications include: \[LIST OF EXAMPLE CLASSIFICATIONS\]Return only the matching value, with no other words, explanation, or information. Do not include \<List of Industries> tags in your response.
- Then click Generate to create your prompt
![](https://cdn.prod.website-files.com/687e604972375496b891fe58/691f5d330541aaa02cf6b0c7_689124cb35429fc1bac69c10_industries.png)

Industry Scoring Prompt Example

## 💡Lead Scoring: Best Practices

Building scoring models is about knowing when to use deterministic logic and when to layer on AI.

The best practice is to start with a small batch of 10-20 rows using a native function.

If it handles 80% of your cases accurately, you might add an AI transformation as a fallback for the remaining 20%, using a conditional formula to make sure it only runs for those edge cases. This lets you find the optimal balance between speed, cost, and accuracy.

The goal isn't perfection on the first try; it's continuous improvement and iteration to unlock your GTM alpha.

We know AI formulas can be a bit finicky. If your AI formula isn't producing the right output, try clicking the red "Output is Wrong" button in the formula generator. This drops you into a helpful flow to iterate on your prompts and refine your logic.

If you still aren’t getting the results you're looking for, remember that all AI formulas are doing is generating code automatically that runs in your column. So if the code isn't working, copy-paste that AI formula code into Claude or another AI assistant and tell it exactly what outputs you're getting versus what you want. Ask it why the code might not be working - this often reveals logic issues you can fix quickly.

## ✅ That’s a wrap!

You now know how to leverage Clay’s built-in scoring tools as well as AI formulas and transformations to score accurately and efficiently.

This scored data sets the stage of what comes next: effective lead routing to the right people in your sales org, allowing for quicker, smoother, and highly personalized outreach.

In our next lesson, we’ll go over lead routing to make sure your best-fit leads get instantly surfaced to the right reps with all the right context.

Next up