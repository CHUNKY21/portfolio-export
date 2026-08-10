# CLAUDE.md — AI UX Portfolio Project

This file is project-level context for Claude Code. Read this before generating any deliverable (slides, web pages, wireframes) for this portfolio.

## Project Overview

Michael Thibodeau is building a UX/AI portfolio for job applications in UX and AI-integrated product design roles, drawing on 15+ years in financial services (Wells Fargo, Credit Suisse, UBS, American Express, ADP, E*Trade). The portfolio consists of 5 case study concepts, delivered as both a PDF deck and an interactive Squarespace web page. The portfolio's production process is itself part of the story: it is being built using Claude and Claude Code, which is a live demonstration of the AI-Enhanced UX process described below.

## The Standing Lens: AI-Enhanced UX Process

Every deliverable in this project — slides, web copy, wireframe descriptions, timelines — must be framed through this process model. This is the throughline that ties all 5 case studies together and should never be lost in production.

**Traditional UX Process:**
Research (2-4 wks) → Wireframing (3-5 wks) → Prototyping (4-6 wks) → Testing (3-4 wks) → Handoff (2-3 wks)
Total: 4-6 months. Tools: Figma, UserTesting, Miro, manual synthesis.

**AI-Enhanced UX Process:**
Research, AI-synthesized (2-5 days) → Ideation, AI co-design (3-5 days) → Prototyping, AI-generated (5-10 days) → Testing, AI-analyzed (1-2 wks) → Handoff, auto-documented (2-3 days)
Total: 1.5-2 months. Tools: Claude, Claude Code, Claude API, Figma.

**The core claim, stated consistently everywhere:** AI amplifies human judgment — it does not replace it. Every case study must show a moment where a human (Michael, or the persona in the case study) made a judgment call that the AI could not have made alone. This is what separates the portfolio from a generic "I used AI" narrative.

When generating any deliverable, map its content back to these five phases (Research → Ideation → Prototyping → Testing → Handoff) using this exact phase language — don't invent new phase names per case study.

## Source of Truth: /portfolio/briefs/

All case study content originates from `/portfolio/briefs/`. Do not invent case study facts, metrics, or narrative details that aren't grounded in these files.

Each of the 5 concepts has **two paired files**:
- `NN-concept-name.md` — the **brief**: UX Story (Who/What/When/Why/How), Strategy, Tactics, Solution, Design Rationale
- `NN-concept-name-discovery.md` — the **discovery doc**: Pain Points (pre-redesign), Supporting Research, Timeline, Project Plan

Always read both files for a concept together before generating output. The brief gives the narrative; the discovery doc gives the evidence and process that justify it. `00-index.md` is the directory's map — read it first if orienting to the whole project.

## Output Conventions

### Design Style Guide (source of truth: ThibodeauCaseB2B26.pdf)
This is Michael's existing, shipped portfolio deck style — match it exactly rather than inventing new visual language. Approximate tokens below; refine against the source PDF if exact hex values are needed.

**Colors:**
- Rust/burnt orange (section dividers, headers): `#C1592E`
- Coral/orange gradient (cover + closing banner, with faint circular line texture): `#FF9966` → `#FF7E63` → `#FFB088`
- Teal (target audience badge): `#1B9E96`
- Green (positive callout boxes — "what we learned"): `#3CAA6E`
- Red/pink (pain points column, "unexpected challenge" callouts): `#D9534F`
- Blue (business goals column, some KPI stats): `#3B9FD4`
- Purple (feature set / UX strategy column): `#7B5AA6`
- Magenta (KPI stat accent): `#C23B8F`
- Lime green (cover left-edge vertical accent bar): `#C4E538`
- Body text: dark gray, near-black. Labels/breadcrumbs: mid gray.
- Background: white throughout, except section dividers (solid rust) and cover/closing (white body + gradient banner).

**Typography:** thin/light geometric sans-serif (title treatment resembles Century Gothic or similar light-weight geometric sans). Titles are large and light-weight, never bold-heavy. Body copy is a standard clean sans-serif at normal weight.

