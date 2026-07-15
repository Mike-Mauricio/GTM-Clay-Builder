---
title: Personalized Outbound Pipeline
type: pattern
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]", "[[automated-outbound]]"]
tags: [pattern, outbound, personalization, ai-snippets, create-step, sequencing, video]
---

# Personalized Outbound Pipeline

An end-to-end pattern for generating AI-personalized outbound messages using the [[ai-snippets]] approach. Follows [[fetc-framework|FETC]] — enriched data flows through modular content generation into assembled, ready-to-send messages.

## Architecture

```
Deep Enrichment → AI Snippet Generation → Formula Assembly → Review → Export
```

### Step 1: Deep Enrichment
Build a rich prospect profile beyond standard firmographics:

| Data Type | Source |
|-----------|--------|
| Social profiles | [[clay-find-people]] enrichment |
| Recent activity | [[claygent]] (LinkedIn posts, blog content) |
| Company signals | [[waterfall-enrichment]] (funding, hiring, tech stack) |
| Custom research | [[claygent]] or [[perplexity-enrichment]] |
| Financial data | [[oakie-ai]] (for public companies) |

The depth of enrichment directly determines personalization quality. Weak enrichment = generic snippets.

### Step 2: Transform for Personalization
Use [[ai-formulas]] (free) to derive personalization signals:
- Calculate tenure, experience metrics
- Create qualification flags
- Identify strongest personalization angle per prospect
- Classify persona type for tone adjustment

### Step 3: Generate AI Snippets
Create separate AI columns for each message component:

| Snippet | Prompt Focus | Tone Adjustment |
|---------|-------------|----------------|
| Subject line | Trigger/signal that explains "why now" | Short, curiosity-driven |
| Intro line | Personalized observation about the prospect | Varies by persona (VP vs. IC) |
| Body | Value proposition tied to their specific pain | Professional, benefit-focused |
| PS line | Personal touch (shared interest, congrats, cultural reference) | Casual, human |

Each snippet is generated independently — different prompts, potentially different AI models.

### Step 4: Assemble via Formula
A formula column concatenates snippets into the final message:

```
Subject: {subject_snippet}

{intro_snippet}

{body_snippet}

{cta}

{ps_snippet}
```

### Step 5: Review and Deliver
- Review assembled messages for quality (spot-check 10-20)
- Deliver via one of the sequencing/activation options below

## Delivery Options

| Tool | Type | Best For |
|------|------|----------|
| [[clay-sequencer]] | Native email sequencer | End-to-end in Clay — send, track, manage replies |
| [[twain]] | AI sequence generation | Full multi-step sequences in one pass |
| Instantly / SmartLead | External email sequencers | Advanced deliverability features, inbox rotation |
| [[la-growth-machine]] | Omnichannel sequencer | Email + Twitter + LinkedIn in one sequence |
| [[sendspark]] | AI video generation | Personalized video links embedded in emails |
| [[tavus]] | AI video replicas | Deepfake-style video where "you" speak to each prospect |

**Supported external sequencers:** Instantly, SmartLead, Outreach.io, SalesLoft, LemList.

### Multi-Step Variable Convention
When pushing to external sequencers, use per-step variable names:
- Step 1: `subject_line_one`, `email_body_one`
- Step 2: `subject_line_two`, `email_body_two`
- Use the "validated work email" column (not generic "email") as the email input.

## Content Generation Approaches Compared

| Approach | Method | Best For |
|----------|--------|----------|
| [[ai-snippets]] | Generate each component separately, assemble | High-touch accounts, maximum control |
| [[twain]] | Generate full sequence in one pass | Scale outbound, consistent structure |
| [[sendspark]] / [[tavus]] | Generate personalized video | Differentiation, high-value accounts |

You can also hybrid: use Twain for the initial sequence structure, then replace individual components with custom AI Snippets where more personalization is needed. Add video links from SendSpark or Tavus as a differentiator.

## See Also

- [[ai-snippets]] — the core content generation approach
- [[twain]] — alternative full-sequence generation
- [[clay-sequencer]] — native delivery tool
- [[la-growth-machine]] — omnichannel delivery
- [[sendspark]] — AI video outreach
- [[tavus]] — AI video replicas
- [[fetc-framework]] — this pipeline implements the Create step
- [[experiment-before-scale]] — test snippets on 10 rows before scaling
- [[people-enrichment-pipeline]] — prerequisite: enrich contacts first
