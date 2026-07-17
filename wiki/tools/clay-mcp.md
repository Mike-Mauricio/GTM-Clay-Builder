---
title: Clay MCP
type: tool
created: 2026-07-14
updated: 2026-07-14
sources:
  - "[[clay-mcp-course]]"
  - "[[best-practices-getting-started]]"
tags:
  - clay-feature
  - mcp
  - conversational-prospecting
  - claude
  - chatgpt
  - copilot
  - ai-chat
---

# Clay MCP

## What It Is

Clay's Model Context Protocol integration that lets reps use Clay directly inside AI chat tools — ChatGPT, Claude, Microsoft Copilot, Claude Code, Codex, and Glean. Research accounts, build lists, find/enrich contacts, and draft personalized outreach in a single conversation without opening Clay or switching tools.

## Setup

- **Claude:** claude.com/connectors → find Clay → connect. Also via Customize → Connectors or Settings.
- **ChatGPT:** type `@clay` in any prompt to authenticate, or Settings → Connectors → Clay.
- **Microsoft 365 Copilot:** separate setup directions via Clay docs.
- **Also works in:** Codex, Claude Code, Glean.
- 500 free credits to start on all platforms.

## The Full Prospecting Motion (One Conversation)

1. **Research the account** — "Research Stripe's recent product launches, hiring trends, and expansion signals." Clay uses live data providers (not training data). Add "use Clay" to force Clay data vs generic web scraping.
2. **Build a target list** — "Find tech companies in New York with 200-500 employees." Same filters as Clay app (industry, size, location, revenue, funding, tech stack).
3. **Find the right people** — "Find sales leaders at CB Insights." Search one company for depth or several at once for breadth.
4. **Filter before enriching** — "Narrow to director level and above, US-based, who joined in the last year." This is how you save credits — never enrich everything.
5. **Enrich selectively** — "Enrich these six contacts with email, work history, and recent thought leadership." Only spend on people who matter.
6. **Call Functions** — "Get the current job openings at Stripe." Managed Functions auto-invoke; Custom Functions called by name. See below.
7. **Draft outreach** — "Draft a personalized email referencing their background and recent company initiatives." Context carries from research steps.
8. **Send** — Claude has a generative email widget (send directly from conversation). ChatGPT: copy to sequencer or send manually.

## The Credit-Saving Pattern: Search → Filter → Enrich

Don't enrich everything returned. Search broad, filter to the people who matter, then enrich only those. This is how you make 500 credits last.

See [[credit-optimization]] for the full framework.

## Functions via MCP

Two kinds of functions accessible from MCP:

| | Managed Functions | Custom Functions |
|---|---|---|
| Built by | Clay (out-of-box) | Your ops team |
| Coverage | Common data: work email, job openings, industry, employee count, funding, traffic | Your company's own logic and rules |
| Write to CRM | No | Yes |
| How to call | Just ask naturally — Clay picks the right one | By name (ops team tells you what it's called) |
| Setup needed | None | Published by ops team |

Examples: "Get job openings at Stripe" (managed), "Run our account scoring function on Acme" (custom).

See [[clay-functions]] for full details on Managed and Custom Functions.

## Business Context

Configure in Clay settings to teach the AI your company, ICP, and value prop. Emails auto-fill based on this context — messages sound like your team wrote them instead of generic AI output. Optional but strongly recommended.

## First-Party Data (via Audiences)

When your ops team has connected [[clay-audiences]], you can query your own CRM/Salesforce data, Gong calls, and engagement history in the same conversation: "What do we already know about CB Insights? Show me open opportunities, past touches, and any signals Clay has flagged." This blends first-party context with market research.

## Competitive Research

"Research CB Insights' products. Who are their main competitors? Give me 3 bullets on their priorities and 3 bullets on risks from those competitors." Clay's live data reveals insights like "defending, not expanding — 265 employees, shrinking 43% over 4 years."

## Individual Briefs

Before outreach, generate summary briefs on top contacts: "Give me summary briefs on each of the top three contacts — background, priorities, recent public commentary." Provides opinionated prioritization.

## Troubleshooting

**Dev Tools first:** Use Network + Console tabs to determine if the block is AI-tool-side (e.g., 403 on OpenAI endpoint) vs Clay-side (function errors, integration issues). If the same prompt works in Claude but fails in ChatGPT, it's usually a ChatGPT org-level restriction.

**Function naming conflicts:** If a custom function name overlaps with a built-in Clay tool, the AI may invoke the wrong one. Fix: prompt "List subroutines" then call by exact name. Avoid generic names like "find contacts."

**ChatGPT 403 "MCP Tool is disabled":** Comes from OpenAI's policy layer, not Clay. The workspace admin must enable the Clay app + all actions, including `run_subroutine_no_mapping` (commonly missed — this is the action that executes custom Functions).

**"Failed to update integration settings":** Hard-refresh; if persists, recreate the function under a different name.

## Admin Controls

- **Default credit limit:** Settings → MCP users — applies to all new reps
- **Per-user overrides:** Set higher/lower limits for specific users
- **Block access:** Remove from workspace or set credit limit to 0 (cannot directly revoke OAuth)
- **Identity sync from Salesforce:** Enable "Sync user IDs from audiences" to restrict reps to only accounts they own in Salesforce
- **Sales Rep role:** Lowest-permission seat — MCP access only, no Clay UI, no table editing, no API key visibility. Reps don't need their own API keys — functions execute server-side with workspace credentials.

## Credit Behavior

- People/company **search** via MCP is free (no credits)
- Credits consumed only on actual enrichments or Function calls
- **Querying Audiences data** uses actions, not credits
- Credit cost is identical whether triggered from Clay, Claude, or ChatGPT
- One-off operations (find email, research account) don't create a Clay table by default — results stay in chat unless user clicks "Open in Clay"

## Limitations

- Results paginate in groups of 20, up to 100 results (5 pages). Beyond 100, use Clay directly.
- Best used for: individual SDR/AE prospecting, meeting prep, quick research, targeted outreach
- Outreach via sequencer requires a Function built for it (sequencer column exposed via MCP); without it, AI can only send via connected email (Gmail)
- CSV in Claude: share CSV in conversation and Claude calls Function once per row (no dedicated bulk upload via MCP)
- Currently connects to Claude, ChatGPT, Microsoft Copilot, and Glean — no self-hosted MCP server for other tools

## Who It's For

SDRs, AEs, and anyone doing prospecting and research. There's a separate Operators course for RevOps/admin setup.

## See Also

- [[clay-functions]] — Managed and Custom Functions callable via MCP
- [[clay-audiences]] — first-party data accessible through MCP conversations
- [[personalized-outbound-pipeline]] — the full outbound pattern MCP implements conversationally
- [[speed-to-lead]] — MCP enables instant research-to-outreach for inbound leads
- [[credit-optimization]] — search → filter → enrich pattern saves credits
