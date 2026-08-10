# CLAUDE.md — Project 01: Meridian Research Agent

This file is project-level context for Claude Code. Read this before generating any deliverable (design system files, components, documentation) for this project.

---

## Project Overview

**Meridian Research Agent** is a real, shipped conversational research agent embedded in Meridian (Anchorpoint Capital's investment operations platform). Analysts ask plain-language research questions, and the agent retrieves, synthesizes, and cites answers with confidence signals.

**Key fact:** This is a shipped v1 product, not a concept. All design decisions are grounded in real user research and shipped code.

---

## The Standing Lens: AI-Enhanced UX Process

This project demonstrates all five phases:

1. **Research (2-5 days, AI-synthesized)** 
   - Conducted interviews with investment operations analysts
   - Mapped manual research workflows to identify time sinks
   - Extracted decision patterns from real workflows

2. **Ideation (3-5 days, AI co-design)**
   - Designed agent behavior patterns
   - Explored confidence signal approaches
   - Iterated on "show sources by default" principle

3. **Prototyping (5-10 days, AI-generated)**
   - Generated wireframes and interaction flows
   - Built clickable prototypes for testing
   - Designed answer view and source expand screens

4. **Testing (1-2 weeks, AI-analyzed)**
   - Ran usability testing with real analysts
   - **Key Finding:** Analysts trusted the agent MORE when confidence was shown on every answer, not just low-confidence cases
   - Analyzed feedback patterns

5. **Handoff (2-3 days, auto-documented)**
   - Generated specs from test analysis
   - Created final wireframes and documentation
   - Handed off with audit trail visible

---

## Core Design Claim

**"The core design challenge wasn't making the agent accurate — it was getting a skeptical, detail-oriented analyst to actually act on an AI answer. Citations weren't an add-on; the citation was part of the answer."**

This is what separates this portfolio from generic "I used AI" narratives. Michael made a human judgment call that the AI couldn't have made alone: that **citations are evidence of reasoning**, not just documentation.

---

## Source of Truth: Briefs

All project content originates from paired brief files:

- `briefs/01-meridian-research-agent.md` — **The brief**: UX Story (Who/What/When/Why/How), Strategy, Tactics, Solution, Design Rationale
- `briefs/01-meridian-research-agent-discovery.md` — **The discovery doc**: Pain Points, Supporting Research, Timeline, Project Plan
- `briefs/01-meridian-research-agent-wireframes.md` — **Wireframe descriptions**: Screen-by-screen UI specs
- `briefs/01-meridian-research-agent-slides.md` — **Slide content**: Deck narrative

Read the brief and discovery doc together before generating any output. The brief gives narrative; the discovery doc gives evidence.

---

## Output Conventions

### Design System (Source of Truth: This Project's Design System)

This project has its own **independent design system** in the `design-system/` folder:

**Files:**
- `tokens.css` — Project-specific CSS custom properties (color palette, typography, spacing)
- `design-system.md` — Complete design specification
- `design-system-web.md` — Website-specific design specs (if applicable)
- `components.html` — Component library with working examples
- `README.md` — Design system overview

**Key principle:** This design system is INDEPENDENT. It does not inherit from the container or AI portfolio levels. It defines this project's unique visual identity.

**Color Philosophy:** Research theme
- Primary palette: Blues and teals (research/exploration colors)
- Accent colors: For confidence scores and citation highlights
- Neutral: Dark grays for text, light grays for backgrounds
- Typography: Poppins (consistent with all projects)

### Web Page & Slide Structure

When building the web page (`site/01-meridian-research-agent.html`) or slides, follow this structure:

1. **Cover** — Title, tagline, research-themed quote
2. **Introduction** — "What's the Research Agent?", Target audience (analysts), Problems, Role
3. **Discovery & Research** — KPI stats (45 min saved), Discovery methods, Problem statement
4. **Pain Points** — Numbered list + supporting quote from interviews
5. **Persona** — Investment operations analyst card (skeptical, detail-oriented)
6. **Framework** — Pain Points → Business Goals → UX Strategy → Feature Set (four-column)
7. **Design/Process** — Sprints & iterations with "What we learned" callout boxes
8. **Results** — KPI stats (82% acceptance, 12% escalation, 6% repeat-question)
9. **Key Insight** — Design Rationale (citations are evidence of reasoning)
10. **CTA** — Contact info

### Wireframe Descriptions

Screen-by-screen specs referencing UI elements named in the brief's Solution section:
- Query input field
- Answer view with citations inline
- Source expand panel
- Confidence score display
- Override workflow

Not full visual mockups — text descriptions detailed enough for a designer to build from.

---

## Mandatory Rule: Design Rationale Is the Differentiator

Every output — design system, web page, slide deck, wireframes — must trace back to and surface the brief's **Design Rationale** section.

For this project: **"Citations weren't an add-on; the citation was part of the answer."**

This shows Michael's competitive differentiator: the tradeoffs he weighed (confidence scores, source transparency, analyst skepticism) and the judgment call that citations = trust. Do not compress, omit, or bury this.

---

## Design System Inheritance

**Container Design System:** `/design-system/` (shared tokens)  
**AI Portfolio Design System:** `/ai-portfolio/design-system/` (shared AI patterns)  
**This Project's Design System:** `design-system/` (independent, unique palette)

**This project does NOT inherit from container or AI portfolio.** Its design system is self-contained and authoritative for all decisions in this project.

---

## Working Order for This Project

1. **Design System** (if not yet complete)
   - Define color palette (research theme: blues/teals)
   - Document typography (Poppins, weights/sizes)
   - Create component specs (citation card, confidence score, answer view)
   - Build component library

2. **Web Page** (`site/01-meridian-research-agent.html`)
   - Use design system tokens
   - All 10 sections structured
   - Responsive design (desktop, tablet, mobile)
   - Test mobile-first

3. **Slide Deck** (if needed)
   - Follow slide structure above
   - Use design system for consistency
   - Surface Design Rationale prominently

4. **Mark complete** when all deliverables use this project's design system consistently

---

## References

- **This project's design system:** `design-system/` folder
- **Container design system:** `../../design-system/`
- **AI Portfolio design system:** `../design-system/`
- **Project brief:** `../../briefs/01-meridian-research-agent.md`
- **Web page:** `../../site/01-meridian-research-agent.html`

---

## Key Metrics (From Discovery)

- **~45 minutes saved** per investigation workflow (real, measured)
- **~82% answer acceptance rate** (estimated)
- **~12% escalation rate** (healthy signal — some cases need human judgment)
- **~6% repeat-question rate** (estimated)
- **4-5 systems** analysts used to check manually
- **0-system workflow** with agent (all data synthesized)

---

**This is a real, shipped project. Every design decision should reflect that rigor and grounding in user research, not speculation.**

Last updated: 2026-08-10
