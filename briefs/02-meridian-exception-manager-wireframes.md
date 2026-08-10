# Wireframes — Meridian Exception Manager (Epic 2)
Source: `02-meridian-exception-manager.md` (WHAT/HOW) + `02-meridian-exception-manager-discovery.md` (Discovery & Research pain points). This is the spec that feeds manual mockup work or an AI design tool — no visual mockups are produced here.

**Screens covered:** Exception Worklist → Exception Detail (Proposed Remediation) → Dismissal / False-Positive Feedback → Team Lead Prioritization Overview

---

## Screen: Exception Worklist

- **Purpose**: Give an operations analyst a single ranked view of what needs attention, resolving discovery pain point #1 — "exceptions arrived as a flat queue with no reliable signal for what actually mattered" — and pain point #2, prioritization depending on tribal knowledge.
- **Key elements**:
  - Prioritized worklist (named in brief HOW → Key interaction patterns) — one row per exception, ranked, not a flat/sortable-only queue
  - Plain-language flag reason shown inline on each row (e.g., "exposure above threshold, no prior tolerated pattern match") — visible before any click, per the discovery doc's "don't make them ask for the reason" principle
  - Workflow state indicator per row (new/flagged → investigating → resolved, named in brief HOW)
  - Aging/escalation indicator — visual treatment that intensifies the longer an exception sits unresolved (brief Acceptance criteria: "aged/unresolved exceptions are visually escalated over time rather than silently sitting in a queue")
  - Filter/view controls (e.g., by workflow state, by stakeholder area such as risk/compliance-flagged items)
- **Primary user action**: Analyst scans the ranked list top-to-bottom, opens the highest-priority unresolved item → goes to Exception Detail
- **AI-generated content vs. static UI**: AI-generated — the ranking/priority order, the flag reason text, the aging-escalation trigger. Static — the row/list structure, column headers, filter controls
- **State variations**:
  - Empty state (no open exceptions — a deliberately reassuring state, not a blank error-style screen)
  - Normal ranked-list state
  - Aged/escalated state (row visually distinct — per Acceptance criteria, escalation must be visible in the worklist itself, not only inside the detail view)
  - Regulatory-flagged state (row visually distinct when risk/compliance stakeholder relevance applies, per brief WHO → Stakeholders)

---

## Screen: Exception Detail — Proposed Remediation Card

