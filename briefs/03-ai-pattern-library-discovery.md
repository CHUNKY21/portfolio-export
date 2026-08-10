# AI Pattern Library
**Design system for AI states** | Synthesis case study — not tied to one employer or one shipped product
*Draws on Michael's real design-system leadership at Wells Fargo, Credit Suisse, and BlackRock — the specific "AI Pattern Library" described here (a defined 4-6 component set, adopted by named product teams) is a constructed narrative built to show what that leadership experience implies when applied to AI-native surfaces, not a single real shipped rollout.*

Status: **Synthesis** — grounded in real design-system leadership at Wells Fargo, Credit Suisse, and BlackRock; the specific AI-pattern component set and adoption narrative described here is constructed for this case study, not sourced from a single real rollout. Built to the standard set in `../ai-ux-process-framework.md`, checked against its Part 4 completeness list at the bottom of this doc. Every adoption metric, audit finding, and quote below is a labeled illustrative target or example — none is presented as a sourced, measured fact.

---

## Summary
A synthesis case study: what happens when the governance and adoption playbook Michael has run for traditional (deterministic) design systems at Wells Fargo, Credit Suisse, and BlackRock gets pointed at a new problem — AI features that don't have a shared vocabulary for confidence, sourcing, in-progress response, correction, or handoff. Rather than each product team inventing its own answer, this case study walks through auditing the ad hoc patterns already in the wild, defining a minimal five-component AI Pattern Library, piloting it with a small set of product teams, and running the same documentation/governance structure used for the org's existing non-AI system. **Illustrative target: adopted by 4 of 6 actively AI-shipping product teams within two quarters of v1 publication** — a target framing this narrative around, not a measured result.

---

## The Problem
Every one of Michael's design-system engagements has started from the same root cause: without a shared, documented component vocabulary, product teams don't coordinate — they each solve the same interface problem slightly differently, and the result is an inconsistent product family even when every individual team is doing competent work. That's the real, recurring pattern behind the Wells Fargo, Credit Suisse, and BlackRock design-system work.

AI features expose a new version of that same root cause, in a place the existing design systems weren't built to cover. A traditional design system has a button, a table, a modal, a form-validation state — it does not have an agreed answer for "here's a source citation," "here's how sure the system is," "the response is still streaming in," or "tell the system it got this wrong." So teams shipping AI features today are back to solving those problems independently, the same way every team solved buttons and modals independently before a design system existed — except now the stakes are trust-related, not just visual-consistency-related.

**Illustrative audit finding, constructed for this case study, not a literal documented audit:** a review of AI features shipped across the org's product teams surfaced at least three independently built confidence-indicator treatments (a percentage, a color-coded pill, and a plain-text qualifier — none sharing a visual language) and four different ways of showing where an AI answer's source material came from, ranging from inline citations to a buried "show sources" link.

- No shared pattern for signaling AI-generated confidence — every team re-derives its own visual language
- No shared pattern for source attribution — some teams show it by default, some hide it behind a click, some don't show it at all
- No shared pattern for "this is still generating" vs. "this is the final answer" — several teams used a generic spinner that gave users no sense of progress or scope
- No shared way for a user to flag a wrong answer, and where a way exists, it isn't visibly connected to any consequence
- No shared pattern for the moment an AI feature should stop and hand off to a human, rather than guess

**Why this mattered:** this isn't a cosmetic inconsistency problem. Confidence, sourcing, and correction are exactly the interaction moments that determine whether a user trusts an AI feature at all — the same "trust calibration" concern that came up independently in Epic 1's discovery work. Letting every team solve trust-critical interactions from scratch means the org's overall trust posture is only as strong as its least-considered AI feature, and no single team is positioned to fix that — it's a design-system-shaped problem, not a single-product-shaped one.

---

## Discovery & Research
Discovery here isn't user interviews for a single product — it's the same organizational audit and stakeholder-alignment process used to start any design-system engagement (Wells Fargo, Credit Suisse), turned toward AI-specific surfaces.

- Inventoried AI features already shipped or in flight across product teams, cataloguing how each currently handles confidence, sourcing, in-progress response, correction, and handoff
- Talked to the designers and PMs on those teams about what they built, why, and what they'd do differently if a shared starting point existed
- Talked to the design-system governance stakeholders (engineering leads for component implementation, product leads whose teams would need to adopt) about what would make a shared pattern set something teams actually use rather than route around
- **AI-native addition to standard discovery:** mapped, per candidate component, what's genuinely reusable across any AI feature (the *shape* of a confidence indicator, a citation card, a streaming state) vs. what's necessarily product-specific (the underlying model, the specific data being cited, the domain-specific confidence threshold) — this boundary is what makes a shared component set possible without forcing every team into an identical AI implementation
- Looked at publicly published AI-design guidance from other design systems (e.g., IBM's Carbon for AI, Google's PAIR guidelines) as an external reference point for how the wider industry frames confidence and uncertainty — used to sanity-check the internal audit's findings, not copied wholesale

