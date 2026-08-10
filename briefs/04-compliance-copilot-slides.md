# Slides — Compliance Co-Pilot (Epic 4)
Source: `04-compliance-copilot.md` (brief) + `04-compliance-copilot-discovery.md` (discovery). Concept-stage: metrics and quotes below are illustrative/target figures reasoned from the real OBI baseline and this concept's proposed scope — not measured results. Each is labeled inline; none should be presented as achieved outcomes in any downstream deliverable.

---

## Section Divider / Cover — Compliance Co-Pilot

- **Title**: Compliance Co-Pilot
- **Tagline**: A multi-agent concept for legible compliance review
- **One-line description**: Extends Michael's real Credit Suisse Outside Business Interests (OBI) work into a concept where a research agent, a policy-check agent, and an escalation agent handle parts of submission review — with every action visible on a timestamped trail.
- **Pull-quote** *(illustrative — reasoned from the documented OBI pain points, not a verbatim interview quote)*: "I never know why my submission is stuck, or who's actually looking at it."
- **Treatment**: coral gradient banner (`#F5805C` → `#FF8C7A` → `#FFB088`), thin title typography, lime/rust accent bars

---

## Introduction — What's Compliance Co-Pilot?

- **Description**: A concept where a submission (e.g., an outside business interest disclosure) is handled in part by three specialized agents — one gathering context, one checking policy conflicts, one routing escalations — instead of moving through purely manual step-by-step review.
- **Target audience** (teal circle-callout): Risk & Compliance manager, Submitter/Employee
- **The problems** (bulleted, from discovery Pain Points — real, sourced from the existing OBI case study):
  1. Submissions returned for missing information, with no clear explanation of what was actually needed
  2. No visibility into where a submission is in the review pipeline or why
  3. No consolidated view of a submitter's disclosure history when making a judgment call
- **My Role**: Extends design and discovery work from Michael's real Credit Suisse OBI case study into this forward-looking multi-agent concept.

---

## KPI Stat Block — Discovery & Research

- **"Why does this matter?"**
- **~40% of OBI submissions returned at least once for missing information** *(illustrative baseline estimate, not sourced from the real OBI dataset — used for "why this matters" framing only)*
- **Discovery methods** (real, carried over from the OBI engagement): interviews with Risk & Compliance managers, Submitter/Employee personas
- **Problem statement** (from brief WHAT → Problem): a single submission today gets manually routed and reviewed step by step, with no visibility into why it's at a given stage or what's being checked

---

## Pain Points from Interviews

1. Submissions returned for missing information, with no clear explanation of what was actually needed
2. No visibility into where a submission is in the review pipeline or why
3. No consolidated view of a submitter's disclosure history when making a judgment call

