# Compliance Co-Pilot
**Credit Suisse** | Multi-agent concept extending the real Outside Business Interests (OBI) case study
*Real client, real prior discovery work (the existing OBI case study) — the multi-agent Compliance Co-Pilot concept itself is speculative/unshipped, extending that real foundation into a forward-looking design.*

Status: **Concept / speculative** (not shipped) — built to the standard set in `../ai-ux-process-framework.md`, checked against its Part 4 completeness list at the bottom of this doc. Every section below is explicit about what's carried over from the real OBI engagement vs. what's proposed/hypothesized for this concept.

---

## Summary
A concept extending Michael's real Credit Suisse Outside Business Interests (OBI) work: instead of a single submission moving through manual step-by-step routing and review, a multi-agent system — a research agent, a policy/compliance-check agent, and an escalation agent — handles detection, review, and routing, with the UI always showing which agent acted, what it did, and why. Positioned honestly as a vision piece: it demonstrates orchestration and accountability design (the core challenge when more than one "agent" touches a case), not shipped results.

---

## The Problem
The real OBI system (see the existing case study) already established that a single submission — e.g., a disclosure of an outside business interest — moved through manual, step-by-step routing and review, with reviewers and submitters unable to see why a submission sat at a given stage or what was actually being checked. That's the real, documented starting point.

This concept asks the next question: if AI agents took on parts of that review (initial research/context-gathering, policy-conflict flagging, escalation routing), what breaks? The answer is legibility — when more than one agent can act on a case, "who decided this and why" becomes a harder problem than it was with a single human reviewer or a single deterministic workflow engine.

**Why this matters:** compliance review is a domain where an opaque decision is not just inconvenient, it's a trust and audit failure. A multi-agent system that can't show its work at each handoff is a regression from even the manual process it's replacing, not an improvement — which is why this concept treats agent-activity legibility as the central design problem, not a nice-to-have.

---

## Discovery & Research
**Carried over from the real OBI engagement** (not re-run for this concept):
- Interviews with Risk & Compliance managers and Submitter/Employee personas — established the four-stage real workflow (detection → review & analysis → escalation → remediation)
- The core documented pain point: submissions returned for missing information, and no visibility into review status or reasoning

**New for this concept — AI-native addition to discovery:**
- Mapped which parts of the real four-stage workflow are plausibly agent-automatable (context-gathering, policy-conflict detection) vs. which require a human compliance judgment call (final approval, ambiguous-policy interpretation, escalation to legal) — this boundary is the concept's central design decision, not an implementation detail
- This concept has not had its own dedicated discovery interviews conducted yet — that's an open next step, not something to backfill with invented findings

**Pain points heard from interviews (real, from the existing OBI case study):**
1. Submissions returned for missing information, with no clear explanation of what was actually needed
2. No visibility into where a submission is in the review pipeline or why
3. Reviewers had no consolidated view of a submitter's disclosure history when making a judgment call

*[No additional pain-point interviews have been conducted specifically for the multi-agent concept — the three above are the real, sourced findings this concept builds on. Do not add fabricated pain points beyond these.]*

**Baseline estimate (illustrative, not sourced from the real OBI dataset):** ~40% of OBI submissions were returned at least once for missing information under the original manual process — used in deliverables as the "why this matters" framing stat, clearly labeled as an illustrative baseline rather than a measured figure.

### Competitive / pattern analysis
Not yet conducted for this concept specifically. Worth benchmarking against how other regulated-industry systems (e.g., healthcare prior-authorization, financial trade surveillance) handle multi-party/multi-system accountability trails before this concept is built out further — flagged as an open next step, not completed research.

---

## Design Thinking / Ideation
The central ideation question for this concept: **when three different actors (research agent, policy agent, escalation agent, plus the human reviewer) can each touch a submission, how does a compliance reviewer know who did what and why — without having to reconstruct it themselves?**

Three behavior questions frame the concept, following the same "define the behavior before the screen" approach used in Epic 1:
- What does each agent surface when it acts — a raw output, or a plain-language explanation of what it checked and why?
- When two agents' outputs conflict (e.g., the research agent finds no issue but the policy agent flags a conflict), how is that surfaced, and who resolves it?
- Where's the line between "an agent can act and move the submission forward" and "an agent can only recommend, and a human must confirm"? Given the OBI domain (regulatory disclosures), the working assumption is that agents propose and a human reviewer confirms every material action — this concept does not propose full agent autonomy over compliance outcomes.

