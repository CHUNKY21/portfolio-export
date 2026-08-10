# Wireframes — Compliance Co-Pilot (Epic 4)
Source: `04-compliance-copilot.md` (WHAT/HOW) + `04-compliance-copilot-discovery.md` (Discovery & Research pain points). This is the spec that fed the Figma mockups below.

**Figma mockups**: [Compliance Co-Pilot — Concept Mockups](https://www.figma.com/design/T0c8hGDQUcZsbxPZZlayC2) — all 4 screens built using the real Design Style Guide palette (color variables bound, not hardcoded) and Poppins Light/Regular as a web-safe stand-in for the deck's geometric sans.

**Screens covered:** Reviewer Queue → Submission Detail (Agent Activity Trail) → Policy Conflict Drill-down → Submitter Status View

---

## Screen: Reviewer Queue

- **Purpose**: Give a compliance reviewer a single place to see where every submission stands, resolving discovery pain point #2 — "no visibility into where a submission is in the review pipeline or why."
- **Key elements**:
  - Submission list, one row per case, with Employee, Firm Name, Type, Status, and a compact agent-activity indicator (e.g., which agent last touched it)
  - Status filter/tabs (mirrors the real OBI app's Previous Requests / Drafts / In Progress / Pending My Approval structure, extended with agent-status awareness)
  - Priority or attention flag for submissions with an unresolved policy conflict
- **Primary user action**: Reviewer scans the queue, identifies a submission needing attention, opens it → goes to Submission Detail
- **AI-generated content vs. static UI**: AI-populated — the agent-activity indicator and any conflict flag. Static — the list structure, filters, column headers
- **State variations**:
  - Empty state (no submissions pending)
  - Normal list state
  - Flagged state (row visually distinct when a policy agent has raised a conflict awaiting review)

---

## Screen: Submission Detail — Agent Activity Trail

- **Purpose**: Show, on a single submission, which agent acted, what it did, and why — this is the concept's central design answer to "who decided this" opacity, and directly resolves discovery pain point #2.
- **Key elements**:
  - **Agent-activity trail/timeline** (named explicitly in brief HOW) — timestamped entries, e.g. "Research agent reviewed disclosure history — Policy agent flagged a potential conflict — Routed to [Approver] for review"
  - Disclosure-history panel — a consolidated view of the submitter's prior disclosures, resolving discovery pain point #3 ("no consolidated view of submitter's disclosure history when making a judgment call")
  - Policy-conflict card(s) — each linked to the specific policy/rule it's based on (brief Acceptance criteria: "every agent-flagged conflict links to the specific policy/rule it's based on")
  - Override control — lets a human reviewer override any agent action
- **Primary user action**: Reviewer reads the trail and disclosure history, drills into a flagged conflict if present, then either confirms the agents' routing or overrides it
- **AI-generated content vs. static UI**: AI-generated — every trail entry, the conflict flags, the routing recommendation, and the disclosure-history ranking (**decision**: the research agent surfaces the 3-5 most relevant prior disclosures first — matched on firm name, activity type, or a policy area related to the current flag — with a one-line "why this is shown" note under each, rather than a flat chronological dump; the reviewer can still expand to the full chronological history). Static — the underlying disclosure records themselves (real submitter data, not agent-generated)
- **State variations**:
  - No-conflict state (research + policy agents found nothing to flag — trail shows a clean pass-through)
  - Conflict-flagged state (policy agent raised an issue, awaiting reviewer action)
  - Overridden state (reviewer has overridden an agent action — brief Acceptance criteria requires this be logged, so the trail must visibly show the override alongside the original agent action, not replace it)

---

## Screen: Policy Conflict Drill-down

- **Purpose**: Let the reviewer verify a policy agent's flag against the actual rule it's based on, rather than trusting the flag blindly — extends Epic 1's "show your work" trust pattern into a multi-agent context.
- **Key elements**:
  - The specific policy/rule text or reference the conflict is based on
  - The submission data point(s) that triggered the flag
  - A path back to confirm or override from this view (so the reviewer doesn't have to return to the trail screen first)
- **Primary user action**: Reviewer reads the linked policy, judges whether the flag is valid, and confirms or overrides
- **AI-generated content vs. static UI**: AI-generated — the flag itself and the reasoning connecting the data point to the policy. Static — the policy/rule text (sourced from the actual compliance rule set, not agent-generated)
- **State variations**: Not applicable beyond the parent screen's conflict-flagged state — this is an expand/drill-down of that state, not an independent flow

---

## Screen: Submitter Status View

- **Purpose**: Give the submitter (secondary persona, per brief WHO) visibility into their own submission's status and what's still needed — resolves discovery pain point #1, "submissions returned for missing information, with no clear explanation of what was actually needed."
- **Key elements**:
  - Plain-language status (**decision**: submitter-facing content is outcome-level only — "In review," "More information needed," "Approved" — plus the specific missing item if blocked. It excludes agent attribution, the activity trail, and any policy-rule references shown to reviewers; the compliance/audit boundary means submitters see *what's happening to their case*, not *how the internal review reasoning works*)
  - Clear statement of any missing information needed, if the submission is blocked on that
  - Submission history (their own past disclosures, for reference)
- **Primary user action**: Submitter checks status; if action is needed, understands exactly what to provide
- **AI-generated content vs. static UI**: AI-generated — the plain-language status summary and the specific "what's missing" explanation, if the research/policy agents' findings inform it. Static — the submission history list
- **State variations**:
  - In-progress (no action needed from submitter)
  - Action-needed (missing information, blocked)
  - Resolved/approved

---

## Consistency Check

- [x] Every screen ties back to a specific pain point from the discovery file (pain points #1, #2, #3 all covered)
- [x] Component terminology matches the brief's HOW → Key interaction patterns exactly ("agent-activity trail/timeline," override, policy-conflict linking — no invented component names)
- [x] AI-generated vs. static content is explicitly distinguished on each screen
- [x] Underspecified areas were flagged, then resolved with explicit design decisions (disclosure-history relevance ranking; submitter-facing detail level) rather than left open or silently guessed
- [x] Screen order follows a logical flow: reviewer entry point (Queue) → core decision screen (Activity Trail) → verification drill-down (Policy Conflict) → the secondary persona's view (Submitter Status)
