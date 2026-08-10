---
name: slide-builder
description: Build a 7-8 slide case study sequence from a paired brief + discovery file in /portfolio/briefs/. Use this whenever the user asks to turn a case study concept into slides, build the deck, create the PDF section for a concept, or generate slide content for any of the 5 portfolio concepts. Always use this skill rather than freehand slide-writing to keep all 5 case studies structurally consistent.
---

# Slide Builder

Converts one case study concept (a brief + discovery file pair from `/portfolio/briefs/`) into a structured 7-8 slide sequence, ready to drop into the PDF deck.

## Before You Start

1. Read `/portfolio/CLAUDE.md` if you haven't already this session — it defines the AI-Enhanced UX Process phase language and the Design Style Guide (colors, typography, and the recurring structural components: breadcrumb headers, section dividers, KPI stat blocks, the four-column Pain Points/Business Goals/UX Strategy/Feature Set framework, callout boxes, persona cards) every slide must follow.
2. Read both files for the target concept: `NN-concept-name.md` (brief) and `NN-concept-name-discovery.md` (discovery).
3. Confirm which concept you're building if it's ambiguous — don't guess between the 5.

## Slide Sequence

Build the sequence defined in CLAUDE.md's "PDF Slide Structure" section, using the structural components it defines rather than generic title/body slides. In brief:

**Cover** — title, tagline, one-line description, a pull-quote drawn from discovery's Pain Points, in the cover treatment (coral gradient banner, thin title).

**Introduction** — "What's [Concept]?" description, Target audience in the teal badge component (pull from brief `audience` field), The problems (bulleted, from discovery Pain Points), My Role framed as if Michael led this project.

**Discovery & Research** — "Why redesign this?" using the KPI stat block component with metrics from discovery's Timeline/Research section. If exact numbers aren't in source files, flag with `[METRIC NEEDED: description]` rather than fabricating a figure — do not invent precise numbers to fill the stat-block pattern. Include Discovery methods list and the brief's problem statement (synthesize from UX Story Why).

**Pain points from interviews** — numbered list pulled directly from discovery's Pain Points, plus one supporting pull-quote.

**Persona card** — build using the bordered card component (name/role/quote/responsibilities/challenges/wishlist) for the primary audience named in the brief.

**Pain Points + Business Goals + UX Strategy = Feature Set** — the four-column framework component. Column 1 (red) = discovery Pain Points, Column 2 (blue) = business goals synthesized from the brief's Strategy, Column 3 (green) = UX Strategy bullets from brief Tactics, Column 4 (purple) = Feature Set from brief Solution/Solution Highlights.

**Design/Process sprints** — map brief Tactics + discovery Supporting Research onto the AI-Enhanced UX Process phases (Research → Ideation → Prototyping → Testing → Handoff, exact language from CLAUDE.md). For each phase, explicitly name where Claude or Claude Code did the work and what human judgment call happened alongside it, and use the green "What we learned" / red "Unexpected Challenge" callout-box components where the source material supports a specific insight or complication. Include a time comparison where discovery's Timeline supports it (e.g., "40 hours manual → 4 hours with AI synthesis").

**Results** — KPI stat block component with final metrics from brief/discovery. Same rule: flag missing numbers, never fabricate.

**Key Insight** — the brief's **Design Rationale** section, adapted to the quote/pull-quote treatment for emphasis. Per CLAUDE.md's mandatory rule: this must survive intact even if other slides get trimmed for space.

Note where a wireframe/visual/screenshot should be inserted with `[VISUAL: description]` placeholders — this skill does not generate images, only marks where they belong.

## Output Format

Deliver as a markdown document with clear `## [Component Name] — [Slide Purpose]` headers (e.g., `## Section Divider — Discovery`, `## KPI Stat Block — Results`), naming which structural component from the style guide each slide uses, so it can be reviewed before being converted to actual PDF/deck software.

## Consistency Check (do this before finishing)

- [ ] All 8 slides present, in order
- [ ] Phase language matches CLAUDE.md exactly (Research/Ideation/Prototyping/Testing/Handoff)
- [ ] Design Rationale slide is present and substantive, not trimmed
- [ ] No fabricated metrics — flagged placeholders used where source data is missing
- [ ] Visual placeholders marked where wireframes/mockups will go