**Recurring structural components — use these, not generic slide layouts:**
- **Breadcrumb header**: small gray text top-left on every content slide, format `Section Name   Project Title` (e.g., "Discovery & Research   Compliance Alert Triage Copilot")
- **Cover slide**: white background, thin coral title top-right-aligned, one-line description beneath, author name/site bottom-right, and a full-width coral/orange gradient banner with subtle circular line texture across the bottom third; a lime-green and rust vertical bar sits at the far left edge
- **Section divider slides** (e.g., "Discovery", "Design"): solid rust background (`#C1592E`), white title text, supporting paragraph in lighter white/gray
- **KPI stat blocks**: no borders or boxes — just an oversized number in a distinct accent color (rotate through blue/magenta/teal/green across a slide's stats) with a small gray label beneath. Use for "Why redesign X" / results slides.
- **Target audience badge**: a filled teal circle containing a short bulleted list, floated beside body text
- **Pain Points → Business Goals → UX Strategy → Feature Set framework**: four solid-color rectangular columns (red, blue, green, purple respectively) with white bullet-point text inside each, connected by `+` and `=` glyphs between columns — this is the canonical way to show how research became a feature set, use it whenever a case study's Tactics/Solution need this synthesis shown visually
- **Insight callout boxes** during process/design-sprint slides: solid green box for "What we learned" content, solid red box for "Unexpected Challenge" content — always paired with a supporting screenshot or sketch beside them
- **Persona cards**: bordered rectangular card, headshot photo, name/role/tenure, a short italicized sentiment quote, then Responsibilities / Key Challenges & Areas of Concern / Wishlist as labeled bullet lists
- **Quotes**: centered, italic, understated gray text — used sparingly, one per relevant slide, pulled from research findings

### PDF Slide Structure
Each case study compiles to slides in this order, following the structural components above:
1. Cover treatment: title, tagline, one-line description, quote pulled from discovery pain points (matches the deck's opening pattern of Project Name → tagline → description → pull-quote)
2. Introduction: "What's X?" description + Target audience (teal badge) + The problems (bulleted) + My Role
3. Discovery & Research: "Why redesign X?" KPI stat blocks (from discovery Timeline/Research, use real or flagged-placeholder numbers), Discovery methods list + Problem statement
4. Pain points from interviews (numbered list) + supporting quote
5. Persona card(s) — reference the audience from the brief's `audience` field
6. Pain Points + Business Goals + UX Strategy = Feature Set (the four-column framework, built from brief Tactics/Strategy/Solution)
7. Design: sprint-by-sprint sections showing iterations, each with a green "what we learned" or red "unexpected challenge" callout box — map these iterations to the AI-Enhanced UX Process phases (Research/Ideation/Prototyping/Testing/Handoff) from the standing lens above, explicitly naming where Claude/Claude Code did the work
8. Results: KPI stat blocks (final metrics)
9. Key Insight / Design Rationale — per the mandatory rule below, must remain prominent, doesn't have to force itself into the KPI-stat visual pattern; can use the quote/pull-quote treatment for emphasis

### Squarespace HTML Conventions
- Single self-contained HTML block per section (inline `<style>`, no external dependencies except system fonts)
- Responsive: single-column stacking below 768px
- Reproduce the same structural components as the PDF (breadcrumb headers, section dividers, KPI stat blocks, the four-column framework, callout boxes, persona cards) using the same color tokens — the web and PDF versions should look like the same design system, not two different ones
- Case study cards on the index/landing page can simplify to title + tagline + 2-3 KPI stat blocks; full detail pages carry the complete structural set
- CTA section at the end of every page (contact email / LinkedIn), can reuse the coral gradient banner treatment from the cover

### Wireframe Descriptions
Structured, screen-by-screen, referencing specific UI elements named in the brief's Solution section (e.g., "alert card," "confidence score," "insight card"). Not full visual mockups — text descriptions detailed enough for a designer (or an AI image/design tool) to build from.

## Mandatory Rule: Design Rationale Is the Differentiator

Every output — every slide deck, every web page, every wireframe set — must trace back to and surface the brief's **Design Rationale** section. This is Michael's competitive differentiator: it shows the tradeoffs he weighed, not just what he shipped. Do not compress, omit, or bury this section in production. If a deliverable format is short on space, cut other content before cutting Design Rationale.

## Working Order

Concepts should be completed one at a time, fully, before moving to the next: wireframes → metrics table → visual assets → slide deck section → web page → mark `status: complete`. See each brief's frontmatter `status` field and the `skills/` directory for the repeatable procedures used at each step.

## References

- Design system (website/live-site edition): See `/docs/design-system.md` — follow these visual specifications for all Squarespace/web UI work. Pixel-accurate to the live site at michaeljthibodeau.com; do not hardcode colors, font sizes, spacing, or shadows. Visual reference: `design-system-visual.html` in the project root.
- Design system (PDF deck edition): See `design-system/design-system.md` — use for the downloadable PDF only, not the web pages.