---

## Design & Iteration
Not yet run — this concept has not entered a design-sprint cycle. The pattern below is the proposed direction, not a tested/iterated outcome.

**Proposed key interaction pattern:**
- **Agent-activity trail/timeline** — a visible, timestamped log on every submission (e.g., "Research agent reviewed disclosure history — Policy agent flagged a potential conflict — Routed to [Approver] for review"), extending the same "show your work by default" principle established in Epic 1's citation design
- **Policy-conflict linking** — every agent-flagged conflict links to the specific policy/rule it's based on, so a reviewer can verify the flag rather than trust it blindly
- **Override + log** — a human reviewer can override any agent action, and that override is itself logged in the same trail, not treated as an exception outside the system's record

**Open design question, not yet resolved:** how much of the real OBI screens/visual structure to reuse directly vs. build fresh concept screens for the multi-agent trail — this is explicitly called out as unresolved in the brief and stays unresolved here.

---

## Usability Testing
**Not yet conducted.** This is a concept/vision piece, not a shipped or tested feature — presenting fabricated testing results here would misrepresent it. The validation plan, if this concept moves forward, would need to test:
- Whether reviewers can correctly reconstruct "who did what and why" from the activity trail without additional explanation
- Whether the override path feels usable or like a workaround the design should have anticipated
- Trust calibration specifically for compliance staff, who (per the real OBI persona work) are accuracy- and audit-focused by role, not casually trusting of automation

---

## Delivered Solution
**Not shipped.** The proposed concept: a submission enters the same four-stage pipeline established by the real OBI system, but research and initial policy-conflict detection are agent-assisted, with every agent action visible in a timestamped trail on the submission. A human reviewer retains final authority on every material action; agents propose, flag, and surface — they don't decide. This boundary (agent proposes / human confirms) is the concept's answer to the "who decided this" opacity problem named in The Problem section above.

---

## Outcomes
**Concept-stage targets — none of these are measured results.** Figures below are illustrative estimates for the case study narrative, reasoned from the real OBI baseline and the scope of what the agents are proposed to automate, not from a pilot or usage data:

- **~30% reduction in review cycle time (target)** — reasoned from the research agent front-loading context-gathering, which was the most time-consuming manual step in the real OBI workflow
- **~50% fewer submissions returned for missing information (target)** — extends the real, documented OBI pain point; the research agent surfacing what's missing *before* a reviewer touches the case is the direct mechanism for this improvement
- **Reviewer trust target: ≥80% of pilot reviewers report the activity trail gives them enough information to confirm an agent's routing without independently re-verifying from scratch** — the trust-specific metric, would require the usability testing outlined above to actually measure

*(All three are labeled as targets throughout any deliverable built from this doc — do not present them as achieved results.)*

---

## Reflection / open backlog
- This concept has not yet had its own discovery interviews, competitive analysis, design sprints, or usability testing — those are the actual next steps if Michael wants to build this out further, not just documentation gaps
- Open question carried from the brief: how much to reuse real OBI visuals/structure vs. build fresh concept screens
- Open question: whether "agent proposes, human confirms" is too conservative for a compelling concept piece, or exactly the right restraint for a regulated domain — worth deciding explicitly rather than leaving implicit

---

## Framework check (against `../ai-ux-process-framework.md` Part 4)
- [x] Covers all 8 stages, naming what's the same vs. new — see Discovery, Ideation sections above; Design & Iteration and Usability Testing sections explicitly state they have not yet occurred, which is itself the "what's new/different" honesty this framework requires for concept-stage work
- [x] Addresses relevant Part 2 categories: Agent Accountability & Legibility (the core focus — who acted and why), Human-in-the-loop/Escalation (agent proposes, human confirms), Trust & Explainability (policy-conflict linking). Confidence & Uncertainty and Feedback & Correction loops are not yet designed — flagged as open, not addressed
- [x] Written to the Who/What/When/Why/How template — see `04-compliance-copilot.md`, this doc is that scaffold's full narrative
- [x] Shows a failure/uncertainty path — the agent-conflict and override paths; explicitly does not show a tested failure path since no testing has occurred
- [x] States plainly this is concept/speculative, not shipped — see header and repeated throughout
- [x] Includes trust-specific metrics alongside the business metric — both listed as hypotheses in Outcomes, per the "no fabricated metrics" rule