**Pain points heard from interviews (illustrative examples, constructed for this synthesis case study, reasoned from the recurring pattern real design-system audits surface — not verbatim sourced quotes):**
1. Every team invents its own confidence visualization, with no shared visual or verbal language for "sure" vs. "not sure"
2. Citation/sourcing is shown inconsistently — some teams follow "show your work by default," others bury it, undermining trust across the product family even where the underlying model quality is fine
3. Streaming/in-progress states range from a generic spinner to token-by-token text with no shared affordance for "still working" vs. "done" — users can't tell if the system finished or stalled
4. No consistent way for a user to tell the system it got something wrong, and where feedback controls exist, nothing visibly happens with that input
5. No consistent way to hand off to a human when the AI shouldn't finish the task alone — inconsistent from a dead-end error message to no handoff path at all

### Competitive / pattern analysis
The "competitor" here is internal: every other product team's ad hoc solution to the same problem, which is the audit described above. Externally, publicly available AI-design guidance from other companies' design systems was used as a reference point for how the industry is converging (or not) on shared conventions for confidence and uncertainty — this shaped the case for why a shared internal vocabulary was worth building now rather than waiting, but wasn't treated as a template to copy directly, since none of those external systems map exactly onto this org's product mix.

---

## Design Thinking / Ideation
Ideation for a design system serving AI features isn't just "design 5 components" — it's defining the *behavior* each component represents, independent of any one product's implementation, so the component stays useful across products with different models, domains, and risk profiles. Three questions framed the ideation phase:

- What's the smallest set of components that covers the recurring problems named in the audit, without trying to solve every AI interaction pattern in v1?
- For each component, what's the line between what the pattern *standardizes* (visual language, interaction behavior, accessibility baseline) and what stays product-specific (the actual confidence score, the actual cited source, the actual escalation destination)?
- How does this pattern set actually get adopted by teams that are used to shipping fast and solving their own problems — component design and governance/rollout design had to be treated as one problem, not two, from the start

That last question mattered most, consistent with the brief's framing that the core design challenge here is governance and adoption, not just component design. A well-designed confidence indicator that no team actually uses doesn't solve the problem named above — it just becomes a sixth ad hoc pattern nobody adopted.

**Component set defined (5 of the 6 candidates named in the brief; "empty/no-answer state" deferred — see Reflection):**
1. **Confidence / Certainty Indicator** — signals how sure the system is in its own output
2. **Citation / Source Card** — shows where an AI answer's underlying material came from
3. **Streaming-Response State** — shows a response still generating vs. complete
4. **Correction / Feedback Control** — lets a user tell the system an answer was wrong or incomplete
5. **Human-Handoff Banner** — signals the system is stopping and routing to a human, and why

---

## Design & Iteration
Following the same design-sprint cadence used for the org's existing non-AI design-system work: define a first draft of each component, pilot it with a small set of product teams, iterate based on what breaks, then document to the same governance standard as the rest of the system.

**Pilot teams (illustrative, generic archetypes constructed for this case study — not named real products):** a research-agent surface, a compliance-review surface, and a customer-support AI surface — chosen to cover a spread of risk profile and audience (internal analyst tool, internal case-review tool, external-facing chat assist), so the component set would have to hold up outside a single narrow use case before wider rollout.

**What changed across iterations (illustrative iteration finding, constructed for this case study, not a documented real finding):** the Confidence Indicator's first draft used a three-tier red/yellow/green treatment. Pilot-team review flagged that red read as "error," not "low confidence" — colliding with the org's existing error/validation color language elsewhere in the design system. The indicator was redesigned around a neutral intensity scale (filled-to-empty segments) plus a plain-text qualifier ("High confidence" / "Partial — verify before use"), removing the error-color collision and making the pattern legible independent of a color-only signal, for accessibility as well as semantic clarity.

**Documentation standard applied per component (per brief acceptance criteria):**
- A defined use case
- An explicit "when NOT to use this" note
- An accessibility/WCAG pass (contrast, non-color-only signaling, screen-reader labeling)
- Do/don't visual examples, in the same format as the org's existing non-AI component documentation

---

## Usability Testing
Testing here has two layers, consistent with running a design-system rollout: does the *component* work for end users, and does the *pattern set* actually get adopted by product teams (the governance-side test).

**Component-level testing (illustrative findings, constructed for this case study, consistent with the trust-calibration finding independently documented in Epic 1):**
- Tested comprehension and trust, not just visual recognition — did a user reading the Citation/Source Card actually know where an answer came from, did the Confidence Indicator change what a user was willing to act on without double-checking
- Citation/Source Card testing echoed Epic 1's finding: showing sourcing by default, not behind a click, measurably changed how much users trusted an otherwise-identical answer
- Correction/Feedback Control testing found that a control with no visible consequence (a thumbs-down that just disappears) was worse than no control at all — users described it as "shouting into a void," which drove the decision to require every adopting team's implementation to show *some* visible acknowledgment when feedback is given, even if the underlying model doesn't retrain in real time

**Governance/adoption-side testing:**
- Piloted the documented v1 set with the three pilot teams before wider publication, watching specifically whether teams adopted the pattern as specified or modified it enough that "consistency" broke down again
- Iterated the documentation format itself after the first pilot team asked for a stricter "when NOT to use this" section — teams were more willing to adopt a pattern when the documentation was explicit about its limits, not just its ideal case

