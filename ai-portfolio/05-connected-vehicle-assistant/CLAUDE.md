# CLAUDE.md — Project 05: Connected Vehicle Assistant

This file is project-level context for Claude Code. Read this before generating any deliverable (design system files, components, documentation) for this project.

---

## Project Overview

**Connected Vehicle Assistant** is a speculative concept exploring ambient AI in automotive contexts. The vision: proactive AI support that surfaces insights contextually — at the right time, in the right modality — without interruption or cognitive load.

**Problem it explores:** Drivers need proactive support (route optimization, maintenance alerts, fuel advice) but can't take attention off the road. Push notifications interrupt; in-vehicle systems compete for attention.

**Solution concept:** Ambient AI assistant that anticipates what drivers need before they ask, surfacing insights contextually through appropriate modalities (visual, haptic, voice) based on driving context and confidence levels.

**Key fact:** This is a **speculative vision piece** grounded in research. Not tested in real vehicles.

---

## The Standing Lens: AI-Enhanced UX Process

This concept demonstrates all five phases:

1. **Research (2-5 days, AI-synthesized)**
   - Analyzed driver attention patterns
   - Researched in-vehicle UX best practices
   - Studied push notification fatigue
   - Reviewed safety guidelines

2. **Ideation (3-5 days, AI co-design)**
   - Designed anticipation algorithms
   - Explored modality matching approaches
   - Debated confidence thresholds
   - Prototyped information hierarchies

3. **Prototyping (5-10 days, AI-generated)**
   - Generated in-vehicle screen designs
   - Created gesture/interaction flows
   - Designed voice interaction patterns
   - Built decision trees for information surfacing

4. **Concept Refinement (1-2 weeks)**
   - Validated design safety assumptions
   - Refined confidence scoring logic
   - Adjusted urgency modalities
   - **Not real-world tested** (vision piece)

5. **Documentation (2-3 days)**
   - Generated concept specs
   - Documented anticipation rules
   - Created modality matrix
   - Handed off as vision brief

---

## Core Design Claim

**"Push AI works when it's high-confidence, relevant, and respectful of attention. The goal is to anticipate what the driver needs before they ask, not to interrupt with unnecessary alerts."**

This is Michael's insight: that **ambient intelligence requires discipline**. Not every prediction surfaces. Only high-confidence, contextually-appropriate insights break through.

---

## Source of Truth: Briefs

All project content originates from paired brief files:

- `briefs/05-connected-vehicle-assistant.md` — **The brief**: UX Story, Strategy, Tactics, Solution, Design Rationale
- `briefs/05-connected-vehicle-assistant-discovery.md` — **The discovery doc**: Driver workflows, Pain Points, Research, Timeline
- `briefs/05-connected-vehicle-assistant-wireframes.md` — **Wireframe descriptions**: In-vehicle screen specs
- `briefs/05-connected-vehicle-assistant-slides.md` — **Slide content**: Presentation narrative

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

**Key principle:** Independent system optimized for in-vehicle context.

**Color Philosophy:** Minimalist/Safety theme
- High contrast for visibility in bright sunlight
- Calming colors (blues, greens) for non-urgent information
- Warm tones (amber, orange) for caution/attention
- Reds reserved for safety-critical information only
- Typography: Poppins (large, readable from distance)

### Ambient AI Principles to Document

The design system should enforce these 5 principles:

1. **Anticipation Over Reaction** — Predict what drivers need before they ask
2. **Modality Matching** — Different channels for different urgency levels
3. **High Confidence Only** — Push only when 80%+ confident
4. **Graceful Transparency** — Explain why when the assistant acts
5. **Always Optional** — Drivers can override or disable

### Web Page & Slide Structure

When building the web page (`site/05-connected-vehicle-assistant.html`) or slides:

1. **Cover** — Title, tagline, automotive-themed quote
2. **Introduction** — "What's Connected Vehicle Assistant?", Target audience (drivers), Problems, Role
3. **Discovery & Research** — KPI stats (attention load reduction), Research methods, Problem statement
4. **Pain Points** — Need proactive support without distraction, competing in-vehicle systems
5. **Framework** — Pain Points → Business Goals → UX Strategy → Features
6. **Design/Process** — Anticipation algorithms, modality matching, confidence thresholds
7. **Results** — Target KPIs (proactive support, reduced load, higher adoption)
8. **Key Insight** — Design Rationale (ambient intelligence requires discipline)
9. **CTA** — Contact info

### Wireframe Descriptions

Screen-by-screen specs:
- Ambient display patterns (heads-up, dashboard, voice)
- Context-aware information surfaces
- Interaction modalities (voice, haptic, visual)
- Safety constraints and guardrails
- Information hierarchies by urgency/confidence

---

## Mandatory Rule: Design Rationale Is the Differentiator

Every output must surface the brief's **Design Rationale**.

For this project: **"Push AI works when it's high-confidence, relevant, and respectful of attention."**

Show why discipline matters. Not every prediction should surface. This differentiates from naive push notification approaches.

---

## Important Note

**This is a speculative vision piece, not a shipped product.** It explores what proactive, ambient AI in vehicles *could* look like. The design is grounded in research (driver attention, HCI, vehicle safety) but hasn't been tested in real vehicles. No feasibility claims are made.

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
   - Define minimalist/safety-focused color palette
   - Document typography (Poppins, large for readability)
   - Create modality-specific components (heads-up, voice, haptic)
   - Build component library with safety guardrails

2. **Web Page** (`site/05-connected-vehicle-assistant.html`)
   - Use design system tokens
   - All 10 sections
   - Responsive design (works on phone, tablet for web version)

3. **Slide Deck** (if needed)
   - Follow structure above
   - Surface Design Rationale

4. **Mark complete** when all deliverables use project design system

---

## References

- **This project's design system:** `design-system/` folder
- **Container design system:** `../../design-system/`
- **AI Portfolio design system:** `../design-system/`
- **Project brief:** `../../briefs/05-connected-vehicle-assistant.md`
- **Web page:** `../../site/05-connected-vehicle-assistant.html`

---

## Key Principles (From Discovery)

- **Anticipation** — Predict driver needs
- **High confidence only** — 80%+ threshold for pushing information
- **Modality matching** — Visual/haptic/voice by urgency
- **Graceful transparency** — Explain AI reasoning
- **Driver agency** — Always optional, always overridable
- **Safety first** — Never pull attention from road

---

## Key Concepts (Speculative Targets)

- **Route optimization** insights (time savings, fuel efficiency)
- **Maintenance alerts** (proactive, not reactive)
- **Fuel optimization** (real-time suggestions)
- **Modality modes:** Visual (dashboard), Haptic (wheel/seat), Voice (ambient), Heads-up (limited)
- **Confidence thresholds:** 80%+ for push, <60% suppressed
- **Context awareness:** Speed, traffic, navigation state, time of day

---

**This is a speculative vision grounded in research and UX best practices. Every design decision should reflect rigor while acknowledging the exploratory nature and lack of real-world validation.**

Last updated: 2026-08-10
