# Slides — AI Pattern Library (Epic 3)
Source: `03-ai-pattern-library.md` (brief) + `03-ai-pattern-library-discovery.md` (discovery). Synthesis case study: real design-system leadership at Wells Fargo, Credit Suisse, and BlackRock; the specific component set, audit findings, adoption figures, and quotes below are constructed for this case study, not measured results or verbatim sourced quotes. Each is labeled inline; none should be presented as achieved outcomes or real quotes in any downstream deliverable.

---

## Section Divider / Cover — AI Pattern Library

- **Title**: AI Pattern Library
- **Tagline**: A design system for AI states
- **One-line description**: A defined set of reusable AI-interaction components — confidence, sourcing, in-progress response, correction, human handoff — documented and governed the same way as any other design-system component, so product teams stop reinventing AI trust patterns from scratch.
- **Pull-quote** *(illustrative, constructed for this case study — not a verbatim interview quote)*: "We built confidence three different ways across three teams, and none of them talk to each other."
- **Treatment**: coral gradient banner (`#F5805C` → `#FF8C7A` → `#FFB088`), thin title typography, lime/rust accent bars

---

## Introduction — What's the AI Pattern Library?

- **Description**: A minimal, documented set of AI-interaction components — Confidence/Certainty Indicator, Citation/Source Card, Streaming-Response State, Correction/Feedback Control, Human-Handoff Banner — governed and adopted the same way Michael has run design-system rollouts at Wells Fargo and Credit Suisse, applied here to a new category of interface state that traditional design systems don't cover.
- **Target audience** (teal circle-callout): product designers across multiple teams shipping AI features without a shared component vocabulary
- **The problems** (bulleted, from discovery Pain Points — illustrative, constructed for this case study):
  1. Every team invents its own confidence visualization, with no shared visual or verbal language
  2. Citation/sourcing shown inconsistently across teams, undermining trust in the product family
  3. No shared "still generating" affordance — users can't tell if the system finished or stalled
- **My Role**: Led the design process for this concept, drawing on real design-system governance leadership at Wells Fargo, Credit Suisse, and BlackRock — the specific AI Pattern Library engagement described here is constructed for this case study, not a single real rollout.

---

## KPI Stat Block — Discovery & Research

- **"Why does this matter?"**
- **3+ independently built confidence-indicator treatments found across an internal audit of shipped AI features** *(illustrative audit finding, constructed for this case study, not a literal documented audit)*
- **4 different citation/sourcing display patterns found across the same audit** *(illustrative, same basis)*
- **Discovery methods**: organizational audit of AI features already shipped across product teams; interviews with the designers/PMs who built them and the design-system governance stakeholders who'd need to support adoption; review of publicly published external AI-design guidance as a reference point
- **Problem statement** (from brief WHAT → Problem): standard design systems don't have components for AI-specific states — there's no established pattern for showing a source, showing confidence, showing an in-progress response, or telling the AI it got something wrong

---

## Pain Points from Interviews

1. Every team invents its own confidence visualization, with no shared visual or verbal language for "sure" vs. "not sure"
2. Citation/sourcing shown inconsistently — some teams show it by default, others bury it, some don't show it at all
3. No shared "still generating" affordance — users can't tell if the system finished or stalled
4. No consistent way for a user to tell the system it got something wrong, with no visible consequence where a control exists at all
5. No consistent way to hand off to a human when the AI shouldn't finish the task alone

