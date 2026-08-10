# Meridian Research Agent
**Anchorpoint Capital** | AI-powered conversational research agent for investment operations
*Anonymized composite based on real work — Anchorpoint Capital and Meridian are fictional stand-ins for the actual client/platform, since that work is current-employer confidential. The problem, process, and outcome described are real.*

Status: **Real, shipped v1** (not speculative) — built to the standard set in `../ai-ux-process-framework.md`, checked against its Part 4 completeness list at the bottom of this doc.

---

## Summary
End-to-end design process for an AI research agent embedded in Meridian, Anchorpoint Capital's investment operations platform. Analysts used to manually cross-reference five-plus internal systems to answer a research question or investigate a discrepancy. The agent now takes a plain-language question, retrieves from connected internal sources, synthesizes a cited answer, and hands off to a human wherever it isn't confident. **Result: ~45 minutes saved per investigation workflow.**

---

## The Problem
Investment operations analysts at Anchorpoint Capital spend a large share of their day on research and investigation tasks — answering questions like "why did this position break" or "what's the history behind this account flag." Answering one of these meant manually opening and cross-referencing multiple internal systems, and the quality of the answer depended heavily on which analyst happened to pick it up.

- No single system had the full picture — answers required assembling context across platforms
- Time-to-answer varied widely by analyst experience, with no shared baseline
- There was no way to hand off a partial finding — it was all-or-nothing manual work
- Any answer produced this way was hard to audit after the fact — nothing showed *where* a conclusion came from

**Why this mattered:** research and investigation tasks are a recurring, high-volume part of the operations workload — even small per-task time savings compound quickly across a team handling this every day. And in a regulated financial environment, answers need to be traceable, not just fast.

---

## Discovery & Research
- Interviews with investment operations analysts across experience levels, plus their team lead
- Mapped the manual research workflow step by step, to see where time actually went (data-gathering vs. synthesis vs. double-checking)
- **AI-native addition to standard discovery:** explicitly mapped what the underlying data sources could plausibly answer with confidence vs. what required human judgment — this shaped where the agent should answer outright vs. where it should hand off
- Also captured analysts' existing trust baseline toward automated output in this domain — this group is detail-oriented and default-skeptical of anything they can't verify, which became the central design constraint

**Pain points heard from interviews:**
1. Manually opening 4-5 systems for a single research question
2. No consistent starting point — every analyst improvises their own process
3. No way to show your work after the fact — answers aren't auditable
4. Repetitive, low-judgment lookups take the same time as genuinely hard investigations

### Competitive / pattern analysis
Looked at how other AI-assisted tools in adjacent domains (research and analyst-support tools) handle the moment a system is uncertain or wrong. The clear pattern across the strongest examples: they show their work by default, not on request — source is visible before the user has to ask for it, and confidence is signaled even when the answer is otherwise solid. That became the design bar for Meridian: not "add citations if asked," but "the citation is part of the answer."

---

## Design Thinking / Ideation
Ideation here wasn't just about the screen — it was about defining the agent's *behavior*, especially in the moments where it doesn't have a clean answer. Workshops focused on three behavior questions before any screen was drawn:
- What does the agent do when it's uncertain, rather than just wrong?
- What does it do when a user tells it the answer was incomplete or off?
- Where's the line between "the agent should just answer" and "the agent should stop and hand this to a human"?

That third question mattered most — this is a domain where a wrong-but-confident answer causes real harm, so the design had to define an explicit boundary between what the agent owns and what stays human-gated, not leave it implicit.

---

## Design & Iteration
Delivered across iterative sprints with weekly usability testing, following the same design-sprint cadence used across Anchorpoint's other Meridian workstreams.

**Key interaction patterns (final):**
- **Query input** — plain-language question entry, no special syntax required
- **Cited answer format** — every answer is delivered with its source(s) visible inline, not hidden behind a "show sources" click
- **Confidence signal** — a clear, non-technical indicator distinguishing "confident answer" from "partial — here's what I found"
- **Show-your-work expand** — any cited source can be expanded to the underlying record, so an analyst can verify without leaving the agent
- **Fallback / handoff state** — when the agent can't produce a confident answer, it says so plainly and routes the analyst toward the right next step, instead of guessing

**What changed across iterations:** early versions surfaced confidence only when the agent flagged low confidence itself. Testing showed analysts trusted the agent *more*, not less, when confidence was shown on every answer, including high-confidence ones — it made the signal legible instead of only appearing as a warning.

---

## Usability Testing
Testing measured trust and comprehension, not just task completion — could an analyst use the agent, understand *why* it gave the answer it did, and know what to do when it didn't have one.

- Tested the happy path (agent has a confident, correct answer) and the failure path (agent is uncertain or the data is incomplete) as equally important scenarios
- Watched specifically for whether analysts stopped to verify sources on their own, or accepted answers at face value without checking — both signaled something about whether the citation design was actually doing its job, not just present
- Iterated the fallback state after early testing showed analysts found a flat "I don't know" unhelpful — it now names what it does know and what it couldn't confirm, rather than a dead end

---

## Delivered Solution
The shipped v1 experience: an analyst asks a question in plain language inside Meridian; the agent retrieves across connected internal sources, returns a synthesized answer with inline citations and a confidence signal, and either resolves the question or hands off with a specific next step when it can't. What the agent owns (retrieval, synthesis, initial confidence assessment) and what stays human-gated (final judgment on anything below full confidence, anything with compliance implications) is visibly distinguished throughout, not left for the analyst to guess.

---

## Outcomes
- **~45 minutes saved per investigation workflow** (primary, real metric)
- Agent-answer acceptance rate — tracked to confirm analysts are acting on answers, not just requesting them and re-doing the work manually anyway
- Escalation-to-human rate — a healthy signal, not a failure metric: shows the handoff boundary is actually being used as designed
- Repeat-question rate — watched as a signal the agent didn't fully answer the first time

---

## Reflection / open backlog
- v2 direction: expanding the set of connected internal sources so fewer questions fall into the "partial answer" bucket
- Open design question carried into Epic 2 (Meridian Exception Manager): this agent is pull-only (analyst asks); the exception-management side of Meridian is push/ambient — worth reading as a deliberate contrast in interaction mode, not a duplicate pattern

---

## Framework check (against `../ai-ux-process-framework.md` Part 4)
- [x] Covers all 8 stages, naming what's the same vs. new — see Discovery, Ideation, and Testing sections above
- [x] Addresses relevant Part 2 categories: Trust & Explainability (citations), Confidence & Uncertainty (confidence signal, fallback state), Human-in-the-loop (explicit ownership boundary), Feedback & Correction (acceptance/repeat-question tracking). Agent Accountability/multi-agent legibility doesn't apply — single-agent case study, addressed in Epics 4 & 5 instead
- [x] Written to the Who/What/When/Why/How template — see `01-meridian-research-agent.md`, this doc is that scaffold's full narrative
- [x] Shows a failure/uncertainty path, not just the happy path — see Testing and Delivered Solution
- [x] States plainly this is real/shipped, anonymized as needed — see header
- [x] Includes trust-specific metrics alongside the business metric — see Outcomes
