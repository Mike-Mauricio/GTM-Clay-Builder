---
title: Claygent Builder
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]"]
tags: [clay-feature, ai, agent-management, claygent, builder]
---

# Claygent Builder

A centralized environment for building, testing, and deploying [[claygent|Claygent]] agents across Clay tables. Accessed via the Agents nav in Clay. Replaces the previous workflow of configuring Claygent inline within individual table columns.

## Key Features

### Sculptor
Natural language agent creation — describe what you want the agent to do, and Sculptor builds the configuration:

**Example:** "Build an agent that scores a lead against our ICP and outputs a score from 1 to 100 with a short rationale explaining the score."

**Refinement:** "Adjust the scoring so company fit is weighted at 60% and persona fit at 40%. Also break out company size as its own factor."

Sculptor iterates on the agent configuration conversationally — no manual prompt engineering needed.

### Free Testing
Testing inside Claygent Builder is **free** — no credits consumed. This changes the experimentation economics: iterate as many times as needed before deploying to a table where credits are consumed.

### Centralized Management
Agents are saved centrally and deployed to tables via AI columns:
1. Build and test agent in Builder
2. Save as a "Saved Claygent"
3. In any table: add AI column → select from Saved Claygents
4. Variables auto-map to table columns
5. **One change in Builder propagates to all tables using that agent**

This solves the maintenance problem — previously, updating a Claygent prompt meant editing it in every table separately.

### Business Context
Claygent Builder pulls from workspace-level Business Context (Settings):
- Company description
- ICP definition
- Buyer personas

Agents automatically have access to this context without repeating it in every prompt.

### Advanced Configuration

| Option | Purpose |
|--------|---------|
| Document attachments | Attach tone guides, example emails, style docs |
| MCP server connections | Connect external tools/APIs |
| Model switching | Compare results across different models |
| Contact/jobs access | Let agent find contacts or job postings automatically |

## Three Ways to Start

1. **From scratch** — Manual prompt configuration
2. **With Sculptor** — Natural language description → auto-built agent
3. **From template** — Pre-built agent templates for common use cases

## Example: Lead Scoring Agent

1. Open Claygent Builder → Sculptor
2. Prompt: "Build an agent that scores leads against our ICP, 1-100 with rationale"
3. Sculptor generates the agent configuration
4. Refine: "Weight company fit at 60%, persona fit at 40%"
5. Test on sample data (free)
6. Save as "ICP Lead Scorer"
7. Deploy to any table via AI column → Saved Claygents

## Example: Outbound Email Writer

1. Sculptor: "Build an agent that writes personalized cold emails using prospect data"
2. Business Context auto-populates company/ICP info
3. Attach tone guide document
4. Test with sample prospects (free)
5. Deploy across outbound tables

## See Also

- [[claygent]] — the underlying AI agent that Builder manages
- [[prompt-engineering-at-scale]] — Builder reduces the need for manual prompt engineering
- [[credit-optimization]] — free testing in Builder saves credits
- [[metaprompter]] — complementary prompt improvement tool