**Pull-quote** *(illustrative, constructed for this case study, reasoned from pain point #4 — not a verbatim quote)*: "I added a thumbs-down button because it felt right to have one. I have no idea if anyone's ever looked at what it collects."

---

## Persona Card — Product Designer (Adopting Team)

- **Name/Role**: primary persona, a product designer on a team shipping an AI feature, without a design system built for AI-specific states (per brief WHO)
- **Sentiment quote** *(illustrative, reasoned from the documented pain points — not a sourced verbatim)*: "I don't want to invent a confidence indicator from scratch again — I want to know what's already been solved and just use it."
- **Responsibilities**: shipping an AI feature on a deadline, deciding how to show confidence/sourcing/in-progress state/correction/handoff without existing internal guidance
- **Key challenges**: no shared starting point for trust-critical interaction states; uncertainty about what "good" looks like without a documented baseline; risk of shipping something visually and behaviorally inconsistent with the rest of the product family
- **Wishlist**: a documented, pre-validated component set for AI states; clear "when NOT to use this" guidance so adopting the pattern doesn't mean blindly copying it into the wrong context; the same governance support the rest of the design system already gets

*(Fields beyond role and core challenge are reasonably inferred from brief WHO + WHAT + the discovery doc's constructed audit narrative, not sourced from dedicated persona interviews — flagged here per wireframe-describer's underspecified-content convention.)*

---

## Four-Column Framework — Pain Points + Business Goals + UX Strategy = Feature Set

| Pain Points (red `#DF505C`) | Business Goals (blue `#8AD9F8`) | UX Strategy (green `#41854F`) | Feature Set (purple `#7C417E`) |
|---|---|---|---|
| Every team invents its own confidence visualization | Consistency and speed — teams stop reinventing AI interaction patterns from scratch | Audit existing ad hoc AI features to find recurring unsolved problems | Confidence / Certainty Indicator |
| Citation/sourcing shown inconsistently, undermining trust | Users get a predictable experience across products | Define and test a minimal component set with pilot teams before wide rollout | Citation / Source Card |
| No shared "still generating" affordance | Prevent every team from independently (and inconsistently) solving trust-critical states | Run the same governance/adoption playbook already proven for non-AI design systems | Streaming-Response State |
| No consistent correction or handoff path | | Document each component with use case, "when NOT to use," and a WCAG pass | Correction / Feedback Control + Human-Handoff Banner |

---

## Design/Process — 8-Stage AI-Enhanced UX Process

- **Discovery & Research**: Same as always — an organizational audit and stakeholder interviews, the same starting point Michael has used for every real design-system engagement. New in the AI-native version: mapped what's genuinely reusable across any AI feature (the shape of a confidence signal) vs. what's necessarily product-specific (the actual model output), a boundary question that didn't exist for buttons and modals.
- **Problem Definition**: Same as always — synthesized the audit into a named pain-point list. New: separated "the pattern doesn't exist yet" (a design system can solve this) from "users don't trust AI output in this domain" (only the interaction design of each component, not the existence of a shared pattern, solves that).
- **Competitive / Pattern Analysis**: New in AI-native version — the "competitor" is internal (every other team's ad hoc solution), benchmarked against publicly published external AI-design guidance as a reference point, not a traditional feature-parity competitor scan.
- **Design Thinking & Ideation**: New in AI-native version — ideation defined each component's *behavior* (what a confidence signal represents, when a handoff triggers) independent of any one product's implementation, plus the adoption/governance question treated as part of ideation, not an afterthought.
- **Design Sprints & Iteration**: Same cadence as prior non-AI design-system work — iterative rounds with pilot teams. New: iterating on a component whose underlying data is non-deterministic (a confidence score, a streaming response) rather than a fixed screen.
- **Usability Testing**: New in AI-native version — tested trust and comprehension at the component level (does a user act differently when sourcing is shown by default) *and* adoption at the governance level (do teams actually implement the pattern as documented) — two testing layers a traditional design-system rollout doesn't need.
- **Delivered Solution**: The "component" delivered is a state/behavior (a confidence signal, a handoff trigger) as much as a screen — v1 ships 5 documented components, each with an explicit boundary between what the pattern owns and what stays product-specific.
- **Outcomes**: See Results below — targets, not measured results.

**Callout — What We Learned (green)**: The confidence indicator's first draft used red/yellow/green — pilot review found red collided with the org's existing error-color language, reading as "something's broken" instead of "the system isn't sure." *(Illustrative iteration finding, constructed for this case study.)* Redesigned around a neutral intensity scale plus a plain-text qualifier, removing the color-only signal entirely — an accessibility fix that also happened to fix the semantic collision.

`[VISUAL: Confidence / Certainty Indicator — Specimen Sheet, from 03-ai-pattern-library-wireframes.md]`

---

## KPI Stat Block — Results (targets, not measured)

- **Adoption: 4 of 6 actively AI-shipping product teams within two quarters of v1 publication (target)**
- **~70% reduction in one-off/inconsistent AI UI patterns flagged in design review (target)**
- **~1-2 designer-days saved per new AI feature by not re-solving these states from scratch (illustrative estimate)**
- **Trust target: aggregate confidence-indicator override/disagreement rate in the 5-15% range once embedded (target, framed as a healthy-use signal, not a failure metric)**

*(All four explicitly labeled as targets/estimates — this component set has not been piloted or measured in a real rollout.)*

---

## Key Insight

> The hard part was never designing a confidence indicator or a citation card — those are solvable in a sprint. The hard part is the same one every design system eventually runs into: getting competing product teams, each under their own deadline, to actually adopt a shared pattern instead of shipping their own. For AI-specific states, that governance problem is higher-stakes than usual, because the pattern being skipped isn't a button style — it's the interaction that decides whether a user trusts the answer at all.

*(Pulled from brief HOW → core design challenge; this is the most concrete design-judgment statement in the source material. Per CLAUDE.md's working agreement, this slide must survive intact even if others are trimmed.)*

`[VISUAL: Governance & Adoption Dashboard, from 03-ai-pattern-library-wireframes.md]`

---

## Consistency Check

- [x] All 9 slides present, in order
- [x] Phase language matches CLAUDE.md's 8-stage names exactly
- [x] Key Insight slide present and substantive, not trimmed
- [x] No fabricated metrics presented as real — all figures labeled illustrative/target/estimate
- [x] No fabricated quotes presented as verbatim — both pull-quotes and the persona sentiment quote explicitly labeled illustrative/constructed
- [x] Visual placeholders marked, referencing the wireframes doc
- [x] Content synthesized beyond the brief/discovery (audit findings, adoption figures, iteration finding, persona detail) is flagged inline, not presented as sourced fact
