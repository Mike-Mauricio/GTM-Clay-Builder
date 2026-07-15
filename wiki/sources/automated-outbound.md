---
title: "Automated Outbound"
type: source
created: 2026-07-14
updated: 2026-07-14
sources: ["https://university.clay.com"]
tags: [clay-academy, outbound, sequencing, personalization, video]
---

# Automated Outbound

**Source:** Clay University (university.clay.com)
**Type:** Video course (15 lessons)
**Level:** Intermediate/Advanced — end-to-end outbound automation
**Location:** `Knowledge/Clay/Lessons/Automated-Outbound/`

## Overview

Clay's outbound automation course covering the complete pipeline from enrichment through message delivery. Heavy on activation tools — introduces Clay's native sequencer, external sequencer integrations (SmartLead, Instantly, La Growth Machine), and AI video generation (SendSpark, Tavus).

Significant overlap with prior courses — 7 of 15 lessons are full recaps of content from [[clay-101-gtm-automation|Clay 101]], [[limitless-research|Limitless Research]], or [[ai-powered-gtm-automation|AI-Powered GTM]]. The 4 genuinely new lessons cover activation and delivery tools not previously documented.

## Lesson Index

| # | Lesson | Focus | Net New? | Key Concepts |
|---|--------|-------|----------|-------------|
| 01 | Intro to Personalized Outreach | Strategy | Recap | ICP refinement, TAM/SAM/SOM narrowing, 5-step framework |
| 02 | Enrich Companies (Waterfalls) | Enrich | Recap | Specific provider chain: Intellizence→Dealroom→Harmonic→Owler→Pitchbook |
| 03 | Enrich People (Waterfalls) | Enrich | Recap | ZeroBounce defaults, catch-all behavior detail |
| 04 | AI Formulas + Conditional Runs | Transform | Recap | Waterfalls are conditional runs under the hood |
| 05 | Data Cleaning + Normalization | Transform | Recap | Normalization tools walkthrough |
| 06 | Claygent: AI Web Scraper | Enrich | Recap | Model selection review |
| 07 | 11 Claygent Prompts | Enrich | Partial | Prompt patterns: Glassdoor, B2B/B2C, job listing goals, Predict Leads |
| 08 | 24 Prompt Templates | Reference | Partial | Three-pillar framework (summarize/extract/copywrite), Gong/Fathom mention |
| 09 | Intro to AI Snippets | Create | Partial | Chain-of-context construction, subject line rules (<8 words, 2nd person) |
| 10 | Push to Email Sequencer | Export | Partial | Multi-step variable naming, validated email tip, sequencer list |
| 11 | SmartLead Walkthrough | Export | Partial | SmartLead {{variable}} syntax, inbox rotation, "don't import leads" workflow |
| 12 | La Growth Machine | Export | Yes | [[la-growth-machine]] — omnichannel sequencing (email + Twitter) |
| 13 | Clay Sequencer | Export | Yes | [[clay-sequencer]] — native sequencer, Clean Variables, Spintax, reply management |
| 14 | SendSpark Video | Create | Yes | [[sendspark]] — AI personalized video generation |
| 15 | Tavus Video | Create | Yes | [[tavus]] — AI video replicas with deepfake-style personalization |

## Key Takeaways

1. **Clay now has a native sequencer.** The [[clay-sequencer]] eliminates the need to export to external tools — build, send, and manage replies all within Clay.
2. **Clean Variables provide safe fallbacks.** When personalization data is missing, Clean Variables substitute default text instead of sending broken merge tags.
3. **Spintax rotates phrases for deliverability.** "Hi/Hello/Hey" rotation helps avoid spam filters at scale.
4. **Reply management with AI + human approval.** AI auto-generates reply drafts, Slack approvals let humans review before sending — human-in-the-loop at the reply stage.
5. **Video outreach via SendSpark and Tavus.** Two integration paths: SendSpark for quick personalized videos, Tavus for AI replica deepfake-style videos.
6. **La Growth Machine enables omnichannel.** Email + Twitter + other platforms in one sequence — but only for high-value prospects due to social platform limits.
7. **Supported sequencers:** Clay Sequencer (native), Instantly, SmartLead, Outreach.io, SalesLoft, LemList, La Growth Machine.

## Cross-References

- New tools: [[clay-sequencer]], [[la-growth-machine]], [[sendspark]], [[tavus]]
- Updated: [[personalized-outbound-pipeline]] (sequencer options, video outreach), [[ai-snippets]] (construction sequence detail)
- Builds on: [[clay-101-gtm-automation]], [[ai-powered-gtm-automation]]
- Related: [[ai-snippets]], [[twain]], [[fetc-framework]], [[prompt-engineering-at-scale]]
