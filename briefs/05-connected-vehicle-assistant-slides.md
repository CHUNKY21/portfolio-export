# Slides — Connected Vehicle Assistant (Epic 5)
Source: `05-connected-vehicle-assistant.md` (brief) + `05-connected-vehicle-assistant-discovery.md` (discovery). Concept-stage: metrics and quotes below are illustrative/target figures reasoned from the real, documented Honda pain point and this concept's proposed scope — not measured results. Each is labeled inline; none should be presented as achieved outcomes in any downstream deliverable.

---

## Section Divider / Cover — Connected Vehicle Assistant

- **Title**: Connected Vehicle Assistant
- **Tagline**: A multi-agent concept for one coherent owner-facing assistant
- **One-line description**: Extends Michael's real American Honda service-design research into a concept where a scheduling agent, a diagnostics agent, and a service-recommendation agent coordinate behind a single owner-facing assistant — with every entry labeled by which agent generated it.
- **Pull-quote** *(illustrative — reasoned from the documented fragmented-notifications pain point, not a verbatim interview quote)*: "I get an alert, a reminder, and a text — and none of them talk to each other, so I don't know what actually matters."
- **Treatment**: coral gradient banner (`#F5805C` → `#FF8C7A` → `#FFB088`), thin title typography, lime/rust accent bars

---

## Introduction — What's the Connected Vehicle Assistant?

