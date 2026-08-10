# CLAUDE.md — Project 04: Compliance Co-Pilot

This file is project-level context for Claude Code. Read this before generating any deliverable (design system files, components, documentation) for this project.

---

## Project Overview

**Compliance Co-Pilot** is a speculative concept that extends Michael's real Credit Suisse Outside Business Interests (OBI) case study into a forward-looking vision of a multi-agent compliance workflow.

**Problem it explores:** Manual submission review with no visibility into the pipeline, no clear explanations for returns, no consolidated view of disclosure history.

**Solution concept:** Three specialized agents (research, policy-check, escalation) handle parts of submission review instead of purely manual processing. Every action is visible on a timestamped activity trail.

**Key fact:** This is a **speculative concept**, not a shipped product. It's a vision piece grounded in real OBI research.

---

## The Standing Lens: AI-Enhanced UX Process

This concept demonstrates all five phases:

1. **Research (2-5 days, AI-synthesized)**
   - Analyzed real OBI case study from prior engagement
   - Researched multi-agent AI architectures
   - Studied compliance officer trust factors

2. **Ideation (3-5 days, AI co-design)**
   - Designed three-agent architecture
   - Explored activity trail patterns
   - Iterated on agent transparency approaches

3. **Prototyping (5-10 days, AI-generated)**
   - Generated submission workflow wireframes
   - Designed activity trail UI
   - Built policy conflict screen
   - Created agent decision cards

4. **Concept Refinement (1-2 weeks)**
   - Validated design approach
   - Refined agent roles
   - Clarified escalation logic
   - **Not yet user-tested** (vision piece)

5. **Documentation (2-3 days)**
   - Generated concept specs
   - Documented agent responsibilities
   - Created architecture diagrams
   - Handed off as vision brief

---

## Core Design Claim

**"When more than one agent can act on a case, the UX problem shifts from 'is the AI right' to 'can the user tell who did what and why.' The activity trail isn't a feature bolted onto the workflow — it's the design's answer to that question."**

This is Michael's strategic insight: that **transparency scales** when multiple agents participate. The activity trail becomes the trust mechanism.

---

## Source of Truth: Briefs

All project content originates from paired brief files:

- `briefs/04-compliance-copilot.md` — **The brief**: UX Story, Strategy, Tactics, Solution, Design Rationale
- `briefs/04-compliance-copilot-discovery.md` — **The discovery doc**: OBI background, Pain Points, Research, Timeline
- `briefs/04-compliance-copilot-wireframes.md` — **Wireframe descriptions**: Submission detail, policy conflict screens
- `briefs/04-compliance-copilot-slides.md` — **Slide content**: Presentation narrative

Read both files together before generating output.

---

## Output Conventions

### Design System (Source of Truth: This Project's Design System)

This project has its own **independent design system** in the `design-system/` folder:

**Files:**
- `tokens.css` — Project-specific CSS tokens
- `design-system.md` — Complete specification
- `components.html` — Component library
- `README.md` — Design system overview

**Key principle:** Independent system. Does not inherit from container or AI portfolio.

**Color Philosophy:** Compliance/Formal theme
- Primary: Formal blues and grays (trust, authority)
- Agent indicators: Color-coded per agent (research=blue, policy=red, escalation=orange)
- Activity trail: Neutral with time-based visual hierarchy
- Typography: Poppins (consistent with all projects)

### Three-Agent Architecture to Document

The design system should support these agents:

1. **Research Agent** — Gathers context about the submitter
2. **Policy-Check Agent** — Analyzes submission against policies
3. **Escalation Agent** — Routes to appropriate reviewers

Each agent needs visual indicators, decision cards, and reasoning displays.

### Web Page & Slide Structure

When building the web page (`site/04-compliance-copilot.html`) or slides:

1. **Cover** — Title, tagline, compliance-themed quote
2. **Introduction** — "What's Compliance Co-Pilot?", Target audience (compliance managers), Problems, Role
3. **Discovery & Research** — KPI stats (targets, not measured), OBI background, Problem statement
4. **Pain Points** — Submissions returned with no explanation, no pipeline visibility, no history view
5. **Persona** — Risk & Compliance Manager card
6. **Framework** — Pain Points → Business Goals → UX Strategy → Features
7. **Design/Process** — Agent architecture, activity trail design, policy conflict handling
8. **Results** — Target KPIs (30% faster, 50% fewer returns, ≥80% trust)
9. **Key Insight** — Design Rationale (activity trail = trust mechanism)
10. **CTA** — Contact info

### Wireframe Descriptions

Screen-by-screen specs:
- Submission detail view with activity trail
- Policy conflict drill-down
- Agent decision cards
- Agent reasoning displays
- Override & logging flows
- Time-based activity visualization

---

## Mandatory Rule: Design Rationale Is the Differentiator

Every output must surface the brief's **Design Rationale**.

For this project: **"The activity trail isn't a feature bolted onto the workflow — it's the design's answer to the trust question."**

Show why transparency matters in multi-agent workflows. This separates vision from generic AI concepts.

---

## Important Note

**This is a speculative concept, not a shipped product.** It extends Michael's real OBI research into a forward-looking vision. No user testing results are fabricated or claimed. Design decisions are grounded in real OBI workflows but projected into a speculative multi-agent future.

---

## Design System Inheritance

**This project does NOT inherit** from container or AI portfolio design systems.

Authority hierarchy:
- Container: `../../design-system/` (reference only)
- AI Portfolio: `../design-system/` (reference only)
- This Project: `design-system/` (AUTHORITATIVE)

---

## Working Order for This Project

1. **Design System** (if not yet complete)
   - Define compliance-formal color palette
   - Document typography (Poppins)
   - Create agent decision cards, activity trail, policy conflict components
   - Build component library

2. **Web Page** (`site/04-compliance-copilot.html`)
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
- **Real OBI case study:** `../../briefs/02-meridian-exception-manager.md` (related work)
- **Project brief:** `../../briefs/04-compliance-copilot.md`
- **Web page:** `../../site/04-compliance-copilot.html`

---

## Key Concepts (From Discovery)

- **Three-agent architecture** (research, policy-check, escalation)
- **Activity trail** as trust mechanism
- **Agent transparency** critical for compliance
- **Target KPIs:** 30% faster cycle, 50% fewer returns, ≥80% trust
- **Grounded in real OBI** workflows

---

## Key Metrics (Targets, Not Measured)

- **~30% faster** review cycle (target)
- **~50% fewer** missing-info returns (target)
- **≥80% reviewer trust** target
- **100% audit trail** for compliance
- **Multi-agent transparency** foundation

---

**This is a speculative vision grounded in real research. Every design decision should reflect rigor while acknowledging the exploratory nature.**

Last updated: 2026-08-10
