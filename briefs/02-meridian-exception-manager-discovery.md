# Meridian Exception Manager
**Anchorpoint Capital** | AI-powered prioritized exception worklist for investment operations
*Anonymized composite based on real work — Anchorpoint Capital and Meridian are fictional stand-ins for the actual client/platform, since that work is current-employer confidential. The problem, process, and outcome described are real. Same underlying platform as Epic 1 (Meridian Research Agent), different product within it.*

Status: **Real, shipped v1** (not speculative) — built to the standard set in `../ai-ux-process-framework.md`, checked against its Part 4 completeness list at the bottom of this doc.

**A note on metrics in this doc:** the design and shipped v1 described here are real, per the project brief. But unlike Epic 1 — where "~45 minutes saved" is a real number sourced from Michael's resume — no equivalent sourced, measured outcome figure exists in this project's source files for Epic 2. Every number in the Outcomes section below is an illustrative, reasoned target consistent with the shipped design's stated goals, not a measured production result, and is labeled as such every place it appears (this doc, the wireframes, the slides, the web pages). This follows the same labeling rule used for Epic 4's concept-stage metrics, applied here even though the underlying work itself is real.

---

## Summary
End-to-end design process for the exception-management side of Meridian, Anchorpoint Capital's investment operations platform. Operational exceptions — trade breaks, mismatches, failed reconciliations — used to surface as a flat queue, so prioritization depended on tribal knowledge: only the most experienced analysts could look at a queue and know which breaks actually mattered. The system now detects, ranks, and proposes remediation for exceptions automatically, presenting them as a prioritized worklist with a visible reason for every flag. This is the direct interaction-mode contrast to Epic 1: Epic 1 is pull (analyst asks a question), Epic 2 is push/ambient (the system is always watching and surfaces what needs attention without being asked).

---

## The Problem
Operational exceptions at Anchorpoint Capital — trade breaks, mismatches, failed reconciliations — surfaced through queues that gave no signal about which ones actually mattered. Prioritization was tribal knowledge: experienced analysts could eyeball a queue and know what to work first, but that judgment lived in people's heads, not in the system.

- No consistent signal for severity or urgency — every exception looked the same until someone opened it
- Prioritization quality depended entirely on which analyst (and how experienced) picked up the queue that day
- High-risk exceptions could sit unworked for hours with nothing distinguishing them from routine, low-risk ones
- There was no way to see *why* something needed attention without manually investigating it first
- Team leads had no visibility into whether prioritization decisions were being made consistently across the team