---

## Delivered Solution
The v1 AI Pattern Library: five documented components — Confidence/Certainty Indicator, Citation/Source Card, Streaming-Response State, Correction/Feedback Control, and Human-Handoff Banner — each shipped with a defined use case, a "when NOT to use this" note, an accessibility/WCAG pass, and do/don't examples, published in the same governance structure as the org's existing non-AI design system rather than as a separate, lower-priority artifact.

**Illustrative before/after comparison, constructed for this case study (per acceptance criteria: 2-3 product teams shown adopting the same component):** before adoption, the research-agent, compliance-review, and customer-support pilot teams each rendered confidence three different ways (a raw percentage, a colored pill, a plain-text qualifier). After adoption, all three use the same intensity-scale-plus-qualifier pattern, differing only in the product-specific confidence threshold each team's model surfaces — the shared visual language now sits on top of team-specific model behavior instead of each team reinventing both at once.

What the component set owns vs. what stays product-specific is explicit throughout the documentation: the pattern standardizes visual language, interaction behavior, and accessibility baseline; each adopting team still owns its own model output, confidence scoring logic, and (for the Human-Handoff Banner) its own actual escalation destination.

---

## Outcomes
**Illustrative targets, constructed for this case study — none of these are measured results:**

- **Adoption: 4 of 6 actively AI-shipping product teams within two quarters of v1 publication (target)** — the primary business-goal metric named in the brief
- **~70% reduction in one-off/inconsistent AI UI patterns flagged in design review, measured against the pre-library audit baseline (target)**
- **~1-2 designer-days saved per new AI feature by not re-solving confidence/citation/streaming/correction/handoff from scratch (illustrative estimate)**
- **Trust-specific metric: aggregate confidence-indicator override/disagreement rate, tracked as a shared cross-team metric once the component is embedded in production (illustrative target range: 5-15%)** — framed as a healthy-use signal, not a failure metric, consistent with how Epic 1 treats escalation-to-human rate: some override is expected and desirable if the confidence signal is well-calibrated, and a rate near zero would suggest the indicator isn't actually influencing behavior

*(All figures above are targets and estimates reasoned from the constructed audit/pilot narrative in this doc, not from a real rollout. Any deliverable built from this doc must keep them labeled as such.)*

---

## Reflection / open backlog
- **Empty/no-answer state** — the sixth candidate component named in the brief — was deferred out of v1. Rationale: the pilot teams' AI features rarely hit a true "no answer" case cleanly; the pattern needs its own dedicated discovery pass rather than being drafted speculatively alongside the other five, so it's carried forward as the first v2 backlog item rather than rushed into v1
- Open governance question: how to keep the library's review/contribution process lightweight enough that product teams propose new AI-state patterns through it, rather than shipping one-offs and routing around governance the same way the original audit found teams doing before the library existed — this is the same adoption risk that motivated the whole case study, and it doesn't fully go away once v1 ships
- Forward link to Epics 4 & 5: those are multi-agent concepts, and this v1 library is deliberately scoped to single-agent AI states (one system, one confidence signal, one citation set). A multi-agent surface needs an additional pattern this library doesn't cover — per-agent attribution and an activity trail across agents, which Epic 4's Compliance Co-Pilot concept sketches independently. Extending the AI Pattern Library to cover multi-agent legibility is flagged as a real, unaddressed gap, not solved here

---

## Framework check (against `../ai-ux-process-framework.md` Part 4)
- [x] Covers all 8 stages, naming what's the same vs. new — Discovery (org-wide audit standing in for user interviews), Ideation (component + governance defined together), Design & Iteration (pilot teams, iteration on the confidence indicator), Testing (component-level and governance-level), Delivered Solution (component set + adoption boundary), Outcomes (adoption/consistency/trust metrics) all above
- [x] Addresses relevant Part 2 categories: Trust & Explainability (Citation/Source Card), Confidence & Uncertainty (Confidence/Certainty Indicator), Human-in-the-loop/Escalation (Human-Handoff Banner), Feedback & Correction Loops (Correction/Feedback Control). **Agent Accountability & Legibility does not apply to this case study** — this is a single-agent-state pattern set (one system's confidence, sourcing, streaming, correction, handoff), not a multi-agent case study; per-agent attribution and cross-agent activity trails are explicitly out of scope here and flagged as a real gap for future work in Reflection above, and are the subject of Epics 4 and 5 instead
- [x] Written to the Who/What/When/Why/How template — see `03-ai-pattern-library.md`, this doc is that scaffold's full narrative
- [x] Shows a failure/uncertainty path, not just the happy path — the Confidence Indicator's low-confidence state, the Correction Control's "flag it's wrong" path, and the Human-Handoff Banner (the component set's dedicated failure/escalation pattern) all address this directly
- [x] States plainly this is a synthesis case study — real design-system leadership, constructed component set and adoption narrative — see header and Status line, restated at each metric/quote throughout
- [x] Includes trust-specific metrics alongside the standard business metric — see Outcomes (confidence-indicator override/disagreement rate alongside adoption and consistency metrics)
