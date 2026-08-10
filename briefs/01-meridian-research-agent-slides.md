# Slides — Meridian Research Agent (Epic 1)
Source: `01-meridian-research-agent.md` (brief) + `01-meridian-research-agent-discovery.md` (discovery — real, shipped work). The ~45-minutes-saved figure is real and sourced (from Michael's resume, per the discovery doc) and is presented as such, unlabeled. Three secondary metrics named in the brief have no sourced number in this project's files — those are filled with illustrative estimates, explicitly labeled. Two pull-quotes are illustrative (no verbatim interview quotes exist in source files) and labeled as such.

---

## Section Divider / Cover — Meridian Research Agent

- **Title**: Meridian Research Agent
- **Tagline**: A conversational research agent for investment operations — real, shipped v1
- **One-line description**: Analysts used to manually cross-reference five-plus internal systems to investigate a discrepancy. The agent now takes a plain-language question, retrieves from connected sources, and returns a cited, confidence-scored answer.
- **Pull-quote** *(illustrative — reasoned from discovery pain point #1, not a verbatim quote)*: "I'd have four systems open just to answer one question — and I still wasn't sure I had the full picture."
- **Treatment**: coral gradient banner (`#F5805C` → `#FF8C7A` → `#FFB088`), thin title typography, lime/rust accent bars

---

## Introduction — What's the Meridian Research Agent?

- **Description**: A conversational agent embedded in Meridian (Anchorpoint Capital's investment operations platform) that retrieves, synthesizes, and cites answers to plain-language research questions.
- **Target audience** (teal circle-callout): Investment operations analyst / accounting ops user, mid-to-senior level (brief WHO → Primary persona)
- **The problems** (bulleted, from discovery Pain Points):
  1. Manually opening 4-5 systems for a single research question
  2. No consistent starting point — every analyst improvises their own process
  3. No way to show your work after the fact — answers aren't auditable
  4. Repetitive, low-judgment lookups take the same time as genuinely hard investigations
- **My Role**: Led the design process for this concept, from discovery interviews through the shipped v1 experience.

---

## KPI Stat Block — Discovery & Research

- **"Why build this?"**
- **~45 minutes saved per investigation workflow** *(real, sourced metric — from Michael's resume, per the discovery doc)*
- **Discovery methods** (real): interviews with investment operations analysts across experience levels, plus their team lead; manual workflow mapped step by step
- **Problem statement** (from brief WHAT → Problem): analysts manually pull data from multiple internal systems to answer a research question or investigate a discrepancy — slow, repetitive, and inconsistent in quality depending on who does it

---

## Pain Points from Interviews

1. Manually opening 4-5 systems for a single research question
2. No consistent starting point — every analyst improvises their own process
3. No way to show your work after the fact — answers aren't auditable
4. Repetitive, low-judgment lookups take the same time as genuinely hard investigations

**Pull-quote** *(illustrative — reasoned from pain point #3, not a verbatim quote)*: "If I can't show where an answer came from, I can't actually use it in a regulated environment."

---

## Persona Card — Investment Operations Analyst

- **Name/Role**: primary persona, investment operations analyst / accounting ops user (per brief WHO)
- **Sentiment**: *(grounded in a real discovery finding, not invented)* — discovery doc states this group is "detail-oriented and default-skeptical of anything they can't verify," which became the central design constraint
- **Responsibilities**: investigating discrepancies, answering ad hoc research questions, escalating high-stakes findings to the team lead
- **Key challenges**: assembling context across multiple systems with no single source of truth; producing answers that hold up to audit
- **Wishlist**: a sourced, verifiable answer faster than the manual process, without sacrificing traceability

---

## Four-Column Framework — Pain Points + Business Goals + UX Strategy = Feature Set

| Pain Points (red `#DF505C`) | Business Goals (blue `#8AD9F8`) | UX Strategy (green `#41854F`) | Feature Set (purple `#7C417E`) |
|---|---|---|---|
| Manually opening 4-5 systems per question | Reduce time-to-resolution on research/investigation tasks | Show sources by default, not on request | Plain-language query input |
| No consistent starting point across analysts | Consistent, trustworthy answers regardless of who's asking | Signal confidence on every answer, not just low-confidence ones | Cited answer format |
| Answers aren't auditable after the fact | | Define an explicit boundary: what the agent owns vs. what stays human-gated | Confidence/certainty signal |
| Repetitive lookups take as long as hard investigations | | | Show-your-work expand-to-source, fallback/handoff state |

---

## Design/Process — 8-Stage AI-Enhanced UX Process

- **Discovery & Research**: Same as always — interviews with analysts and their team lead, manual workflow mapped step by step. New in AI-native version: explicitly mapped what the underlying data sources could plausibly answer with confidence vs. what required human judgment.
- **Problem Definition**: Same as always — synthesized the four pain points above. New: separated "the workflow is slow" (an agent can help) from "I don't trust unverifiable output" (only interaction design solves this).
- **Competitive / Pattern Analysis**: Real — benchmarked adjacent AI-assisted research/analyst-support tools specifically for how they handle uncertainty; the pattern found across the strongest examples set the design bar: "the citation is part of the answer," not an optional add-on.
- **Design Thinking & Ideation**: New in AI-native version — ideation centered on agent behavior before any screen: what happens when the agent is uncertain, when a user corrects it, and where the pull-vs-hand-off line sits.
- **Design Sprints & Iteration**: Real — iterative sprints with weekly usability testing.
- **Usability Testing**: Real — tested the happy path and the failure path as equally important; watched whether analysts verified sources unprompted, which signaled whether the citation design was actually doing its job.
- **Delivered Solution**: Real, shipped v1 — query input, cited answer, confidence signal, show-your-work expand, fallback/handoff state.
- **Outcomes**: See Results below.

**Callout — What We Learned (green)**: Early versions surfaced confidence only when the agent flagged low confidence itself. Testing showed analysts trusted the agent *more*, not less, when confidence was shown on every answer — it made the signal legible instead of only appearing as a warning.

`[VISUAL: Answer View screen, from 01-meridian-research-agent-wireframes.md]`

---

## KPI Stat Block — Results

- **~45 minutes saved per investigation workflow (real, sourced)**
- **~82% agent-answer acceptance rate** *(illustrative estimate — no sourced number exists for this secondary metric)*
- **~12% escalation-to-human rate** *(illustrative estimate — a healthy signal per the discovery doc, not a failure metric)*
- **~6% repeat-question rate** *(illustrative estimate — lower indicates the agent answered fully the first time)*

---

## Key Insight

> The core design challenge wasn't making the agent accurate — it was getting a skeptical, detail-oriented analyst to actually *act* on an AI answer in a regulated environment. Citations and source traceability did that work: not "add a citation if asked," but "the citation is part of the answer." Everything else in the design — the confidence signal, the show-your-work expand, the fallback state — exists to make that trust legible, not just present.

*(Pulled from brief HOW → trust design and the discovery doc's Competitive Analysis section — the most concrete design-judgment statement in the source material. Per CLAUDE.md's working agreement, this slide must survive intact even if others are trimmed.)*

`[VISUAL: Source Detail Expand screen, from 01-meridian-research-agent-wireframes.md]`

---

## Consistency Check

- [x] All 9 slides present, in order
- [x] Phase language matches CLAUDE.md's 8-stage names exactly
- [x] Key Insight slide present and substantive, not trimmed
- [x] Real, sourced metric (~45 min saved) presented as fact; all other numbers labeled illustrative estimates
- [x] No fabricated quotes presented as verbatim — both pull-quotes explicitly labeled illustrative
- [x] Visual placeholders marked, referencing the wireframes doc
- [x] Content synthesized beyond the brief/discovery is flagged inline, not presented as sourced fact
