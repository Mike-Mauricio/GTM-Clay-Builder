---
title: Clay AI Architecture
type: concept
created: 2026-07-14
updated: 2026-07-14
sources: ["[[best-practices-getting-started]]"]
tags: [ai, architecture, privacy, security, models, pricing, byok]
---

# Clay AI Architecture

Unified overview of how AI is embedded across Clay's platform — which features use AI, which models power them, how pricing works, and Clay's data privacy guarantees.

**Core guarantee: Your data is never used to train AI models.** Clay has contractual agreements with all AI providers prohibiting customer data from being used for model training.

## AI Features Map

| Feature | What It Does | How AI Is Used |
|---------|-------------|----------------|
| **Email Sequencer** | Email campaigns from tables | Generates personalized copy using prospect data and business context |
| **Message Drafting** | Per-prospect outreach | Reads table columns to create tailored messages using "My Business Context" |
| **Use AI** | Web research, content gen, image gen | Multi-model access for research, structured extraction, and image creation |
| **Claygent** | AI web agent for scraping/research | Navigates websites, extracts information, makes source decisions |
| **Sculptor** | Chat interface for table building | Reads table data, suggests formulas, helps debug and analyze |
| **Formula Generator** | Natural language to formulas | Converts descriptions to Clay formula syntax (only schema sent, not row data) |
| **API Generator** | Natural language to HTTP requests | Generates API configurations from descriptions (credentials never sent to AI) |
| **Debug with AI** | Error diagnosis | Analyzes error logs against Clay docs (personal table data excluded) |
| **Find Companies (NL)** | Natural language ICP search | Converts ICP description to database queries against 50M+ companies |

## Available Models

Clay provides access to models from multiple providers:

| Provider | Notable Models |
|----------|---------------|
| **Clay** | Helium, Neon, Argon, Xenon, Radon, Conductor, Navigator |
| **OpenAI** | GPT-4o, GPT-4.1, GPT-5/5.1/5 Mini/5 Nano, o1/o3/o4 Mini, DALL-E 3, GPT Image 1 |
| **Anthropic** | Claude 3/3.5 Haiku, Claude 3.7/4/4.5 Sonnet, Claude 4/4.5/4.6 Opus |
| **Google** | Gemini 2.0/2.5 Flash, Gemini 2.5/3 Pro, Imagen 3.0 |
| **xAI** | Grok 4, Grok 4.1 Fast Reasoning |
| **DeepSeek** | R1, V3.2 |
| **Mistral** | Medium 3, Large 2.1/3, Magistral Medium, Devstral 2 |

Option to bring your own API keys (BYOK) for any supported provider.

## AI Pricing

Clay uses two pricing structures for AI — both consuming data credits (plus 1 action per AI prompt).

### Fixed Pricing (~80% of models)

Flat data credit cost per task. Known before you run. Applies to all Clay models and most third-party models.

| Provider | Model | Content Gen | Web Research |
|----------|-------|-------------|--------------|
| Clay | Helium | -- | 1 credit |
| Clay | Argon | -- | 3 credits |
| OpenAI | GPT-5 Mini | 0.4 | 1 |
| OpenAI | GPT-5 Nano | 0.2 | 0.5 |
| Gemini | 2.5 Flash | 0.5 | 1 |

### Variable Pricing (~20% of models)

Charges based on actual LLM cost with **0% markup**. Applies to advanced reasoning models where compute cost varies significantly per prompt. The process:

1. **Withhold** — estimated credits held upfront (75th percentile of past runs)
2. **Execute** — model processes the task
3. **Calculate** — actual LLM cost determined per row
4. **Reconcile** — surplus refunded, additional cost deducted. You only pay actual cost.

| Provider | Model | Content Gen | Web Research |
|----------|-------|-------------|--------------|
| OpenAI | GPT-4o | 1 | variable |
| OpenAI | o3 | 5 | variable |
| Anthropic | Claude 4.5 Haiku | 1 | variable |
| Anthropic | Claude 4.5 Sonnet | 1.5 | variable |
| Anthropic | Claude 4.6 Opus | 7.5 | variable |
| Gemini | 2.5 Pro | 3 | variable |

**Balance protection:** If credits reach zero during a run, processing stops. Completed rows retain results; unstarted rows don't run.

### Deterministic vs. Generative

This pricing distinction maps to [[deterministic-vs-generative]]:
- **Deterministic AI** (extract, calculate, classify) = free, no credits
- **Generative AI** (content creation, research, reasoning) = costs credits per the tables above

### BYOK (Bring Your Own Keys)

Using your own API keys eliminates data credit cost but still consumes 1 action per run. Clay's built-in AI often runs up to 2x faster due to negotiated higher rate limits.

When using external keys, AI usage is billed directly by the provider. Track spending in the provider's console — Clay only shows actions consumed.

## Data Privacy & Security

### Encryption & Compliance

- **At rest:** Industry-standard encryption (AWS US-East)
- **In transit:** TLS 1.2/1.3
- **Certifications:** SOC 2 Type II, ISO 27001, GDPR, CCPA
- **Data location:** Primarily US (AWS US-East)

### Data Control

- Clay acts as **data processor**; you remain the **data controller**
- All AI features are opt-in — you choose which columns AI sees
- Data deletion available at any time; workspace deletion removes all data after 30 days
- Only authorized workspace users can access your data

### AI Provider Guarantees

All AI subprocessors (OpenAI, Anthropic, Google, others) are contractually obligated to:
- Never train models on customer data
- Maintain security certifications (SOC 2, ISO 27001)
- Comply with data protection regulations

Full subprocessor list: [trust.clay.com](http://trust.clay.com/)

## See Also

- [[deterministic-vs-generative]] — free vs. credit-consuming AI transformations
- [[credit-optimization]] — strategies for managing AI credit spend
- [[claygent]] — AI web agent details and model tiers
- [[metaprompter]] — prompt improvement before spending credits
