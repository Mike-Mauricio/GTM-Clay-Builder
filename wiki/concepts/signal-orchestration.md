---
title: Signal Orchestration
type: concept
created: 2026-07-14
updated: 2026-07-14
sources: ["[[signals-and-abm]]"]
tags: [concept, signals, scoring, orchestration, signal-stacking, velocity]
---

# Signal Orchestration

The practice of combining multiple [[clay-signals]] to create a holistic view of prospect intent. A single signal provides limited context — but layering signals together reveals genuine buying momentum. Also called "signal stacking."

## Why Single Signals Aren't Enough

A pricing page visit alone is ambiguous. But a pricing page visit + recent funding news + competitor mention on LinkedIn + new revenue team hire = a pattern indicating real buying momentum. Each signal alone is interesting; together, they tell a compelling story.

## Three Processing Models

### Sequential Processing (Journey-Based)
Signals must occur in a specific order before triggering action. Maps to a defined buyer journey:
1. Engages with educational content
2. Visits website
3. Downloads resource
→ Then trigger outreach

**Best for:** Clear, predictable buyer journeys with defined milestones.

### Parallel Processing (Threshold-Based)
Monitor multiple signals simultaneously. Take action when any combination reaches a threshold (e.g., 3 out of 5 signals hit), regardless of order.

**Best for:** Non-linear buyer journeys. Captures more opportunities. Requires stronger scoring to avoid false positives.

### Hybrid Approach
Most successful teams combine both:
- **Parallel processing** for initial qualification (wider net)
- **Sequential processing** for nurture sequences (guided stages toward conversion)

## Signal Weight Assignment

Not all signals carry equal predictive power. A pricing page visit from a C-level exec at a target account should weight far more than a blog view from an intern.

Weights should evolve based on performance data. If competitor mentions convert at 40% higher rates than content downloads, adjust scoring to reflect this. This requires a feedback loop between scoring and conversion outcomes.

## Signal Velocity

One of the most underutilized aspects of signal intelligence. The temporal relationship between signals often reveals more than the signals themselves.

**Scenario A:** Pricing page Monday → case study Tuesday → job posting Wednesday = concentrated, accelerating interest. Likely active evaluation.

**Scenario B:** Pricing page January → case study March → job posting May = passive awareness over months.

Same three signals, dramatically different intent. In Clay, track velocity by date-stamping signal records and using formulas to calculate time elapsed between first and most recent signal.

## Scoring Systems

### Point-Based Scoring
Assign specific point values to criteria, set qualification thresholds. Use Clay's native **Score Row** capability.

**Best for:** Clean, structured data with clear conversion patterns.

### AI-Powered Scoring
Use AI to interpret unstructured data, messy inputs, or when you don't yet know what weights to assign.

Example prompt:
```
Score this prospect from 1-100 considering: We sell best to
high-growth tech companies. Recent funding is a strong positive.
Using our competitor makes them harder to convert. Multiple
signals indicate higher intent.
```

**Best for:** Messy data, unstructured text, contextual understanding, early-stage learning.

### Learning Scoring Systems
Track outcomes back to initial scores to build a closed feedback loop:
- Initial score when entering system
- Which signals triggered qualification
- Time from qualification to first conversation
- Conversion outcome (won/lost/pipeline)
- Deal size if won

Over time, patterns emerge that refine the model.

## Relationship to Signal Convergence

Signal orchestration is the operationalized version of the "signal convergence over single-filter scoring" principle from GTM engineering. Don't disqualify on any single signal — use multi-signal composite scores where signals reinforce each other.

## See Also

- [[clay-signals]] — what signals are and the four categories
- [[signal-based-prospecting]] — the implementation pattern
- [[abm-architecture]] — signals powering ABM stage progression
- [[gtm-alpha]] — orchestrated signals create proprietary competitive advantage
- [[credit-optimization]] — balance signal monitoring frequency with credit spend
