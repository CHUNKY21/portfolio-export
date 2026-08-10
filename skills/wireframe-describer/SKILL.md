---
name: wireframe-describer
description: Produce structured, screen-by-screen wireframe descriptions from a brief's Solution section in /portfolio/briefs/. Use this whenever the user asks to describe wireframes, plan mockup screens, define UI elements, or prep design specs for any of the 5 portfolio concepts before actual visual design work begins. This skill produces text descriptions, not images — use it as the input for manual mockup work or an image/design generation tool.
---

# Wireframe Describer

Converts a case study's Solution section (from its brief in `/portfolio/briefs/`) into structured, screen-by-screen wireframe descriptions detailed enough for manual design work or an AI design tool to build from.

## Before You Start

1. Read `/portfolio/CLAUDE.md` if you haven't already this session — for brand tokens and the standing AI-Enhanced UX process framing.
2. Read the target concept's brief file (`NN-concept-name.md`), focusing on the **Solution** and **Solution Highlights** sections.
3. Also read the paired discovery file's Pain Points section — wireframes should visibly resolve the specific frustrations named there, so each screen should trace back to a pain point it fixes.

## What This Skill Does NOT Do

This skill produces text descriptions of screens, not visual mockups or images. Do not attempt to generate actual pixel layouts, SVG mockups, or image files here — that's a separate design step. The output of this skill is the *spec* that feeds that step.

## Per-Screen Description Structure

For each screen implied by the brief's Solution section, produce:

**Screen name** (e.g., "Alert Triage Queue", "Insight Card Detail View")

- **Purpose**: One sentence — what problem does this screen solve, tied explicitly to a named pain point from the discovery file
- **Key elements**: Bullet list of UI components (e.g., "confidence score badge," "evidence drill-down panel," "officer override button") — use the exact terminology from the brief's Solution section, don't invent new component names
- **Primary user action**: What is the user doing on this screen, and what happens next
- **AI-generated content vs. static UI**: Explicitly separate what's AI-populated (e.g., risk scores, natural-language explanations, recommended actions) from static interface chrome — this distinction matters for the portfolio's "AI amplifies judgment" narrative
- **State variations**: Note if the screen needs multiple states (e.g., empty state, loading, high-confidence vs. low-confidence result, error/override state)

## How Many Screens

Most concepts imply 3-5 core screens. Don't pad the list — only describe screens that are actually implied by the brief's Solution section and Solution Highlights. If the brief is vague about a screen's structure, flag it rather than inventing detail: `[UNDERSPECIFIED: brief does not detail X — confirm with Michael before designing]`.

## Output Format

Deliver as a markdown document with `## Screen: [Name]` headers per screen, in the logical order a user would move through them (entry point first). Include a one-line summary at the top listing all screens covered.

## Consistency Check (do this before finishing)

- [ ] Every screen ties back to a specific pain point from the discovery file
- [ ] Component terminology matches the brief's Solution section exactly (no invented names)
- [ ] AI-generated vs. static content is explicitly distinguished on each screen
- [ ] Underspecified areas are flagged, not silently filled in
- [ ] Screen order follows a logical user flow
