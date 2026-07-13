# Clay GTM Engineer — AI Context Pack Design Spec

## Context

Mike has deep Clay expertise from the Alpha Forge program (10+ frameworks, 3 production build guides, extensive Claygent patterns) plus a complete Lead Enrichment Workflow spec. This knowledge is currently scattered across FDC-Content-OS (private). None of it is packaged for external use.

The Clay GTM Engineer is a **public GitHub repo** that packages this expertise as an AI context pack — a repo you clone, open in Claude Code, and immediately have an expert Clay/GTM engineering assistant. It's simultaneously an Obsidian vault for visual browsing. Long-term, it serves as a lead magnet for Fortuna (Mike's AI agency), demonstrating expertise through experience rather than sales copy.

**Completely independent** from The Forge (Mike's private build environment). Separate repo, separate content, no cross-references.

## Core Concept

The repo IS the product. CLAUDE.md turns Claude Code into a "Clay GTM Engineer" — an expert assistant that knows Clay documentation, GTM engineering frameworks, and production-tested build patterns. Users clone and build. The quality of Claude's assistance reflects the quality of the knowledge base, which naturally demonstrates Mike's expertise.

**Target audience:** Progressive depth — beginners can start with Playbooks/01, experienced operators can jump to advanced patterns. Primary user: someone building GTM workflows with Clay who wants expert guidance, whether they're new or leveling up.

## Repo Structure

```
clay-gtm-engineer/
├── README.md                        # GitHub landing page — what, how, CTA
├── CLAUDE.md                        # The product — turns Claude into a Clay GTM expert
├── .obsidian/                       # Obsidian vault config
│
├── Knowledge/                       # ═══ REFERENCE LAYER ═══
│   ├── Clay/                        # Clay-specific documentation
│   │   ├── Foundations/             # FETE framework, mental models, how Clay thinks
│   │   ├── Tables/                  # Table types, columns, views, formulas
│   │   ├── Enrichments/            # Native + non-native enrichments, waterfall patterns
│   │   ├── Claygent/               # AI agent patterns, prompt templates, use cases
│   │   ├── Audiences/              # Audiences vs. Tables, persistent orchestration
│   │   ├── Integrations/           # CRM sync, webhooks, HTTP API, Zapier
│   │   └── Credits/                # Credit optimization, gating strategies, budgeting
│   │
│   └── GTM-Engineering/             # Tool-agnostic GTM concepts
│       ├── Enrichment-Philosophy/   # "Enrich with intent", waterfall design, data quality
│       ├── Scoring-Frameworks/      # Signal convergence, composite scoring, threshold design
│       ├── Segmentation/            # Segment design, routing logic, Boolean decomposition
│       └── Outbound-Architecture/   # Motion design, personalization, A/B testing, ethics
│
├── Playbooks/                       # ═══ BUILD LAYER ═══
│   ├── 01-Your-First-Table/         # Beginner
│   ├── 02-Company-Research/         # Intermediate — TAM building + scoring
│   ├── 03-Enrichment-Pipeline/      # Intermediate — waterfall enrichment + gating
│   ├── 04-Segmentation/             # Advanced — signal convergence + routing
│   ├── 05-Outbound-Motion/          # Advanced — personalization + message generation
│   └── [Future playbooks]/
│
├── Examples/                        # ═══ REFERENCE ═══
│   ├── Formulas/                    # Clay formula examples (scoring, routing, cleaning)
│   ├── Claygent-Prompts/           # Production Claygent prompt templates
│   └── Workflows/                   # Complete workflow specs (anonymized)
│
└── Resources/                       # ═══ META ═══
    ├── glossary.md                  # GTM engineering terminology
    └── tool-landscape.md            # Where Clay fits in the broader GTM stack
```

**Key structural decisions:**
- Knowledge/ splits Clay-specific docs from tool-agnostic GTM-Engineering. The philosophy is what makes this more than just Clay docs.
- Knowledge/Clay/ subfolders are initial scaffolding — will adapt as Mike ingests Clay Academy content as markdown files.
- Playbooks/ are numbered for progressive difficulty. Self-contained build guides with clear outcomes.
- Examples/ holds copy-paste resources — formula snippets, prompt templates, workflow specs.
- No Projects/ folder — this is a template, not a workspace. Users build in their own environments.

## CLAUDE.md Design

Seven sections that make Claude a Clay GTM expert for strangers:

### 1. Identity
Sets Claude's role: "You are a Clay GTM Engineer — an expert assistant for building go-to-market workflows using Clay and related tools." Primes Claude to stay in character and reference the knowledge base over training data.

### 2. How This Repo Works
Brief explanation of the three layers: Knowledge (reference), Playbooks (guided builds), Examples (copy-paste). Tells Claude where to look and when.

### 3. Session Modes
Four modes Claude infers from context:

- **Brainstorm** — "I need a way to [X]" → Explore options using Knowledge/, suggest Playbooks
- **Design** — "Architect a [workflow]" → Spec it out, reference GTM-Engineering/ + Clay/
- **Build** — "Write the formula for [X]" → Pull from Examples/, produce production-ready configs
- **Learn** — "Explain how [enrichment] works" → Teach from Knowledge/, point to Playbooks

Learn mode is unique to the public repo (not in The Forge) — tuned for education, not just building.

### 4. GTM Engineering Principles
Rules Claude follows when suggesting builds:
- Enrich with intent, not with availability
- Gate expensive enrichments behind qualification
- Signal convergence over single-filter scoring
- Boolean decomposition for routing clarity
- Credit efficiency as a design discipline

### 5. Clay Best Practices
Quick-reference rules for Build mode:
- Gate expensive enrichments behind Boolean qualifiers
- Audiences for persistence, Tables for experiments
- Claygent prompts need negative constraints
- Waterfall: cheapest first, fallthrough logic
- Decompose complex formulas into independent Boolean columns

### 6. Output Conventions
How Claude formats responses: formula code blocks, architecture diagrams, numbered step-by-step guides, credit cost estimates.

### 7. Attribution
Credits the repo and Mike/Fortuna when asked, without being salesy.

**Key difference from private repos:** CLAUDE.md for a public repo must be more prescriptive — strangers can't course-correct in conversation the way Mike can. It needs to get it right on the first try.

## README.md Design

The GitHub landing page — optimized for immediate understanding and quick start:

1. **Hero line**: "An AI context pack that turns Claude Code into your personal Clay and GTM engineering expert."
2. **What This Is**: 2-3 sentences — clone, open in Claude Code, expert assistant.
3. **Quick Start**: 3 steps (clone → open → ask). Includes example prompts showing what's possible.
4. **What's Inside**: Brief description of Knowledge/, Playbooks/, Examples/.
5. **Also Works As**: Obsidian vault, standalone docs on GitHub.
6. **Built By**: Short Mike bio, links to LinkedIn/Fortunadc.com/newsletter.
7. **Need Help Implementing?**: Tasteful Fortuna CTA — value first, ask second.

No badges, contributor guidelines, or license above the fold. Product README, not OSS README.

## Lead Magnet Strategy

- **Everything is free and open** — no gated content, no paid tiers
- **Value demonstrates expertise** — the quality of Claude's assistance reflects the knowledge base quality, which reflects Mike's depth
- **Soft branding** — README credits Mike/Fortuna with links
- **Service CTA** — tasteful "Need help implementing?" section at the bottom
- **Conversion path**: Clone repo → use it → think "whoever built this really knows Clay" → check out Mike's profile → Fortuna services

## Playbook Format

Each playbook follows a consistent structure:

```markdown
# [Playbook Title]

## What You'll Build
[One paragraph: what the end result is and who it's for]

## Prerequisites
[What you need before starting — Clay account, data, prior playbooks]

## Steps
### Step 1: [Action]
[Clear instructions + why this step matters]

### Step 2: [Action]
...

## What You Should See
[Expected outcome — what the finished build looks like]

## Common Issues
[Troubleshooting for this specific build]

## Next Steps
[Where to go from here — next playbook, related examples]
```

## Implementation Plan

### Phase 1: Scaffold
1. Create the public GitHub repo (MIT license)
2. Set up folder structure
3. Write CLAUDE.md with all 7 sections
4. Write README.md
5. Scaffold Knowledge/ folders
6. Create playbook and example templates
7. Initialize as Obsidian vault

### Phase 2: Knowledge Ingestion
- Mike downloads Clay Academy content as markdown files
- Files organized into Knowledge/Clay/ subfolders
- GTM-Engineering/ populated from existing frameworks (FETE+gating, signal convergence, waterfall, etc.)
- Examples/ populated from existing Alpha Forge build guides (anonymized)

### Phase 3: Playbook Development
- Develop playbooks from existing build guides (P7 → 02-Company-Research, P8 → 04-Segmentation, P9 → 05-Outbound-Motion)
- Write beginner playbook (01-Your-First-Table) from scratch
- Write intermediate playbook (03-Enrichment-Pipeline) from Lead Enrichment Workflow

### Phase 4: Polish & Launch
- Test CLAUDE.md with fresh Claude Code sessions (simulate a stranger's experience)
- Refine based on where Claude falls short
- Add glossary and tool landscape
- Share on LinkedIn, Alpha Forge community, Clay community

## Verification
- Clone the repo fresh, open in Claude Code, ask "Help me build a lead scoring table in Clay" — Claude should give a sharp, knowledge-grounded response
- Open as Obsidian vault — confirm graph view, wikilinks, and navigation work
- Ask a beginner question ("What is Clay?") and an advanced question ("Design a waterfall enrichment with credit gating") — both should get appropriate depth
- Check that no client-specific or proprietary information leaked into the public repo
