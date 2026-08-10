# CLAUDE.md — Project 03: AI Pattern Library

This file is project-level context for Claude Code. Read this before generating any deliverable (design system files, components, documentation) for this project.

---

## Project Overview

**AI Pattern Library** is a design system and component library for AI-native product design. It defines reusable patterns for designing AI features across multiple products.

**Problem it addresses:** Most AI products re-invent the same wheels (loading indicators, error messages, confidence signals, handoff flows). How do you design consistently for AI states that don't exist in traditional UI?

**Key fact:** This is a design system project, not a shipping product. It's the conceptual foundation for AI UX patterns.

---

## The Standing Lens: AI-Enhanced UX Process

This project demonstrates the pattern library creation process:

1. **Research (2-5 days, AI-synthesized)**
   - Analyzed AI UX patterns from 50+ products
   - Extracted common pain points in AI interactions
   - Studied user trust factors in AI contexts

2. **Ideation (3-5 days, AI co-design)**
   - Brainstormed confidence signal approaches
   - Designed loading state variations
   - Explored source/citation formats
   - Iterated on error messaging

3. **Prototyping (5-10 days, AI-generated)**
   - Generated pattern components
   - Built interactive examples
   - Documented interaction flows
   - Created component spec sheets

4. **Testing (1-2 weeks, AI-analyzed)**
   - Tested pattern effectiveness with users
   - Measured trust in different confidence indicators
   - Analyzed error message effectiveness
   - Tested source citation clarity

5. **Handoff (2-3 days, auto-documented)**
   - Generated pattern documentation
   - Created usage guidelines
   - Built component library for developers
   - Handed off with copy templates

---

## Core Design Claim

**"AI UX is as much about communicating uncertainty as showing results. A confident wrong answer is worse than an honest 'I don't know.'"**

This is Michael's core insight: that **transparency > perfection** in AI interactions. The design system should make uncertainty visible and give users agency.

---

## Source of Truth: Briefs

All project content originates from paired brief files:

- `briefs/03-ai-pattern-library.md` — **The brief**: UX Story, Strategy, Tactics, Solution, Design Rationale
- `briefs/03-ai-pattern-library-discovery.md` — **The discovery doc**: Pain Points, Research, Timeline, Project Plan
- `briefs/03-ai-pattern-library-wireframes.md` — **Wireframe descriptions**: Pattern specs
- `briefs/03-ai-pattern-library-slides.md` — **Slide content**: Presentation narrative

Read both files together before generating output.

---

## Output Conventions

### Design System (Source of Truth: This Project's Design System)

This project has its own **independent design system** in the `design-system/` folder:

**Files:**
- `tokens.css` — Pattern library CSS tokens
- `design-system.md` — Complete specification
- `components.html` — Interactive pattern examples
- `README.md` — Library overview

**Key principle:** Independent system defining the visual language for AI patterns.

**Color Philosophy:** AI States theme
- Loading/thinking: Neutral/muted colors (grays, blues)
- Confidence: Color spectrum (red=low, yellow=medium, green=high)
- Error: Warm tones (reds, oranges)
- Success: Greens
- Typography: Poppins (consistent with all projects)

### Patterns to Document

The design system should define these 6 core patterns:

1. **Loading & Thinking States**
   - Animated indicators
   - "AI is thinking..." messaging
   - Cancellation options
   - Timeout handling (e.g., "Still thinking..." at various intervals)

2. **Confidence Signals**
   - Confidence percentage (0-100%)
   - Visual confidence indicators (color-coded)
   - Confidence explanations
   - Drill-down to sources

3. **Error & Uncertainty States**
   - "I'm not sure" vs. "I failed" distinction
   - Suggested alternatives
   - Escalation paths
   - Retry mechanisms

4. **Source & Citation Patterns**
   - Inline source links
   - Expandable source panels
   - Visual source indicators
   - Citation formats

5. **Human Handoff**
   - "Talk to a human" CTA
   - Handoff context
   - Queue position/wait time
   - Callback options

6. **Feedback & Learning**
   - "Was this helpful?" buttons
   - Explanation requests
   - Correction inputs
   - Privacy-aware feedback

### Web Page & Slide Structure

When building the web page (`site/03-ai-pattern-library.html`) or slides:

1. **Cover** — Title, tagline, design system quote
2. **Introduction** — "What's an AI Pattern Library?", Audience, Problem, Role
3. **Discovery & Research** — KPI stats (50+ products analyzed), Research methods, Problem statement
4. **Pain Points** — AI products re-invent wheels, inconsistent patterns
5. **Framework** — Pain Points → Business Goals → UX Strategy → Features
6. **Patterns** — Deep-dive on 6 core patterns with examples
7. **Design/Process** — Pattern research and validation
8. **Results** — Impact metrics (design acceleration, consistency, trust)
9. **Key Insight** — Design Rationale (transparency > perfection)
10. **CTA** — Contact info

---

## Mandatory Rule: Design Rationale Is the Differentiator

Every output must surface the brief's **Design Rationale**.

For this project: **"AI UX is as much about communicating uncertainty as showing results."**

Show why transparency matters. This differentiates from generic component libraries.

---

## Design System Inheritance

**This project does NOT inherit** from container or AI portfolio design systems.

This is the **reference design system** for AI patterns — other projects may reference it, but it stands alone.

---

## Working Order for This Project

1. **Design System** (if not yet complete)
   - Define AI States color palette (loading, confidence, error, success)
   - Document typography (Poppins)
   - Create 6 core pattern components
   - Build interactive pattern library

2. **Web Page** (`site/03-ai-pattern-library.html`)
   - Use design system tokens
   - All 10 sections
   - Include live pattern examples

3. **Slide Deck** (if needed)
   - Follow structure above
   - Surface Design Rationale

4. **Mark complete** when pattern library is complete and interactive

---

## References

- **This project's design system:** `design-system/` folder
- **Container design system:** `../../design-system/`
- **AI Portfolio design system:** `../design-system/`
- **Project brief:** `../../briefs/03-ai-pattern-library.md`
- **Web page:** `../../site/03-ai-pattern-library.html`

---

## Key Metrics (From Discovery)

- **50+ products** analyzed for pattern research
- **6 core patterns** identified across all AI products
- **Transparency over perfection** principle
- **Design acceleration** target (time saved per new AI feature)
- **Consistency** across products (brand assurance)
- **Trust improvement** (measurable via user research)

---

**This is a design system reference library. Every pattern should be production-ready and reusable.**

Last updated: 2026-08-10