**Pull-quote** *(illustrative — reasoned from pain point #2, not a verbatim quote)*: "It's a black box. I submit, then I wait, and I don't know what's happening in between."

---

## Persona Card — Risk & Compliance Manager

- **Name/Role**: primary persona, Risk & Compliance manager (per brief WHO)
- **Sentiment quote** *(illustrative, reasoned from the documented pain points — not a sourced verbatim)*: "I need to trust the system's recommendation, not just accept it — show me why."
- **Responsibilities**: reviewing submissions for policy conflicts, making judgment calls on ambiguous cases, escalating where needed
- **Key challenges**: opacity of any automated flag ("why was this flagged"), workload from re-verifying findings they can't see the reasoning behind
- **Wishlist**: a visible reasoning trail for every automated action, the ability to override without losing the audit record, a consolidated view of submitter history

*(Fields beyond role and core challenge are reasonably inferred from brief WHO + WHAT, not sourced from dedicated persona interviews for this concept — flagged here per wireframe-describer's underspecified-content convention.)*

---

## Four-Column Framework — Pain Points + Business Goals + UX Strategy = Feature Set

| Pain Points (red `#DF505C`) | Business Goals (blue `#8AD9F8`) | UX Strategy (green `#41854F`) | Feature Set (purple `#7C417E`) |
|---|---|---|---|
| Submissions returned for missing info, no explanation | Faster, more consistent compliance review with a clear audit trail | Extend real OBI discovery findings, not start from zero | Research agent (context-gathering) |
| No visibility into pipeline status or reasoning | Reviewers and submitters understand what's happening at every step | Agent proposes, human confirms every material action | Policy/compliance-check agent |
| No consolidated disclosure history for judgment calls | | Visible, timestamped agent-activity trail on every submission | Escalation agent |
| | | | Agent-activity trail/timeline UI + policy-conflict linking + override & log |

---

## Design/Process — 8-Stage AI-Enhanced UX Process

- **Discovery & Research**: Same as always — real interviews with Risk & Compliance managers and Submitters (carried over from OBI). New in AI-native version: explicitly mapped which parts of the workflow are agent-automatable (context-gathering, conflict detection) vs. requiring human compliance judgment.
- **Problem Definition**: Same as always — synthesized the OBI pain points. New: separated "the workflow is slow" (an agent can help) from "I don't trust an opaque automated flag" (only interaction design solves this).
- **Competitive / Pattern Analysis**: *Not yet conducted for this concept* — flagged as an open next step, not completed research.
- **Design Thinking & Ideation**: New in AI-native version — ideation centered on agent *behavior* before any screen: what each agent surfaces, how conflicting agent outputs are shown, and where the agent-proposes/human-confirms line sits.
- **Design Sprints & Iteration**: *Not yet run.* The agent-activity trail, policy-conflict linking, and override+log pattern below are proposed, not tested/iterated.
- **Usability Testing**: *Not yet conducted.* This is a concept/vision piece — no fabricated test results are presented.
- **Delivered Solution**: Concept only — agents propose, flag, and surface; a human reviewer retains final authority on every material action.
- **Outcomes**: See Results below — targets, not measured results.

**Callout — Unexpected Challenge (red)**: The hardest open question for this concept isn't agent accuracy — it's whether reviewers will trust a workflow where three different agents can each touch one case. That's a legibility problem, not a model-quality problem, which is why the activity trail is the concept's central feature rather than an accessory.

`[VISUAL: Submission Detail — Agent Activity Trail screen, from 04-compliance-copilot-wireframes.md]`

---

## KPI Stat Block — Results (targets, not measured)

- **~30% reduction in review cycle time (target)**
- **~50% fewer submissions returned for missing information (target)**
- **≥80% of pilot reviewers report the activity trail gives them enough information to confirm an agent's routing without re-verifying from scratch (trust target)**

*(All three explicitly labeled as targets — this concept has not been piloted or tested.)*

---

## Key Insight

> When more than one agent can act on a case, the UX problem shifts from "is the AI right" to "can the user tell who did what and why." The agent-activity trail isn't a feature bolted onto the workflow — it's the design's answer to that question, and everything else (policy linking, override+log) exists to make the trail trustworthy rather than just present.

*(Pulled from brief HOW → core design challenge; this is the most concrete design-judgment statement in the source material. Per CLAUDE.md's working agreement, this slide must survive intact even if others are trimmed.)*

`[VISUAL: Policy Conflict Drill-down screen, from 04-compliance-copilot-wireframes.md]`

---

## Consistency Check

- [x] All 9 slides present, in order
- [x] Phase language matches CLAUDE.md's 8-stage names exactly
- [x] Key Insight slide present and substantive, not trimmed
- [x] No fabricated metrics presented as real — all figures labeled illustrative/target
- [x] No fabricated quotes presented as verbatim — both pull-quotes explicitly labeled illustrative
- [x] Visual placeholders marked, referencing the wireframes doc
- [x] Content synthesized beyond the brief/discovery (persona sentiment, illustrative quotes, target metrics) is flagged inline, not presented as sourced fact
