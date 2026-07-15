---
title: Lead Routing
type: concept
created: 2026-07-14
updated: 2026-07-14
sources:
  - "[[automated-inbound]]"
tags:
  - concept
  - routing
  - inbound
  - round-robin
  - rep-assignment
---

# Lead Routing

Getting the right leads to the right reps as fast as possible. Routing is the step between [[lead-scoring]] and outreach — once a lead is qualified and scored, it needs to land on a specific rep's desk without manual intervention. In the context of [[speed-to-lead]], routing delays are pipeline killers.

## Weighted Round Robin in Clay

Clay has a native action: **"Distribute Leads Round Robin (Weighted)"**. This is the primary routing mechanism for most inbound pipelines.

### How It Works

The action references a **rep table** — a separate Clay table that serves as the live source of truth for your sales team. Each row in the rep table represents one rep with these fields:

| Column | Purpose |
|--------|---------|
| Rep Name | Display name for assignment |
| Rep Email | Where notifications and CRM assignments go |
| Status | Active/inactive toggle — inactive reps stop receiving leads |
| Weight | Relative share of lead distribution |

### Weight Distribution

Weights determine what proportion of leads each rep receives. They're relative, not absolute:

- **Weights: 2, 2, 1** → Rep A gets 40%, Rep B gets 40%, Rep C gets 20%
- **Weights: 3, 1, 1** → Rep A gets 60%, Rep B gets 20%, Rep C gets 20%
- **Default weight: 1** — if no weight is specified, all reps get even distribution

Use higher weights for:
- Senior reps who can handle more volume
- Reps covering high-priority territories
- Ramp-up periods where you want to funnel more leads to proven closers

### Keeping the Rep Table Current

The rep table can be set to **import from Salesforce on a schedule**, pulling the current active user list, territories, and any custom fields you use for routing. This keeps Clay's routing table in sync with your CRM without manual updates.

When a rep goes on PTO or leaves the team, update their status in Salesforce — the next scheduled import updates Clay automatically, and that rep stops receiving leads.

## What Round Robin Handles

- **Workload balancing** — no rep gets buried while another has an empty queue
- **Territory respect** — weight adjustments can approximate territory-based routing
- **Specialization** — combine with pre-routing filters (e.g., enterprise leads go to a separate table with only enterprise reps)
- **Speed** — automated assignment means zero delay between scoring and rep notification

## Beyond Round Robin

For complex or niche routing logic that goes beyond weighted distribution — territory-based rules, skill-based matching, capacity-aware routing, or multi-criteria assignment — consider dedicated routing tools like **Default**. These tools specialize in the routing problem and can handle edge cases that a round robin can't express.

The decision point: if your routing rules can be expressed as "distribute evenly with weights," Clay's native action is sufficient and keeps everything in one platform. If your rules require conditional logic, geographic matching, or real-time capacity awareness, a dedicated routing layer is worth the integration complexity.

## Related

- [[inbound-automation-pipeline]] — routing is the step between scoring and personalization
- [[lead-scoring]] — scores feed routing decisions
- [[speed-to-lead]] — routing speed directly impacts lead conversion
- [[clay-salesforce-integration]] — rep table sync from Salesforce
