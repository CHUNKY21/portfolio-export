# Connected Vehicle Assistant
**American Honda** | Multi-agent concept extending real Honda service-design research
*Real client, real prior discovery work (Honda customer-interview and journey-mapping engagements) — the multi-agent Connected Vehicle Assistant concept itself is speculative/unshipped, extending that real foundation into a forward-looking design.*

Status: **Concept / speculative** (not shipped) — built to the standard set in `../ai-ux-process-framework.md`, checked against its Part 4 completeness list at the bottom of this doc. Every section below is explicit about what's carried over from real Honda research vs. what's proposed/hypothesized for this concept.

---

## Summary
A concept extending Michael's real American Honda service-design work: instead of an owner receiving fragmented, one-off notifications — a maintenance reminder here, a diagnostic alert there — a multi-agent system — a scheduling agent, a diagnostics agent, and a service-recommendation agent — coordinates behind a single owner-facing assistant, with every entry in the assistant's feed labeled by which agent generated it. Positioned honestly as a vision piece: it demonstrates agent-coordination and legibility design (the same core challenge as Epic 4, applied to a second industry and a consumer rather than enterprise audience), not shipped results.

---

## The Problem
Real Honda service-design research (customer interviews and journey mapping, conducted as part of Michael's prior American Honda engagement) established that connected-vehicle owners today receive disconnected, one-off notifications: a maintenance-due reminder from one part of the system, a diagnostic/warning-light alert from another, with no single assistant tying scheduling, vehicle health, and service recommendations together. That fragmentation is the real, documented starting point for this concept — owners are left to interpret and reconcile each alert themselves.

This concept asks the next question: if three specialized agents — one watching vehicle health, one managing scheduling, one generating service recommendations — each had a reason to reach the owner, what breaks? The risk is twofold: **opacity** (the owner can't tell which system is telling them what, or why) and **notification pile-up** (three independently-triggering agents produce more noise, not less, unless something unifies them).

**Why this matters:** a missed or misunderstood maintenance signal is not just an inconvenience — it's the mechanism behind costlier repairs, safety risk, and a weaker owner-to-dealer relationship. A multi-agent system that replaces three disconnected notification sources with three disconnected *agents* is a regression, not an improvement — which is why this concept treats a single unified, labeled feed as the central design problem, not a nice-to-have layered on afterward.

---

## Discovery & Research
**Carried over from real Honda service-design research** (not re-run for this concept):
- Customer interviews and journey-mapping work conducted as part of Michael's real American Honda service-design engagement
- The core documented pain point: owners get fragmented, one-off notifications with no unified assistant tying scheduling, diagnostics, and service recommendations together

**New for this concept — AI-native addition to discovery:**
- Mapped which parts of the ownership experience are plausibly agent-automatable (translating a diagnostic code into plain language, proposing a scheduling slot, generating a service recommendation from health data) vs. which require human judgment (a technician's actual repair diagnosis, a service advisor's negotiation with the owner on cost or timing) — this boundary is the concept's central design decision, not an implementation detail
- Surfaced the owner's likely trust baseline toward automated diagnostic claims specifically — per `../ai-ux-process-framework.md` Part 1's own framing, "a compliance reviewer and a vehicle owner start from very different trust baselines": a vehicle owner is not reading a warning light as an audit-relevant judgment call, they're reading it as "is my car safe to drive today," which raises the cost of a wrong-but-confident explanation
- **This concept has not had its own dedicated discovery interviews conducted yet** — that's an open next step, not something to backfill with invented findings

**Pain point carried over (real, from the brief's stated Honda research):**
1. Owners receive fragmented, one-off notifications (a maintenance reminder here, a diagnostic alert there) with no unified assistant tying scheduling, diagnostics, and service recommendations together

*[This is the one real, sourced pain point this concept builds on, as stated in the brief. No additional pain-point interviews have been conducted specifically for the multi-agent concept — do not add fabricated pain points beyond this one.]*

**Baseline estimate (illustrative, not sourced from Honda usage data):** an estimated ~1 in 3 service-center calls in this segment are owners asking what a dashboard warning light or notification means, rather than booking or describing a symptom — used in deliverables as the "why this matters" framing stat, clearly labeled as an illustrative estimate rather than a measured figure.

### Competitive / pattern analysis
Not yet conducted for this concept specifically. Worth benchmarking against how other connected-vehicle apps and adjacent consumer telematics products (other OEM apps, aftermarket diagnostic/fleet-management tools) handle multi-source alert consolidation and plain-language translation of diagnostic codes before this concept is built out further — flagged as an open next step, not completed research.

---

## Design Thinking / Ideation
The central ideation question for this concept: **when three agents (scheduling, diagnostics, service-recommendation) can each independently decide to reach the owner, how does the owner get one coherent assistant instead of three competing notification sources?**

Three behavior questions frame the concept, following the same "define the behavior before the screen" approach used in Epic 1 and Epic 4:
- What does each agent surface when it acts — a raw code/label (e.g., a warning-light code), or a plain-language explanation of what it means and what to do next? (Working answer: always the latter — a code alone is exactly the gap the real Honda research identified.)
- When two agents' outputs relate to the same underlying issue (e.g., the diagnostics agent flags a symptom right as the service-recommendation agent would suggest addressing it), how is that surfaced — as two separate feed entries, or merged into one entry with sub-attribution? (Working answer: merged — this is the concept's direct answer to the notification-pile-up risk named in The Problem.)
- Where's the line between "an agent can act and reach the owner automatically" and "an agent can only propose, and the owner must confirm"? Working assumption: diagnostics and recommendation content can surface ambiently and automatically (it's informational), but anything with a scheduling or cost implication — booking an appointment, confirming a service — requires the owner's explicit one-tap confirmation. This concept does not propose agents auto-booking service without owner consent.

---

## Design & Iteration
Not yet run — this concept has not entered a design-sprint cycle. The pattern below is the proposed direction, not a tested/iterated outcome.

**Proposed key interaction pattern:**
- **Unified assistant feed/thread** — a single chronological stream, not three separate notification sources, where every entry carries a visible agent label (diagnostics, scheduling, or service-recommendation) so the owner always knows which system is talking, extending the same agent-legibility principle established in Epic 4's activity trail
- **Plain-language diagnostic translation** — every diagnostics-agent alert is paired with a plain-language explanation and a recommended next step, never a bare code or warning label alone (this directly answers the real Honda pain point and the "what does this alert mean" call driver)
- **Entry consolidation** — when multiple agents' outputs relate to the same underlying vehicle issue, they're merged into one feed entry with sub-attribution (e.g., "Diagnostics flagged this — Service recommendation attached"), rather than presented as separate notifications
- **One-tap scheduling action** — a scheduling suggestion is actionable directly in the feed entry (propose a slot, confirm), not a handoff to a separate app or flow, per the brief's acceptance criteria

**Open design question, now resolved for this concept:** the brief left open whether this should be an in-vehicle interface, a mobile app, or both, and explicitly recommended picking one to keep the case study focused. **Decision: mobile app is the primary and only surface designed for this concept.** Reasoning: the owner's dominant relationship to service scheduling and diagnostic follow-up happens away from the vehicle (before or after a drive, when deciding whether to call the dealer), and a mobile surface supports the "propose, owner confirms" scheduling pattern far better than an in-vehicle screen would while driving. An in-vehicle glanceable summary (e.g., a dashboard-level "1 new item in your assistant" indicator) is a plausible v2 extension, explicitly out of scope for this concept's screens.

**Scope decision on the secondary persona:** the brief names the dealer/service advisor as a secondary persona who receives service recommendations. For this concept, the dealer-facing side of that handoff (how a service advisor's system receives and displays an assistant-initiated recommendation) is treated as out of scope for the screens built here — this concept designs the owner-facing assistant only, with the handoff to the dealer represented as a single "request appointment" action rather than a fully designed dealer-side interface.

---

## Usability Testing
**Not yet conducted.** This is a concept/vision piece, not a shipped or tested feature — presenting fabricated testing results here would misrepresent it. The validation plan, if this concept moves forward, would need to test:
- Whether owners can correctly attribute a feed entry to the right agent and reason (multi-agent legibility, not just "did they see the notification")
- Whether entry consolidation actually reduces perceived notification fatigue compared to the real, documented baseline of separate one-off notifications, or whether it introduces its own confusion (e.g., owners missing that a merged entry contains more than one thing)
- Trust calibration specifically for diagnostic claims — per the Discovery section's framing, an owner's trust baseline toward "is my car safe" content is different from a compliance reviewer's, and needs its own testing rather than reusing Epic 4's findings by assumption

---

## Delivered Solution
**Not shipped.** The proposed concept: an owner-facing mobile assistant presents a single unified feed. A diagnostics agent watches vehicle health continuously and surfaces plain-language alerts ambiently; a service-recommendation agent generates suggestions from that same health data and attaches them to the relevant diagnostic entry rather than posting separately; a scheduling agent proposes an appointment slot directly in the feed, actionable in one tap. Every entry is labeled by its originating agent. Informational content (diagnostics, recommendations) surfaces automatically; anything with a scheduling or cost implication requires the owner's explicit confirmation before it's finalized — agents propose, the owner confirms. This boundary is the concept's answer to both risks named in The Problem: opacity (solved by per-entry agent labeling) and notification pile-up (solved by consolidation).

---

## Outcomes
**Concept-stage targets — none of these are measured results.** Figures below are illustrative estimates for the case study narrative, reasoned from the real Honda pain point and the scope of what the agents are proposed to automate, not from a pilot or usage data:

- **~20% uplift in service-scheduling conversion from an assistant-initiated prompt (target)** — reasoned from the one-tap, in-feed scheduling action removing the handoff-to-a-separate-flow friction named in the brief's acceptance criteria
- **~35% reduction in "what does this alert mean" service-center calls (target)** — extends the real, documented Honda pain point (fragmented, unexplained notifications); the plain-language diagnostic translation is the direct proposed mechanism for this improvement
- **Owner trust target: ≥75% of pilot owners report the assistant helped them understand their vehicle's status without needing to call the dealer** — the trust-specific metric; would require the usability testing outlined above to actually measure

*(All three are labeled as targets throughout any deliverable built from this doc — do not present them as achieved results.)*

---

## Reflection / open backlog
- This concept has not yet had its own discovery interviews, competitive analysis, design sprints, or usability testing — those are the actual next steps if Michael wants to build this out further, not just documentation gaps
- Resolved from the brief: in-vehicle vs. mobile vs. both — this concept commits to mobile-only, with an in-vehicle glanceable summary flagged as a plausible v2 extension, not designed here
- Resolved scope decision: the dealer/service-advisor side of the handoff is represented as a single action, not a fully designed second interface, in this pass
- Open question, not yet resolved: whether the scheduling agent should be allowed to hold a tentative slot pending owner confirmation (reducing friction) vs. only ever proposing without reserving anything (avoiding any appearance of an unconfirmed commitment) — worth deciding explicitly before this concept enters a design-sprint cycle

---

## Framework check (against `../ai-ux-process-framework.md` Part 4)
- [x] Covers all 8 stages, naming what's the same vs. new — see Discovery, Ideation sections above; Design & Iteration and Usability Testing sections explicitly state they have not yet occurred, which is itself the "what's new/different" honesty this framework requires for concept-stage work
- [x] Addresses relevant Part 2 categories: Agent Accountability & Legibility (the core focus — which agent surfaced what, entry consolidation), Human-in-the-loop/Escalation (agent proposes, owner confirms for anything scheduling/cost-related), Trust & Explainability (plain-language diagnostic translation). Confidence & Uncertainty and Feedback & Correction loops are not yet designed — flagged as open, not addressed
- [x] Written to the Who/What/When/Why/How template — see `05-connected-vehicle-assistant.md`, this doc is that scaffold's full narrative
- [x] Shows a failure/uncertainty path — the notification-pile-up risk and its consolidation answer; explicitly does not show a tested failure path since no testing has occurred
- [x] States plainly this is concept/speculative, not shipped — see header and repeated throughout
- [x] Includes trust-specific metrics alongside the business metric — both listed as hypotheses in Outcomes, per the "no fabricated metrics" rule