- **Purpose**: Let the analyst act on a flagged exception starting from a proposed fix instead of a blank investigation — the direct answer to discovery pain point #4, "no visibility into why an exception was flagged; analysts re-verified from scratch every time."
- **Key elements**:
  - Proposed-remediation card (named explicitly in brief HOW → Key interaction patterns) — the suggested next step, shown prominently, not buried under raw exception data
  - Flag rationale — the full version of the worklist's inline reason, expanded (what data/pattern triggered the flag)
  - Workflow-state control — lets the analyst move the item new/flagged → investigating → resolved (brief Acceptance criteria: "clear visual/state distinction between AI-proposed and human-confirmed resolution")
  - Confirm-remediation action — human explicitly confirms/accepts the proposed fix; the system never marks an exception resolved on its own (per discovery's Ideation section)
  - Path to the dismissal/feedback action (see next screen) for when the flag itself is wrong, not just the proposed fix
- **Primary user action**: Analyst reviews the flag rationale and proposed remediation, then either confirms the remediation (moves to resolved) or dismisses the flag as a false positive
- **AI-generated content vs. static UI**: AI-generated — the flag rationale, the proposed remediation, the workflow-state recommendation. Static — the underlying exception/transaction record itself (real trade/reconciliation data, not agent-generated), the confirm/dismiss controls
- **State variations**:
  - AI-proposed, unconfirmed state (default — proposal shown, awaiting human action)
  - Human-confirmed/resolved state (visually distinct per Acceptance criteria — must not look identical to the AI-proposed state)
  - Investigating state (analyst has picked it up but not yet resolved)
  - Low-confidence state (**decision**: the brief does not specify what the detail view shows when the system's own confidence in the proposed remediation is low — `[UNDERSPECIFIED: brief does not detail a low-confidence remediation state — confirm with Michael before designing]`. Resolved here: when confidence is low, the card still shows the flag rationale but replaces the single proposed-remediation action with a labeled "possible next steps" list and no default confirm action — the analyst must choose a direction rather than confirm a single suggestion, so the UI never presents a low-confidence guess with the same visual weight as a high-confidence one.)

---

## Screen: Dismissal / False-Positive Feedback

- **Purpose**: Give the analyst a low-friction way to tell the system a flag was wrong, and make that feedback visibly count — resolves the alert-fatigue core design challenge named in brief HOW, and directly implements the discovery doc's finding that a dismissal control analysts "suspected did nothing" went unused.
- **Key elements**:
  - "Not actually an issue" dismissal action (named in brief HOW and Acceptance criteria), reachable directly from the worklist row or the detail view without extra steps
  - Optional short reason/category for the dismissal (supports future pattern-matching, without forcing a long form that would suppress use of the control)
  - Visible acknowledgment on dismissal (per discovery's Design & Iteration: "got it — deprioritizing similar patterns") — confirms the feedback loop is live, not silent
- **Primary user action**: Analyst dismisses a flagged exception as not-actually-an-issue; sees immediate confirmation that the system registered it; returns to the worklist, where that item is removed from the active ranking
- **AI-generated content vs. static UI**: AI-generated — the pattern-matching that will use this dismissal to affect future ranking (per discovery's dismissal-recurrence outcome metric). Static — the dismissal control itself and its acknowledgment message
- **State variations**:
  - Default dismissal-confirmation state (acknowledgment shown, item removed from active worklist)
  - Dismissal-recurrence state — a later exception matches a previously dismissed pattern; per discovery's Outcomes (dismissal-recurrence rate is tracked as a trust signal), this state should visibly note "similar to a pattern dismissed on [date]" rather than re-flagging identically, so the analyst can see the feedback loop working in the moment

---

## Screen: Team Lead Prioritization Overview

- **Purpose**: Give the team lead (secondary persona, brief WHO — "owns prioritization across the exception queue") visibility into whether prioritization is happening consistently across the team, resolving discovery pain point #5, "team leads had no way to confirm prioritization was happening consistently across the team."
- **Key elements**:
  - Team-level worklist view — aggregated across analysts, same ranking logic as the individual worklist
  - Manual re-prioritization indicator — surfaces where an analyst has overridden the system's ranking (this is the brief's WHY → trust-specific success metric made visible as a UI element, not just a background analytic)
  - Aging/escalation summary — how many items are aged past a threshold, team-wide
- **Primary user action**: Team lead scans for items that are aged, contested (manually re-prioritized), or stakeholder-flagged, and can drill into any individual exception (reuses Exception Detail)
- **AI-generated content vs. static UI**: AI-generated — the ranking, the aging calculation, the "manually re-prioritized" flag. Static — the team roster/assignment structure
- **State variations**: Not applicable beyond the states already defined on Exception Worklist and Exception Detail — this is an aggregated/team-scoped lens on the same underlying data, not an independent flow

---

## Consistency Check

- [x] Every screen ties back to a specific pain point from the discovery file (pain points #1–#5 all covered)
- [x] Component terminology matches the brief's HOW → Key interaction patterns exactly ("prioritized worklist," "proposed-remediation card," workflow states, dismissal path — no invented component names)
- [x] AI-generated vs. static content is explicitly distinguished on each screen
- [x] Underspecified areas were flagged, then resolved with an explicit design decision (low-confidence remediation state) rather than left open or silently guessed
- [x] Screen order follows a logical flow: primary persona's entry point (Worklist) → core decision screen (Detail/Remediation) → feedback path (Dismissal) → secondary persona's view (Team Lead Overview)