**Why this mattered:** some exceptions have regulatory implications, and a de-prioritized high-risk break isn't just slower resolution — it's real exposure. Continuous/ambient AI monitoring (vs. Epic 1's on-demand agent) meant the design problem wasn't "can the system detect these" — it was "will experienced staff trust and act on a system that's always flagging things at them," which is a different, harder question than trust in a single asked-for answer.

---

## Discovery & Research
- Contextual interviews with the operations analysts currently doing manual triage, plus their team lead, focused on capturing the implicit rules experienced staff already use to prioritize a flat queue
- Mapped what could plausibly be inferred from the underlying exception data (severity, dollar exposure, recurrence pattern) vs. what required human judgment (regulatory sensitivity, client relationship context, whether a break was a known, tolerated pattern) — this boundary shaped which exceptions the system could rank with confidence vs. flag for human triage first
- **AI-native addition to standard discovery:** because this is push/ambient rather than pull, discovery also had to map the analyst's existing trust baseline toward being *told* something needs attention, not just toward being *answered* — a system that interrupts and is wrong burns trust faster than a system that's asked and is wrong. That distinction became the central design constraint for this epic, distinct from Epic 1's.

**Pain points heard from interviews:**
1. Exceptions arrived as a flat queue with no reliable signal for what actually mattered — everything looked equally urgent until someone opened it
2. Prioritization depended on tribal knowledge; only the most experienced analysts could triage quickly, and that knowledge wasn't written down anywhere
3. High-risk exceptions could sit unworked for hours because nothing in the queue visually distinguished them from routine ones
4. No visibility into *why* an exception was flagged — analysts re-verified from scratch every time, even for patterns they'd seen before
5. Team leads had no way to confirm prioritization was happening consistently across the team, or to see where re-prioritization was happening manually

### Competitive / pattern analysis
Looked at how other AI-assisted monitoring and alerting tools (fraud/risk alerting, IT ops incident triage) handle the moment they're proactively pushing something at a user rather than answering a question. The clearest pattern separating tools staff actually trusted from ones they learned to ignore: the trusted ones explained *why* an item was surfaced inline, at the moment of interruption, not behind a click — and gave an easy, low-friction way to tell the system "this one doesn't matter," with visible evidence that feedback changed future behavior. Tools that pushed alerts without a visible reason trained their users to tune them out within weeks. That became the design bar for Meridian's exception worklist: never surface a ranked item without a reason attached, and never let a dismissal disappear without a trace.

---

## Design Thinking / Ideation
Because this is a push/ambient system, ideation centered on defining the system's *behavior* at the moment it interrupts someone — not just the worklist screen. Workshops worked through three behavior questions before any screen was drawn:
- What does the system show when it's *not* highly confident an exception deserves top priority, rather than just ranking it and staying silent about the uncertainty?
- What happens when an analyst dismisses something as "not actually an issue" — does that exact pattern get flagged the same way again next time, or does the system visibly learn from it?
- Where's the line between "the system can detect, rank, and propose a fix" and "the system can resolve it"? Given that some exceptions carry regulatory implications, the working boundary was: the system never auto-resolves — it always proposes, and a human confirms every resolution.

The alert-fatigue risk named in the brief's core design challenge drove most of this stage: experienced staff disengage fast from a system that over-flags or under-explains, and once disengaged, they stop trusting the ranking even when it's right. Every ideation decision was tested against "would this make an already-skeptical analyst trust the ranking more, or train them to ignore it."

---

## Design & Iteration
Delivered across iterative sprints with weekly usability testing, following the same design-sprint cadence used across Anchorpoint's other Meridian workstreams.

**Key interaction patterns (final):**
- **Prioritized worklist** — a ranked list, not a flat queue; each item shows a visible reason it was ranked where it is, not just a score
- **Proposed-remediation card** — every flagged exception pairs with a suggested next step, so the analyst starts from a proposal instead of a blank investigation
- **Workflow states** — new/flagged → investigating → resolved, with a clear visual distinction between what the AI decided (the ranking, the flag, the proposed fix) and what a human has confirmed
- **Dismissal / feedback path** — a low-friction "not actually an issue" action that visibly feeds back into future prioritization, rather than silently disappearing
- **Aging escalation** — exceptions left unresolved are visually escalated over time instead of sitting static in the list, so age itself becomes a priority signal

**What changed across iterations:** the earliest version ranked exceptions with a numeric priority score only. Testing showed analysts distrusted a bare score — several described it as "just another black box telling me what to do." The design was revised to replace the score with a plain-language reason ("flagged: exposure above threshold and no prior tolerated pattern match") shown directly on the worklist row, before any click — the same "don't make them ask for the reason" principle established in Epic 1's citation design, applied here to a push interaction instead of a pull one.

---

## Usability Testing
Testing measured whether analysts trusted the ranking enough to act on it without re-verifying everything from scratch, not just whether they could operate the worklist.

- Tested the happy path (system correctly ranks and proposes a fix for a real high-priority exception) and the failure path (system over-flags something an experienced analyst immediately recognizes as low-risk) as equally important scenarios
- Watched specifically for whether analysts worked the list top-to-bottom as ranked, or re-sorted/re-triaged it themselves — the latter was a direct signal the ranking wasn't yet trusted, not a neutral behavior
- Iterated the dismissal flow after early testing showed analysts wouldn't use a dismissal control they suspected did nothing — a visible acknowledgment ("got it — deprioritizing similar patterns") was added so the feedback loop was legible in the moment, not just functional in the background

---

## Delivered Solution
The shipped v1 experience: exceptions are detected and ranked continuously, without an analyst having to open or ask for a queue. Each item in the worklist carries a plain-language reason it was flagged and a proposed remediation, and analysts triage top-down instead of manually figuring out what matters. Workflow state (new/flagged → investigating → resolved) makes explicit what the system decided and what a human confirmed at each step — the system never marks an exception resolved on its own. Dismissing a false positive is a first-class action, not a workaround, and visibly feeds back into future ranking. Aged, unresolved exceptions escalate visually over time rather than sitting silently in the list, so nothing can be quietly de-prioritized by inaction alone.

---

## Outcomes
*(All figures below are illustrative, reasoned targets — no sourced, measured production number exists for this concept in the project's source files. See the note at the top of this document.)*

- **~35% reduction in average exception time-to-resolution (illustrative target)** — reasoned from removing the manual "figure out what matters first" step named as the primary pain point in discovery
- **~40% reduction in aged/unresolved exceptions (illustrative target)** — reasoned from the aging-escalation pattern making neglect visible instead of passive
- **Reduction in exceptions manually re-prioritized by a human (trust-specific target)** — the core trust signal named in the brief's WHY: if analysts stop re-sorting the ranked list themselves, that's evidence the AI's prioritization is being trusted, not just tolerated
- **Dismissal-recurrence rate (trust/feedback-specific target)** — how often a pattern an analyst dismissed as "not an issue" gets re-flagged the same way again; watched as a signal the feedback loop is actually changing future behavior, not just logging the click

---

## Reflection / open backlog
- v2 direction: extending the same detection/ranking approach to a broader set of exception types beyond the initial rollout, and closing the loop further so dismissal feedback measurably changes ranking behavior within days, not just accumulates in a log
- Open design question: whether team leads need a dedicated view into prioritization consistency across the team (raised in discovery, not yet built) or whether the individual worklist's transparency is sufficient
- Read together with Epic 1: this is the deliberate push/ambient contrast to Epic 1's pull-only research agent — same platform, same underlying trust-building principle (never surface a conclusion without a visible reason), applied to two different interaction modes. Worth presenting as a matched pair in a portfolio review, not two unrelated features

---

## Framework check (against `../ai-ux-process-framework.md` Part 4)
- [x] Covers all 8 stages, naming what's the same vs. new — see Discovery, Ideation, and Testing sections above
- [x] Addresses relevant Part 2 categories: Trust & Explainability (visible reason on every ranked item), Confidence & Uncertainty (behavior when not highly confident, named in Ideation), Human-in-the-loop (system proposes, human confirms every resolution), Feedback & Correction (dismissal path and dismissal-recurrence tracking). Agent Accountability/multi-agent legibility doesn't apply — single-system case study, addressed in Epics 4 & 5 instead
- [x] Written to the Who/What/When/Why/How template — see `02-meridian-exception-manager.md`, this doc is that scaffold's full narrative
- [x] Shows a failure/uncertainty path, not just the happy path — see Testing (over-flagging scenario) and Delivered Solution (dismissal as first-class action)
- [x] States plainly this is real/shipped, anonymized as needed — see header and metrics note above
- [x] Includes trust-specific metrics alongside the business metric — see Outcomes; all explicitly labeled as illustrative targets, not measured results, per this project's no-fabrication rule
