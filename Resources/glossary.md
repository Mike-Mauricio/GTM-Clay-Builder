---
category: reference
last-verified: 2026-07-13
---

# GTM Engineering Glossary

| Term | Definition |
|------|-----------|
| **FETE** | Find, Enrich, Transform, Export — Clay's core workflow model |
| **Table** | A Clay workspace for building and testing enrichment workflows. Tables are labs — build, iterate, discard |
| **Audience** | A persistent, auto-updating Clay list. Audiences are the orchestration layer — they keep running |
| **Claygent** | Clay's AI agent that can browse the web, find contacts, and extract data using natural language prompts |
| **Sculptor** | Clay's AI analysis tool for spotting patterns, analyzing distributions, and summarizing enrichment results |
| **Enrichment** | The process of adding data to a record — company info, contact details, tech stack, signals |
| **Waterfall Enrichment** | Chaining multiple data providers with fallthrough logic — if provider A returns empty, try provider B |
| **Credit Gating** | Running cheap/free enrichments first, then only spending credits on records that pass qualification filters |
| **Signal Convergence** | Scoring based on multiple reinforcing signals rather than any single filter. Three weak signals > one strong signal |
| **Boolean Decomposition** | Breaking complex routing logic into independent true/false columns that feed a single routing formula |
| **TAM** | Total Addressable Market — the full universe of companies that could be customers |
| **ICP** | Ideal Customer Profile — the specific characteristics of your best-fit customers |
| **Enrichment Discipline** | "Enrich with intent, not with availability" — only enrich fields that change routing, scoring, or copy |
| **HTTP API Action** | Clay's method for calling external APIs that don't have native integrations |
| **Native Integration** | A built-in Clay connector (e.g., BuiltWith, Apollo, Clearbit) |
| **Non-Native Integration** | An external tool connected via HTTP API, webhook, or Zapier |
