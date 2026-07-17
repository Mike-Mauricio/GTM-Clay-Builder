---
title: Clay API & CLI
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: [[best-practices-getting-started]]
tags: [api, developer, integration]
---

# Clay API & CLI

Clay's developer platform for programmatic access to Clay's GTM dataset, enrichment functions, and workflows — no UI required. Includes the **Public API** (REST endpoints for backend services and batch jobs) and the **CLI** (natural language workflow building from coding agents like Claude Code, Codex, and Cursor).

## Does Clay Have a Traditional API?

Not exactly. Clay is not a typical SaaS tool where you hit an endpoint and get data back in milliseconds. It is an enrichment and automation platform built around tables, workflows, and integrations. Enrichment calls may take seconds to minutes depending on complexity.

There are **three ways to interact with Clay programmatically**, depending on what you need:

### 1. Webhooks (Send Data In)

Every Clay table has a unique webhook endpoint. Send data from forms, CRMs, or other apps — Clay processes it immediately through enrichment columns, then you push results back out via [[clay-http-api|HTTP API]] actions.

This is the most "API-like" pattern for most users. See [[clay-webhooks]] for the full setup.

**Auto-delete for high-volume streaming:** When using Clay as an API pipeline, enable Auto-delete to automatically enrich incoming webhook data, send results to your destination (Salesforce, Google Sheets, etc.), then delete the rows. Clay streams data through rather than storing it — ideal for high-volume or continuous enrichment jobs.

### 2. Third-Party Wrappers (Light API Proxying)

Use tools like Replit or Make as a wrapper around Clay. They receive API requests, trigger Clay enrichments, and return results once processing completes.

Works when you absolutely need an endpoint, but be aware:
- Responses may take a minute or more (Clay enrichments are not instant)
- You need to build logic to handle async processing and timeouts
- Adds a dependency on the wrapper tool

### 3. Enterprise People & Company API (Direct Lookups)

Enterprise-only. A fast, native API for accessing Clay's proprietary People and Company data.

- Send an email or LinkedIn URL to get person details
- Send a domain to get company info
- Useful for lightweight lookups and lead enrichment
- Does NOT include deep enrichment (emails, phone numbers, revenue data)

## Agent Plugin (CLI + Public API)

Clay's Agent Plugin is in **open beta**. It provides two primary features:

### CLI

Build GTM workflows in natural language from coding agents. Install via:

```
Set up the Clay plugin by following the steps in https://github.com/clay-run/agent-plugins
```

Supported in Claude Code, Codex, and Cursor. Mac and Linux only (no Windows in open beta).

### Public API

Direct HTTP access for backend services, queue workers, batch jobs, and custom app integrations. Better suited than the CLI for headless/automated workflows.

Full docs at [developers.clay.com](https://developers.clay.com/).

### Three Core Primitives

| Primitive | What It Does | Availability |
|-----------|-------------|-------------|
| **Searches** | Find companies and people using structured filters over Clay's GTM dataset | All plans |
| **Routines** | Run Clay-managed functions, custom functions, and Workflows for enrichment, research, scoring, routing | All plans |
| **Tables** | Read structured data from known Clay tables (read-only) | Enterprise only |

Both CLI and API calls consume the **same credits and actions** as equivalent in-product work. No additional cost.

### MCP vs CLI/API

- **[[clay-mcp|MCP]]** — Used by interactive AI assistants (Claude Desktop, ChatGPT) via OAuth for conversational access
- **CLI/API** — Designed for programmatic, headless, or automated workflows (scripts, backend services, coding agents)

## Plan Availability and Limits

The developer platform is available across **all Clay plans**, including free and trial. Agent Plugin open beta is available on all modern plans and, for a limited time, on legacy plans through end of 2026.

| Plan | Results per Request | Total Search Results |
|------|-------------------|---------------------|
| Free | 50 | 100/mo |
| Trial | 50 | 10K per 14 days |
| Paid self-serve | 10,000 | 1M/yr |
| Enterprise | 10,000 | 10M/yr |

## What You Cannot Do (Yet)

- **Build or write to Clay tables** via CLI or API — the CLI builds logic via Workflows, not tables. The Tables primitive is read-only (Enterprise only).
- **Credit budgets** are not yet available in open beta. You can see run-level credit and action consumption from the Runs view in Workflows. Credit budget support is on the roadmap.

## Terms of Service

If you purchase Clay Credits, you agree:
- **No reselling credits** — cannot sell or transfer credits to any other user without prior written approval
- **No reselling data** — cannot re-sell any data obtained from Clay

See [Clay Terms of Service](https://www.clay.com/terms-of-service) for full details.

## Related

- [[clay-http-api]] — HTTP API enrichment and source mode for connecting to any external API
- [[clay-webhooks]] — Webhook endpoints for streaming data into Clay tables
- [[clay-functions]] — Reusable workflows: Managed + Custom functions
- [[clay-mcp]] — Conversational prospecting via MCP protocol
- [[clay-audiences]] — Persistent, always-on enrichment layer (vs Tables for experiments)
- [[conditional-runs]] — Boolean gating to control when enrichments fire
