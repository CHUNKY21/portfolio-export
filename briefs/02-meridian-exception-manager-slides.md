# Slides — Meridian Exception Manager (Epic 2)
Source: `02-meridian-exception-manager.md` (brief) + `02-meridian-exception-manager-discovery.md` (discovery). The underlying design is real, shipped work (per the brief and discovery doc). However, no sourced, measured outcome figure exists in this project's files for this concept — unlike Epic 1's real "~45 minutes saved." Every metric and quote below is an illustrative, reasoned target/example, labeled inline; none should be presented as a real measured result or a verbatim quote in any downstream deliverable.

---

## Section Divider / Cover — Meridian Exception Manager

- **Title**: Meridian Exception Manager
- **Tagline**: From a flat queue to a ranked worklist the team trusts
- **One-line description**: An AI layer that detects, prioritizes, and proposes remediation for operational exceptions inside Meridian, Anchorpoint Capital's investment operations platform — presenting them as a ranked, actionable worklist instead of a flat queue.
- **Pull-quote** *(illustrative — reasoned from discovery pain point #1, not a verbatim interview quote)*: "Every exception looked the same until I opened it. I had no way to know what actually mattered."
- **Treatment**: coral gradient banner (`#F5805C` → `#FF8C7A` → `#FFB088`), thin title typography, lime `#BFFD20` / rust `#D54E2B` accent bars

---

## Introduction — What's Meridian Exception Manager?

- **Description**: A system that continuously watches for operational exceptions — trade breaks, mismatches, failed reconciliations — and surfaces them as a ranked worklist with a visible reason for every flag and a proposed next step, instead of a flat queue analysts have to triage manually.
- **Target audience** (teal circle-callout): Operations analyst (same persona as Epic 1, now in reactive/triage mode), Team lead who owns prioritization across the queue
- **The problems** (bulleted, from discovery Pain Points):
  1. Exceptions arrived as a flat queue with no reliable signal for what actually mattered
  2. Prioritization depended on tribal knowledge that lived only in experienced analysts' heads
  3. High-risk exceptions could sit unworked for hours with nothing distinguishing them from routine ones
- **My Role**: Led the design process for this concept, from contextual interviews with the manual-triage team through shipped v1.

---

## KPI Stat Block — Discovery & Research

- **"Why does this matter?"**
- **~35% reduction in average exception time-to-resolution (illustrative target — no sourced measurement exists for this concept)**
- **Discovery methods**: contextual interviews with operations analysts doing manual triage, plus their team lead, focused on capturing the implicit rules experienced staff already use to prioritize
- **Problem statement** (from brief WHAT → Problem): operational exceptions surfaced through queues and manual triage, so prioritization depended on tribal knowledge of "which ones actually matter"

---

## Pain Points from Interviews

1. Exceptions arrived as a flat queue with no reliable signal for what actually mattered
2. Prioritization depended on tribal knowledge; only the most experienced analysts could triage quickly
3. High-risk exceptions could sit unworked for hours because nothing visually distinguished them from routine ones
4. No visibility into why an exception was flagged — analysts re-verified from scratch every time
5. Team leads had no way to confirm prioritization was happening consistently across the team

**Pull-quote** *(illustrative — reasoned from pain point #4, not a verbatim quote)*: "I'd end up re-checking the same thing three different ways just to convince myself it was actually urgent."

---

## Persona Card — Operations Analyst (Triage Mode)

- **Name/Role**: primary persona, Operations analyst (per brief WHO) — same persona as Epic 1, here in a reactive/triage rather than investigative mode
- **Sentiment quote** *(illustrative, reasoned from the documented pain points — not a sourced verbatim)*: "Tell me why this matters before you ask me to act on it, and I'll trust the ranking. Just rank it silently and I won't."
- **Responsibilities**: triaging the exception queue, resolving or escalating flagged breaks, distinguishing real issues from noise
- **Key challenges**: alert fatigue from over-flagging, no visible reasoning behind past prioritization, high-risk items indistinguishable from routine ones at a glance
- **Wishlist**: a ranked worklist instead of a flat queue, a visible reason attached to every flag, an easy way to say "not actually an issue" that visibly changes future behavior

*(Fields beyond role and core challenge are reasonably inferred from brief WHO + WHAT + discovery pain points, not sourced from dedicated persona-sentiment interviews — flagged here per wireframe-describer's underspecified-content convention.)*

---

## Four-Column Framework — Pain Points + Business Goals + UX Strategy = Feature Set

| Pain Points (red `#DF505C`) | Business Goals (blue `#8AD9F8`) | UX Strategy (green `#41854F`) | Feature Set (purple `#7C417E`) |
|---|---|---|---|
| Flat queue, no signal for what matters | Faster exception resolution, fewer missed high-risk breaks | Contextual interviews to capture the implicit rules experienced staff already use | Prioritized worklist (ranked, not flat) |
| Prioritization is tribal knowledge | Fewer aged/unresolved exceptions | Visible reasoning for every flag, by default, not on request | Proposed-remediation card |
| No visibility into why something was flagged | Analysts trust the system's prioritization enough to act on it | Low-friction dismissal path that visibly feeds back into the system | Workflow states (new/flagged → investigating → resolved) with AI-proposed vs. human-confirmed distinction |
| Aged high-risk exceptions can sit unworked | | Aging made visible, not silent | Aging/escalation indicator + dismissal feedback loop |

---

## Design/Process — 8-Stage AI-Enhanced UX Process

- **Discovery & Research**: Same as always — contextual interviews with the manual-triage team and their team lead. New in AI-native version: mapped what the system could plausibly rank with confidence (severity, exposure, recurrence pattern) vs. what needed human judgment (regulatory sensitivity, client context) — and, because this is push/ambient rather than pull, explicitly mapped the analyst's trust baseline toward being *told* something needs attention vs. being *answered* on request.
- **Problem Definition**: Same as always — synthesized the manual-triage pain points into a clear problem statement. New: separated "the queue is unranked" (a system can fix this) from "I don't trust being interrupted by an automated flag" (only interaction design fixes this).
- **Competitive / Pattern Analysis**: New in AI-native version — benchmarked against other proactive alerting/monitoring tools (fraud/risk alerting, IT ops incident triage) specifically on how they handle being wrong when *pushing* something at a user, not just feature parity. Tools that alerted without a visible reason trained users to ignore them within weeks — that became the design bar here.
- **Design Thinking & Ideation**: New in AI-native version — ideation centered on the system's behavior at the moment it interrupts someone: what it shows when not highly confident, what happens after a dismissal, and where "detect and propose" ends and "human must confirm" begins.
- **Design Sprints & Iteration**: Same as always — iterative sprints with weekly usability testing. New: the earliest version ranked with a bare numeric score; testing showed analysts distrusted it as "another black box," so iteration replaced the score with a plain-language reason shown inline before any click.
- **Usability Testing**: Same as always — task completion. New: tested whether analysts worked the list top-to-bottom as ranked (trust) or re-sorted it themselves (distrust signal), and deliberately tested the over-flagging failure path, not just the happy path.
- **Delivered Solution**: The shipped v1 — continuous detection and ranking, a visible reason and proposed remediation on every item, explicit AI-proposed vs. human-confirmed workflow states, and a first-class dismissal path that feeds back into ranking.
- **Outcomes**: See Results below — illustrative targets, since no sourced measured figure exists for this concept; see the metrics note at the top of this document.

**Callout — Unexpected Challenge (red)**: The riskiest early design choice wasn't the ranking algorithm — it was showing a bare priority score with no reason. Testing showed that a system which pushes an unexplained number at someone is trusted *less* than a flat, unranked queue, because it reads as a black box making decisions for you rather than a tool helping you decide. Replacing the score with a visible, plain-language reason was the single highest-leverage change in the whole iteration cycle.

`[VISUAL: Exception Worklist screen, from 02-meridian-exception-manager-wireframes.md]`

---

## KPI Stat Block — Results (illustrative targets, not measured results)

- **~35% reduction in average exception time-to-resolution (illustrative target)**
- **~40% reduction in aged/unresolved exceptions (illustrative target)**
- **Reduction in exceptions manually re-prioritized by a human (trust-specific illustrative target)** — tracked as the signal that the AI's prioritization is trusted, not just tolerated
- **Dismissal-recurrence rate (trust/feedback-specific illustrative target)** — how often a dismissed false-positive pattern stops recurring, watched as a signal the feedback loop is actually working

*(All figures explicitly labeled as illustrative targets — no production measurement exists for this concept in the project's source files, per the metrics note at the top of this document.)*

---

## Key Insight

> This is the deliberate push/ambient contrast to Epic 1's pull-only research agent — same platform, same underlying trust-building principle (never surface a conclusion without a visible reason), applied to a completely different interaction mode. Epic 1 has to earn trust when *asked* a question; Epic 2 has to earn trust while *interrupting* someone who didn't ask for anything. That's why alert fatigue and false-positive distrust, not accuracy alone, were the core design challenge — a system that's right but unexplained gets ignored just as fast as one that's wrong.

*(Pulled from brief HOW → core design challenge and the discovery doc's Reflection section; this is the most concrete design-judgment statement in the source material. Per CLAUDE.md's working agreement, this slide must survive intact even if others are trimmed.)*

`[VISUAL: Exception Detail — Proposed Remediation Card screen, from 02-meridian-exception-manager-wireframes.md]`

---

## Consistency Check

- [x] All 9 slides present, in order
- [x] Phase language matches CLAUDE.md's 8-stage names exactly
- [x] Key Insight slide present and substantive, not trimmed
- [x] No fabricated metrics presented as real — all figures labeled illustrative targets
- [x] No fabricated quotes presented as verbatim — both pull-quotes and the persona sentiment quote explicitly labeled illustrative
- [x] Visual placeholders marked, referencing the wireframes doc
- [x] Content synthesized beyond the brief/discovery (persona sentiment detail, illustrative quotes, target metrics) is flagged inline, not presented as sourced fact
