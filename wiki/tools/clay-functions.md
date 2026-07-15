---
title: Clay Functions
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: ["[[functions-course]]", "[[clay-mcp-course]]"]
tags: [clay-feature, functions, reusable-workflows, governance, infrastructure, mcp]
---

# Clay Functions

Reusable workflows built from any set of columns in Clay. Define once, set inputs and outputs, save — then anyone in the workspace can call it from any table. Edits propagate to every table using the function automatically.

Think of it like a recipe: the head chef writes it once, line cooks follow it, and when the chef changes it, everyone runs the updated version.

## The Problem It Solves

Rebuilding the same Clay table over and over. Same data sources, same lookups, same logic — duplicated across every new project.

The pain becomes acute at scale. When the same [[waterfall-enrichment]] workflow exists across 10 tables and you need to swap one provider in the email waterfall, you'd have to open each table and update it individually. Functions fix this: update once, propagates everywhere.

## How It Works Behind the Scenes

When a function runs, it spins up its own mini table in the background. All the enrichments, lookups, and transformations execute there. Results pipe back to the calling table as a single column.

The calling table stays clean. Instead of fifteen columns of intermediate logic, you get one column with the final output. The complexity is hidden inside the function.

## Functions vs Templates

| | Templates | Functions |
|---|---|---|
| **Mechanism** | Copy into table | Call from table |
| **Updates** | Manual per table | Auto-propagate everywhere |
| **Table impact** | Adds columns directly | Returns one column (hides complexity) |
| **Governance** | None — each copy is independent | Single source of truth |

Templates are snapshots. Functions are living infrastructure.

## Building a Function

1. **Build and verify the workflow in a table first.** Get the logic right before packaging it. Test on real data — [[experiment-before-scale|run small batches]] before committing.
2. **Select the columns** that make up the workflow, right-click, and choose "Save as function."
3. **Name it clearly.** This is critical — unnamed or vaguely named functions create confusion at scale. Use a naming convention: `Workflow Type + Outputs + Version` (e.g., "Contact Enrichment: Email Plus Phone V1").
4. **Map inputs** (what the function needs from the calling table) and **select outputs** (what it returns).
5. **Toggle "replace columns with function"** to collapse the selected columns into a single function column. Keeps the table clean.
6. **Call from other tables:** find the function in the column menu, map inputs from the calling table's columns, set conditionals if needed, save.

## When to Use (4 Signals)

1. **Running the same enrichment logic across more than one table.** If you've built it twice, it should be a function.
2. **Approaching column limits on heavy enrichment tables.** Functions collapse 15 columns of logic into one.
3. **Want non-technical teammates to run complex workflows.** They add one column, map inputs, done. No understanding of the underlying logic required.
4. **Need governance.** Every team uses the same qualification logic, the same enrichment criteria, the same [[credit-optimization|credit-gated]] workflows. No drift, no shortcuts.

## Three Use Case Categories

### 1. Enrichment Functions

Firmographic enrichment is the classic example. Revenue + employee count + web traffic waterfalls across 12 providers, consolidated into one column back. Instead of building a 12-provider [[waterfall-enrichment]] from scratch in every table, call the function and get clean firmographic data.

Company hierarchy enrichment is more advanced: an AI agent researches parent/subsidiary structure, synthesizes findings, and consolidates into a structured output. Complex enough that you definitely don't want to rebuild it per table.

### 2. Copywriting Functions

These implement the [[ai-snippets]] pattern at scale. Email address goes in. The function runs a Salesforce lookup plus Snowflake queries to pull product usage data and conversation history. That first-party data feeds persona analysis via Claude. Out come 3 message variants:

- **Insight-led** — leads with a relevant observation about the prospect's business
- **Value nugget** — leads with a specific, quantified value proposition
- **High-signal** — leads with a strong buying signal detected in the data

The fallback pattern matters: when no high signal exists, the function returns "NO HIGH SIGNAL - USE STANDARD MESSAGES" instead of forcing a weak personalization. Better to send a solid generic message than a bad personalized one.