- **Description**: A concept where a vehicle owner's scheduling, diagnostics, and service-recommendation needs are handled by three specialized agents feeding one unified assistant feed, instead of three disconnected one-off notification sources.
- **Target audience** (teal circle-callout): Vehicle owner using a connected-vehicle mobile app
- **The problems** (bulleted, from discovery's Pain Points — real, sourced from prior Honda service-design research):
  1. Owners receive fragmented, one-off notifications (a maintenance reminder here, a diagnostic alert there) with no unified assistant tying scheduling, diagnostics, and service recommendations together
- **My Role**: Extends design and discovery work from Michael's real American Honda service-design engagement into this forward-looking multi-agent concept.

---

## KPI Stat Block — Discovery & Research

- **"Why does this matter?"**
- **~1 in 3 service-center calls in this segment are owners asking what an alert means, rather than booking or describing a symptom** *(illustrative estimate, not sourced from Honda usage data — used for "why this matters" framing only)*
- **Discovery methods** (real, carried over from prior Honda engagement): customer interviews and journey-mapping work
- **Problem statement** (from brief WHAT → Problem): owners get fragmented, one-off notifications with no unified assistant tying scheduling, diagnostics, and service recommendations together

---

## Pain Points from Interviews

1. Owners receive fragmented, one-off notifications (a maintenance reminder here, a diagnostic alert there) with no unified assistant tying scheduling, diagnostics, and service recommendations together

**Pull-quote** *(illustrative — reasoned from the pain point above, not a verbatim quote)*: "Every alert feels like it's from a different app, even though it's the same car."

*(This concept builds from one real, documented pain point, per the brief — additional pain points are not fabricated to pad this list.)*

---

## Persona Card — Vehicle Owner

- **Name/Role**: primary persona, vehicle owner using a connected-vehicle mobile app (per brief WHO)
- **Sentiment quote** *(illustrative, reasoned from the documented pain point — not a sourced verbatim)*: "Just tell me plainly what's wrong and what I need to do — I don't want to decode a warning light myself."
- **Responsibilities**: keeping up with vehicle maintenance, interpreting alerts and reminders, deciding when and where to schedule service
- **Key challenges**: fragmented notifications from separate sources, uncertainty about what a diagnostic alert actually means or how urgent it is, friction in going from "I got an alert" to "I have an appointment"
- **Wishlist**: one place to see everything about their vehicle's status, plain-language explanations instead of codes, one-tap scheduling instead of a separate app or phone call

*(Fields beyond role and core challenge are reasonably inferred from brief WHO + WHAT, not sourced from dedicated persona interviews for this concept — flagged here per wireframe-describer's underspecified-content convention.)*

---

## Four-Column Framework — Pain Points + Business Goals + UX Strategy = Feature Set

| Pain Points (red `#DF505C`) | Business Goals (blue `#8AD9F8`) | UX Strategy (green `#41854F`) | Feature Set (purple `#7C417E`) |
|---|---|---|---|
| Fragmented, one-off notifications with no unifying assistant | Increase service-scheduling conversion, reduce missed-maintenance issues | Extend real Honda service-design findings, not start from zero | Diagnostics agent (plain-language alert translation) |
| No plain-language explanation of diagnostic alerts | Strengthen the owner-to-dealer relationship | Agent proposes, owner confirms for anything scheduling/cost-related | Scheduling agent (proposed slots, one-tap confirm) |
| Scheduling suggestions require a separate app/flow handoff | | Single unified feed with per-entry agent labeling and consolidation | Service-recommendation agent |
| | | | Unified assistant feed/thread UI + diagnostic detail + scheduling action screen |

---

## Design/Process — 8-Stage AI-Enhanced UX Process

- **Discovery & Research**: Same as always — real customer interviews and journey-mapping work (carried over from prior Honda engagement). New in AI-native version: explicitly mapped which parts of the ownership experience are agent-automatable (diagnostic translation, scheduling proposals, recommendations) vs. requiring human judgment (a technician's actual diagnosis), and surfaced the owner's distinct trust baseline toward automated diagnostic claims.
- **Problem Definition**: Same as always — synthesized the fragmented-notifications pain point. New: separated "the notifications are disconnected" (an agent-coordination pattern can help) from "I don't trust what a warning light is telling me" (only interaction design, not a feature, solves this).
- **Competitive / Pattern Analysis**: *Not yet conducted for this concept* — flagged as an open next step, not completed research.
- **Design Thinking & Ideation**: New in AI-native version — ideation centered on agent *behavior* before any screen: what each agent surfaces, how related agent outputs are merged rather than piled up, and where the agent-proposes/owner-confirms line sits.
- **Design Sprints & Iteration**: *Not yet run.* The unified feed, plain-language diagnostic translation, entry consolidation, and one-tap scheduling pattern below are proposed, not tested/iterated. The brief's open surface question (in-vehicle vs. mobile vs. both) is resolved here: mobile-only, decided explicitly in the discovery doc.
- **Usability Testing**: *Not yet conducted.* This is a concept/vision piece — no fabricated test results are presented.
- **Delivered Solution**: Concept only — agents propose and surface; the owner's confirmation finalizes anything with a scheduling or cost implication.
- **Outcomes**: See Results below — targets, not measured results.

**Callout — Unexpected Challenge (red)**: The hardest open question for this concept isn't whether each individual agent is accurate — it's whether stitching three independently-triggering agents together actually reduces notification volume for the owner, or just relabels the same volume with better attribution. That's why entry consolidation, not just agent labeling, is treated as a first-class design decision rather than a visual polish step.

`[VISUAL: Unified Assistant Feed screen, from 05-connected-vehicle-assistant-wireframes.md]`

---

## KPI Stat Block — Results (targets, not measured)

- **~20% uplift in service-scheduling conversion from an assistant-initiated prompt (target)**
- **~35% reduction in "what does this alert mean" service-center calls (target)**
- **≥75% of pilot owners report the assistant helped them understand their vehicle's status without needing to call the dealer (trust target)**

*(All three explicitly labeled as targets — this concept has not been piloted or tested.)*

---

## Key Insight

> When three agents can each independently decide to reach the owner, the UX problem isn't "does each agent work" — it's "does the owner end up with one coherent assistant, or three notification sources wearing one label." Entry consolidation and per-entry agent attribution aren't cosmetic; they're the concept's actual answer to the pile-up risk that a naive multi-agent rollout would create.

*(Pulled from brief HOW → core design challenge; this is the most concrete design-judgment statement in the source material. Per CLAUDE.md's working agreement, this slide must survive intact even if others are trimmed.)*

`[VISUAL: Diagnostic Alert Detail screen, from 05-connected-vehicle-assistant-wireframes.md]`

---

## Consistency Check

- [x] All 9 slides present, in order
- [x] Phase language matches CLAUDE.md's 8-stage names exactly
- [x] Key Insight slide present and substantive, not trimmed
- [x] No fabricated metrics presented as real — all figures labeled illustrative/target
- [x] No fabricated quotes presented as verbatim — both pull-quotes explicitly labeled illustrative
- [x] Visual placeholders marked, referencing the wireframes doc
- [x] Content synthesized beyond the brief/discovery (persona sentiment, illustrative quotes, target metrics) is flagged inline, not presented as sourced fact
