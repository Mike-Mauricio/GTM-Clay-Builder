---
title: Clay Webhooks
type: tool
created: 2026-07-14
updated: 2026-07-14
sources:
  - "[[automated-inbound]]"
tags:
  - tool
  - clay-feature
  - webhooks
  - inbound
  - lead-capture
  - real-time
---

# Clay Webhooks

Import mechanism for capturing leads from any source in real-time. Webhooks let Clay receive data the moment an event happens — a form submission, a webinar registration, a trial signup — without polling or scheduled imports.

## Setup

1. In Clay, go to **Import → "Pull in data from a Webhook"**
2. Clay generates a unique webhook URL
3. Copy the URL and paste it into the source tool's webhook configuration
4. Send a test event to confirm the connection
5. Clay automatically maps incoming fields to columns

That's it. Every subsequent event from that source flows into the Clay table instantly.

## Common Use Cases

| Source | Signal | Why It Matters |
|--------|--------|----------------|
| **Typeform / Forms** | Form submissions | Inbound interest — the highest-intent signal |
| **Zoom** | Webinar registrants & attendees | Event engagement — registrants show interest, attendees show commitment |
| **Trial / Product** | Trial signups | Product-qualified leads — already exploring your tool |
| **Intercom / Zendesk / Drift** | Chat conversations | Support-initiated interest or expansion signals |
| **Blog / Content** | Subscribers, downloads | Content engagement — early-funnel interest signals |
| **Segment** | Content engagement events | Behavioral data — page views, feature usage, custom events |
| **Any tool with webhooks** | Custom events | If it sends webhooks, Clay can receive it |

### Typeform Shortcut

Clay also has a **native Typeform integration** — go to Import → "Import Typeform form responses." This is simpler than the webhook approach for Typeform specifically, since it handles the connection setup and field mapping automatically. Use the native integration when Typeform is your only form source; use webhooks when you want a consistent pattern across multiple sources.

## Limits

- **50,000 submissions per webhook source** — this is a per-table limit on webhook imports
- When approaching the limit, create a new table with a fresh webhook URL for additional volume
- For high-volume sources, monitor submission counts and plan table rotation in advance

## Strategic Insight: Clay-First Routing

The default instinct is to route inbound signals to the CRM first, then enrich from there. This is backwards for [[speed-to-lead]].

**CRM-first routing** introduces delays at every step:
1. Signal hits CRM → CRM processes and creates record → sync to enrichment tool → enrichment runs → results sync back to CRM → rep gets notified

**Clay-first routing** collapses this:
1. Signal hits Clay via webhook → enrichment runs instantly → scoring and routing happen in the same table → qualified lead pushes to CRM and sequencer simultaneously

The CRM receives a finished, enriched, scored, routed lead — not a raw form fill that needs manual processing.

## Team Interest Signals

When multiple people from the same company submit through the same webhook source, that's a strong **team interest signal**. One person filling out a form is individual curiosity. Two or three people from the same domain is organizational intent — the problem is being discussed internally.

Clay can detect this pattern using company domain grouping. When you see it, act fast — this signal decays quickly but converts at a much higher rate than individual submissions.

## Related

- [[speed-to-lead]] — webhooks enable real-time processing, the foundation of fast response
- [[inbound-automation-pipeline]] — webhooks are the input layer of the full pipeline
- [[fete-framework]] — webhooks implement the "Find" step for inbound signals
