---
title: Signal-Based Prospecting
type: pattern
created: 2026-07-14
updated: 2026-07-14
sources: ["[[signals-and-abm]]"]
tags: [pattern, signals, prospecting, proactive-gtm, automation]
---

# Signal-Based Prospecting

A pattern for transforming raw signal detections into qualified, enriched prospects ready for outreach. Replaces reactive "batch and blast" prospecting with event-triggered, timing-optimized engagement.

## Architecture

```
Signal Detection → Enrichment → Qualification → Routing → Action
```

## Step 1: Signal Detection

Configure [[clay-signals]] — default or custom — to monitor for buying events:

| Signal Type | Example | Urgency |
|-------------|---------|---------|
| Job change | Champion moves to new company | High — act within days |
| New hire | VP Marketing joins target account | High — engage before vendor relationships form |
| Funding | Series B announcement | Medium — new budget, but not urgent |
| Tech change | Competitor tool removed | High — active evaluation window |
| Content signal | Blog post about your problem space | Low — awareness, not active buying |

### Run Frequency
- **Daily** — job changes, critical account monitoring
- **Weekly** — market research, broader trend monitoring
- **Monthly** — industry analysis, long-term strategic intelligence

More frequent = catch opportunities faster, but consume more credits. Match frequency to your sales velocity.

## Step 2: Automatic Enrichment

Layer enrichments on signal results automatically:
- **Contact enrichment** — find email, phone so reps can reach out immediately
- **Company enrichment** — tech stack, funding, headcount for qualification and messaging
- **AI research** — [[claygent]] or [[perplexity-enrichment]] for personalized talking points

## Step 3: Qualification

Score and filter signal results before routing to reps:
- Apply [[signal-orchestration]] scoring (point-based or AI-powered)
- Gate expensive downstream actions behind qualification thresholds
- Combine signal data with enrichment data for composite scores

## Step 4: Routing

Route qualified signals to the right team and channel:

| Destination | Use Case |
|-------------|----------|
| **New Clay table** | Dedicated table per signal type for tracking |
| **Existing table** | Append to tables already in use |
| **Slack channel** | Real-time alerts for reps to act immediately |
| **CRM push** | Auto-create records with enriched data populated |
| **Webhooks** | Trigger external systems and advanced automation |

## Step 5: Action

Trigger the appropriate response based on signal type and account value:
- **Personalized outreach** — [[personalized-outbound-pipeline]] with signal as the "why now"
- **Sequence enrollment** — auto-enroll in signal-specific sequences (funding sequence, new hire sequence, etc.)
- **Ad targeting** — add to [[abm-architecture]] retargeting audiences
- **Internal alert** — Slack digest with AI-generated prospect summary

## Best Practices

- **Start with one signal.** Get it working end-to-end before adding more.
- **Quality over quantity.** One well-configured signal beats five noisy ones.
- **Define follow-up processes before launching.** Who gets notified? What actions do they take? Expected response timing?
- **Measure signal-to-opportunity conversion.** Track which signals actually predict buying to refine over time.
- **Layer signals for higher intent.** New CMO (default) + blog about marketing infrastructure challenges (custom) = far higher intent than either alone.

## See Also

- [[clay-signals]] — what signals are and the four categories
- [[signal-orchestration]] — combining signals for higher-intent detection
- [[personalized-outbound-pipeline]] — outreach powered by signal context
- [[abm-architecture]] — signals driving ABM stage progression
- [[experiment-before-scale]] — test signal workflows on small batches
- [[crm-enrichment-lifecycle]] — signals triggering CRM data actions
