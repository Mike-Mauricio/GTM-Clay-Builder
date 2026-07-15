---
title: AI Snippets
type: concept
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]", "[[automated-outbound]]"]
tags: [concept, personalization, content-creation, outbound, create-step]
---

# AI Snippets

A modular approach to AI-generated outbound content where each message component (subject line, intro, body, PS line) is generated independently as a "snippet," then assembled into a complete message via formula columns. This gives more control than generating entire messages in one prompt.

## How It Works

1. **Enrich deeply** — Build a prospect profile with company data, social profiles, recent activity
2. **Generate snippets** — Separate AI columns produce individual content pieces:
   - Subject line snippet (references a trigger or signal)
   - Intro snippet (personalized observation about the prospect)
   - Body snippet (value proposition tied to their specific pain)
   - PS line snippet (personal touch — shared interest, language, congrats)
3. **Assemble** — A formula column concatenates snippets into the final message
4. **Adjust tone** — Each snippet can have persona-specific tone instructions (VP vs. IC, technical vs. business)

## Why Snippets Over Full-Message Generation

| Full-Message Generation | AI Snippets |
|------------------------|-------------|
| One prompt generates everything | Each component generated independently |
| Hard to control individual parts | Full control over every sentence |
| Inconsistent quality across sections | Each snippet optimized separately |
| One bad element ruins the whole message | Swap out individual snippets |
| Less transparent | Each snippet traceable to a data point |

## The Hypothesis-Driven Approach

Every snippet should reflect a **hypothesis** about why this person was selected:
- "Congrats on the new GTM hire" → hypothesis: they're scaling and need tools
- "Saw you closed Q1 with 2x pipeline growth" → hypothesis: they're hitting capacity limits
- Subject line in prospect's second language → hypothesis: personal touch increases response rate

This replaces variable-stuffing ("I see you work at {{company}}") with genuine personalization grounded in enriched data.

## Example Evolution

**Variable-stuffing (bad):**
> Hi {{first_name}}, I see you're working at {{company}} as {{title}}...

**AI Snippet (good):**
> Hi Sarah — congrats on the new VP of Ops hire. When teams scale past 50, the manual reporting processes that worked at 20 start breaking. That's exactly where we help.

The snippet version reflects enriched data (hiring signal), a hypothesis (scaling pain), and a personalized observation.

## Construction Sequence: Chain-of-Context

When building snippets, each generation receives all previously generated snippets as context to prevent repetition:

1. Generate **subject line** from thought leadership data (under 8 words, second person, reference research)
2. Generate **intro line** — feed subject line as context. Pattern: "Just read..." / "Just listened to..."
3. Generate **body** — feed subject line + intro as context
4. Generate **PS line** — feed all prior as context. Personal touches: alma mater, traditions, shared interests

The chain-of-context pattern ensures each snippet builds on the prior ones without repeating the same data points.

### Subject Line Rules
- Under 8 words
- Second person ("Your insights on..." not "Their insights on...")
- Reference specific research (blog post, podcast, award)
- No clickbait or ALL CAPS

## See Also

- [[fetc-framework]] — AI Snippets power the Create step
- [[twain]] — alternative: full sequence generation (less control, more speed)
- [[personalized-outbound-pipeline]] — implementation pattern with delivery options
- [[clay-sequencer]] — native delivery tool for snippet-powered campaigns
- [[claygent]] — often used to generate enrichment data that feeds snippets