### 3. Signal Detection Functions

Job change detection with backup waterfalls — 11 email providers and 12 LinkedIn lookup methods chained together. When one source misses, the next picks up.

Employment status analysis adds relationship context: is this person at a subsidiary? A partner organization? The function handles the nuance so the calling table just gets a clean status back.

These connect directly to [[clay-signals]] and [[signal-orchestration]] workflows.

## Governance Patterns

### Conditional Checkbox Input

Add a checkbox as a function input. Phone enrichment only runs when the checkbox is set to true. This prevents accidental expensive runs — nobody accidentally enriches 1,000 rows of phone data because they forgot to filter first.

The checkbox acts as an explicit opt-in. Cheap enrichments run unconditionally; expensive ones require the checkbox. See [[conditional-runs]] for the underlying pattern.

### GDPR Compliance Gating

Conditional logic inside the function checks the contact's region before any enrichment runs. If the contact is in a restricted geography, the workflow stops. No enrichment, no data processing, no compliance risk.

The key: this runs every time for every caller. Nobody can skip it. The compliance logic is baked into the function, not left to individual table builders to remember.

## Scaling

### Column Limits
Functions solve column limits directly. 15 columns of intermediate logic hidden inside the function, one column returned to the calling table. For tables with heavy enrichment stacks, this is the difference between hitting the wall and scaling further.

### Row Limits
The 50K row limit on standard tables is gone with functions — pass-through execution with no row cap for enterprise-scale workflows.

### Naming Convention
Consistency matters when the function library grows. Use: `Workflow Type + Outputs + Version`.

- "Contact Enrichment: Email Plus Phone V1"
- "Company Firmographics: Revenue + Headcount + Traffic V2"
- "Signal Detection: Job Change + Employment Status V1"

### Internal Catalog
Maintain a shared document listing each function with: name, description, required inputs, outputs, owner, and **cost per row**. Credit costs don't show in the calling table — this is a visibility gap that the catalog fills. Without it, teams burn credits without realizing the per-row cost of the function they're calling.

## Managed vs Custom Functions

When functions are accessed via [[clay-mcp]], they split into two types:

| | Managed Functions | Custom Functions |
|---|---|---|
| **Built by** | Clay (out-of-box) | Your ops team |
| **Coverage** | Common data: work email, job openings, industry, employee count, funding, traffic | Your company's own logic and rules |
| **Write to CRM** | No | Yes (e.g., add contact to Salesforce) |
| **How to call** | Just ask naturally — Clay picks the right one | By name (ops team tells you what it's called) |
| **Setup needed** | None | Published by ops team |

Managed Functions are Clay's pre-built library — reps don't need to know they exist, they just ask for data and Clay invokes the right one. Custom Functions are everything covered in the sections above — your team's own logic, published to the workspace.

## Beyond the Table

Functions are callable from outside Clay via MCP (Model Context Protocol). Claude, ChatGPT, Microsoft Copilot, Codex, Claude Code, and Glean can invoke Clay functions directly. See [[clay-mcp]] for the full conversational prospecting workflow.

This makes functions infrastructure for the full GTM stack, not just Clay tables. A sales rep in Claude can call a function to enrich a prospect mid-conversation. An internal knowledge tool can trigger a signal detection function when a user asks about an account.

The quality of naming, input definitions, and output structure matters even more for external callers. A human in Clay can figure out a vaguely named function. An AI caller cannot.

## Availability

Available on all paid Clay plans at no additional cost.

## See Also

- [[clay-audiences]] — Functions are reusable across audiences, not just tables
- [[claygent-builder]] — Builder manages agents; Functions manage workflows. Complementary tools for different types of reusable logic
- [[credit-optimization]] — Governance patterns like conditional checkboxes and GDPR gating are credit optimization at the infrastructure level
- [[waterfall-enrichment]] — The most common pattern packaged as a function
- [[experiment-before-scale]] — Build and test in a table first, then save as a function
- [[ai-snippets]] — Copywriting functions implement the snippet pattern with first-party data
