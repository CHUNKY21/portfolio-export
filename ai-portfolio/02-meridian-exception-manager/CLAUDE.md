# CLAUDE.md — Project 02: Meridian Exception Manager

This file is project-level context for Claude Code. Read this before generating any deliverable (design system files, components, documentation) for this project.

---

## Project Overview

**Meridian Exception Manager** is a real, shipped AI layer that detects, prioritizes, and proposes remediation for operational exceptions in Anchorpoint Capital's investment operations workflow.

**Problem it solved:** Operational exceptions arrived as a flat queue with no prioritization, routing, or context. Analysts spent time manually sorting before investigation.

**Key fact:** This is a shipped v1 product demonstrating **push AI** — AI that surfaces what to do next, not what went wrong.

---

## The Standing Lens: AI-Enhanced UX Process

This project demonstrates all five phases:

1. **Research (2-5 days, AI-synthesized)**
   - Analyzed 6+ months of exception logs
   - Interviewed analysts on triage workflows
   - Extracted decision patterns from historical data

2. **Ideation (3-5 days, AI co-design)**
   - Designed push notification vs. worklist patterns
   - Explored confidence-score presentation
   - Iterated on proposal clarity vs. brevity

3. **Prototyping (5-10 days, AI-generated)**
   - Generated exception list & detail screens
   - Designed AI proposal cards
   - Built interactive prototypes

4. **Testing (1-2 weeks, AI-analyzed)**
   - Tested with real analysts
   - Measured time-to-action improvements
   - Analyzed override patterns (feedback signals)

5. **Handoff (2-3 days, auto-documented)**
   - Generated specs and interaction documentation
   - Created exception handling playbooks
   - Handed off with confidence scoring logic

---

## Core Design Claim

**"Push AI works when it surfaces what to do next (the proposal) without requiring an explanation of what went wrong. The goal is action, not education."**

This is Michael's human judgment: that **proposals trump diagnoses** in the context of time-constrained analyst workflows. The AI doesn't need to explain why; it needs to say what to do.

---

## Source of Truth: Briefs

All project content originates from paired brief files:

- `briefs/02-meridian-exception-manager.md` — **The brief**: UX Story, Strategy, Tactics, Solution, Design Rationale
- `briefs/02-meridian-exception-manager-discovery.md` — **The discovery doc**: Pain Points, Research, Timeline, Project Plan
- `briefs/02-meridian-exception-manager-wireframes.md` — **Wireframe descriptions**: Screen-by-screen UI specs
- `briefs/02-meridian-exception-manager-slides.md` — **Slide content**: Deck narrative

Read both files together before generating output.

---

## Output Conventions

### Design System (Source of Truth: This Project's Design System)

This project has its own **independent design system** in the `design-system/` folder:

**Files:**
- `tokens.css` — Project-specific CSS custom properties
- `design-system.md` — Complete design specification
- `design-system-web.md` — Website-specific design specs (if applicable)
- `components.html` — Component library
- `README.md` — Design system overview

**Key principle:** Independent design system. Does not inherit from container or AI portfolio.

**Color Philosophy:** Operations theme
- Primary palette: Warm tones for urgency/action (oranges, reds, ambers)
- Accent colors: For priority levels and remediation highlights
- Neutral: Dark text, light backgrounds
- Typography: Poppins (consistent with all projects)

### Web Page & Slide Structure

When building the web page (`site/02-meridian-exception-manager.html`) or slides:

1. **Cover** — Title, tagline, operations-themed quote
2. **Introduction** — "What's the Exception Manager?", Target audience (operations analysts), Problems, Role
3. **Discovery & Research** — KPI stats (40% time saved target), Discovery methods, Problem statement
4. **Pain Points** — Flat queue, no prioritization, no routing, no context
5. **Persona** — Operations analyst card (efficiency-focused, overloaded)
6. **Framework** — Pain Points → Business Goals → UX Strategy → Feature Set
7. **Design/Process** — Sprints with callout boxes on discovery insights
8. **Results** — KPI stats (~40% faster review, ~50% fewer returns, ≥80% trust)
9. **Key Insight** — Design Rationale (proposals trump diagnoses)
10. **CTA** — Contact info

### Wireframe Descriptions

Screen-by-screen specs:
- Exception list view (prioritized & routed)
- Exception detail view (with AI proposals)
- Remediation confirmation flow
- Priority level indicators
- Routing logic visualization

Text descriptions detailed enough for designer implementation.

---

## Mandatory Rule: Design Rationale Is the Differentiator

Every output must surface the brief's **Design Rationale**.

For this project: **"Push AI works when it surfaces what to do next without requiring an explanation of what went wrong."**

Show Michael's judgment call: why proposals matter more than diagnoses in this workflow. This differentiates from generic AI automation narratives.

---

## Design System Inheritance

**This project does NOT inherit** from container or AI portfolio design systems.

**Authority hierarchy:**
- Container: `../../design-system/` (reference only)
- AI Portfolio: `../design-system/` (reference only)
- This Project: `design-system/` (AUTHORITATIVE for this project)

---

## Working Order for This Project

1. **Design System** (if not yet complete)
   - Define operations-themed color palette
   - Document typography (Poppins)
   - Create exception card, proposal card, priority level components
   - Build component library

2. **Web Page** (`site/02-meridian-exception-manager.html`)
   - Use design system tokens
   - All 10 sections
   - Responsive design

3. **Slide Deck** (if needed)
   - Follow structure above
   - Surface Design Rationale

4. **Mark complete** when all deliverables use project design system

---

## References

- **This project's design system:** `design-system/` folder
- **Container design system:** `../../design-system/`
- **AI Portfolio design system:** `../design-system/`
- **Project brief:** `../../briefs/02-meridian-exception-manager.md`
- **Web page:** `../../site/02-meridian-exception-manager.html`

---

## Key Metrics (From Discovery)

- **~40% faster** review cycle (target)
- **~50% fewer** missing-info returns (target)
- **≥80% reviewer trust** target
- **Multi-step exceptions** routed automatically
- **Confidence scores** on every proposal
- **Override logging** for feedback loop

---

**This is a real, shipped product. Every design decision should reflect production-level rigor.**

Last updated: 2026-08-10
