# Wireframes — AI Pattern Library (Epic 3)
Source: `03-ai-pattern-library.md` (WHAT/HOW) + `03-ai-pattern-library-discovery.md` (Discovery & Research pain points, Design & Iteration component set). Synthesis case study — component set and adoption narrative are constructed, per the discovery doc's Status line.

**Format note (per brief's "Out of scope" flag):** this concept is presentation-format-flexible. Unlike a typical end-user app flow, the "screens" here are component/pattern specimens — documentation artifacts a product designer consults, not screens an end user moves through in sequence. That reframes two things every other screen-description in this project takes for granted, flagged and resolved below rather than left implicit:

- `[UNDERSPECIFIED: brief's WHAT/HOW describe components, not a user flow — who is the "user" of these screens, and what does "primary user action" mean for a specimen sheet?]` **(decision):** the user of every screen below is a product designer or engineer on an adopting team, consulting the pattern library while building their own AI feature — not an end user of any single AI product. "Primary user action" is read accordingly: what does *this* person do with *this* screen.
- `[UNDERSPECIFIED: brief doesn't specify how the case study demonstrates adoption across teams, beyond acceptance criteria requiring "2-3 product teams shown adopting the same component"]` **(decision):** screen 5 below is a governance/adoption dashboard, not a component specimen — it's the artifact that makes the adoption story (and the case study's core design challenge, per brief HOW) visible and demoable, not just claimed in prose.

**Screens covered:** Confidence / Certainty Indicator — Specimen Sheet → Citation / Source Card — Anatomy & States → Streaming-Response State — Sequence View → Correction Control → Human-Handoff Banner — Interaction Flow → Governance & Adoption Dashboard

---

## Screen: Confidence / Certainty Indicator — Specimen Sheet

- **Purpose**: Give any adopting team a single, documented visual language for signaling how sure the system is — resolves discovery pain point #1, "every team invents its own confidence visualization, with no shared visual or verbal language for 'sure' vs. 'not sure.'"
- **Key elements**:
  - The indicator itself, shown at all defined states side by side (see State variations)
  - Usage note: defined use case, plus the explicit "when NOT to use this" note (per brief acceptance criteria)
  - Accessibility annotation: contrast values, confirmation the signal isn't color-only, screen-reader label text for each state
  - Do/don't example pair (e.g., "don't" shows the deprecated red/yellow/green treatment flagged in the discovery doc's iteration finding, "do" shows the shipped intensity-scale-plus-qualifier treatment)
- **Primary user action**: A designer scans the specimen sheet to pick the correct state and copy pattern for their feature's actual confidence output, then references the accessibility annotation before implementation
- **AI-generated content vs. static UI**: This screen is entirely static documentation — nothing on the specimen sheet itself is AI-generated. (The indicator's *underlying value*, when embedded in a real product, is AI-generated; that distinction is called out explicitly on the sheet so adopting teams don't confuse "the pattern is static" with "the data behind it is static.")
- **State variations**:
  - High confidence
  - Partial / verify-before-use (medium confidence)
  - Low confidence
  - Unknown / not yet scored (e.g., system hasn't returned a confidence value yet — distinct from low confidence, so a team can't accidentally render "unknown" as "low")

---

## Screen: Citation / Source Card — Anatomy & States

- **Purpose**: Give adopting teams a shared anatomy for showing where an AI answer's source material came from, shown by default rather than behind a click — resolves discovery pain point #2, "citation/sourcing is shown inconsistently... undermining trust across the product family."
- **Key elements**:
  - Labeled anatomy diagram: source label, snippet/excerpt region, expand-to-full-record affordance, source-type icon (e.g., internal document vs. external link)
  - Usage note + "when NOT to use this" (e.g., not intended for answers with no retrievable source — that case routes to the Human-Handoff Banner or a future empty-state pattern instead of a fabricated citation)
  - Accessibility annotation: focus order for the expand affordance, label text
  - Cross-reference note: this anatomy is the same "show your work by default" principle documented in Epic 1's citation design, here generalized into a reusable component rather than a one-product pattern
- **Primary user action**: A designer maps their feature's actual source data onto the anatomy's labeled regions, and confirms their case doesn't fall under the "when NOT to use this" note before shipping
- **AI-generated content vs. static UI**: AI-generated — the source selection and excerpt shown inside the card, in a real implementation. Static — the card's anatomy, labels, and expand affordance
- **State variations**:
  - Single source
  - Multiple sources (stacked/collapsed)
  - Expanded (drilled into the full underlying record)
  - No source available (explicitly routes elsewhere per the "when NOT to use this" note, rather than rendering an empty card)

---

## Screen: Streaming-Response State — Sequence View

- **Purpose**: Give adopting teams a shared affordance for "still generating" vs. "done," so users can tell whether the system is working or stalled — resolves discovery pain point #3, "streaming/in-progress states range from a generic spinner to token-by-token text with no shared affordance... users can't tell if the system finished or stalled."
- **Key elements**:
  - A sequence, not a single static frame: shown as a strip of states in order (start → in-progress → complete), since this component is inherently time-based
  - Visual "still working" affordance distinct from a generic spinner (e.g., a persistent, low-motion indicator that stays visible alongside partial text, not a full-screen blocking spinner)
  - Usage note + "when NOT to use this" (e.g., not a substitute for the Confidence Indicator — a response can finish streaming and still be low-confidence; the two are shown together, not conflated)
  - Accessibility annotation: how the "still generating" state is announced to screen readers without producing excessive interruption
- **Primary user action**: A designer checks their feature's actual response latency/behavior against the defined states, and confirms the in-progress affordance is present before their feature ships
- **AI-generated content vs. static UI**: AI-generated — the streaming text itself. Static — the progress affordance and state chrome around it
- **State variations**:
  - Start (request sent, generation not yet visible)
  - In-progress (partial text visible, "still working" affordance active)
  - Complete (affordance clears, full response stable)
  - `[UNDERSPECIFIED: brief's HOW doesn't define a streaming error/interruption state]` **(decision):** added a fourth state — Interrupted/failed mid-stream — showing the partial text retained (not discarded) plus a plain-text note that generation stopped early, so a user isn't left staring at a response that silently cut off with no explanation

---

## Screen: Correction Control → Human-Handoff Banner — Interaction Flow

- **Purpose**: Show the Correction/Feedback Control and Human-Handoff Banner together as one interaction flow, not two disconnected components — resolves discovery pain points #4 ("no consistent way for a user to tell the system it got something wrong, and where feedback controls exist, nothing visibly happens with that input") and #5 ("no consistent way to hand off to a human... inconsistent from a dead-end error message to no handoff path at all").
  - `[UNDERSPECIFIED: brief lists these as two separate components — is one screen combining them a deviation from the brief?]` **(decision):** kept as two distinct, independently documented components (each gets its own usage note, "when NOT to use this," and accessibility pass), but shown on one screen as a flow, because the discovery doc's usability-testing finding was specifically that a feedback control with no visible consequence tested worse than no control at all — showing them combined makes that consequence (correction can lead to handoff) visible in the specimen itself, not just asserted in documentation text.
- **Key elements**:
  - Correction/Feedback Control: the flag/correct affordance itself (e.g., "this isn't right" action plus optional free-text detail)
  - Visible acknowledgment state: what the user sees immediately after giving feedback (per the discovery doc's testing finding — feedback must show *some* consequence, even if the underlying model doesn't retrain in real time)
  - Human-Handoff Banner: plain-language statement that the system is stopping and routing to a human, plus the specific next step (not a dead end)
  - Usage note + "when NOT to use this" for each component independently
- **Primary user action**: A designer decides, for their feature, which correction inputs should route to a visible acknowledgment only vs. which should trigger the Human-Handoff Banner, and implements the acknowledgment state so feedback never disappears silently
- **AI-generated content vs. static UI**: AI-generated — none of the control chrome itself; a real implementation may use the correction signal to inform a downstream model or routing decision, but that's product-specific logic layered underneath the static pattern. Static — the control, the acknowledgment state, and the banner's structure. The banner's *specific destination/next step* is product-specific and filled in by the adopting team, not prescribed by the pattern
- **State variations**:
  - Feedback given → visible acknowledgment (no handoff needed)
  - Feedback given → routes to Human-Handoff Banner
  - Handoff triggered independent of user feedback (e.g., the system itself determines it can't complete the task, per the Confidence Indicator's low-confidence/unknown state)

---

## Screen: Governance & Adoption Dashboard

- **Purpose**: Make the case study's actual core design challenge — governance and adoption, not just component design, per brief HOW — visible as an artifact, and satisfy the acceptance criterion that 2-3 product teams are shown adopting the same component with a before/after comparison.
- **Key elements**:
  - Per-team adoption status for each of the 5 components (e.g., a simple grid: team × component × adopted/in-progress/not started)
  - Before/after comparison panel for the Confidence Indicator specifically, showing the three pilot teams' pre-library treatments next to their shared post-adoption treatment (per the discovery doc's illustrative before/after example)
  - Aggregate metrics panel: adoption count, reduction in one-off patterns flagged in design review, aggregate confidence-indicator override/disagreement rate — all labeled illustrative targets, not live data, consistent with the discovery doc's Outcomes section
  - Link out to each component's specimen sheet and documentation
- **Primary user action**: A design-system governance stakeholder (the secondary persona, per brief WHO) reviews adoption status across teams and identifies where to focus outreach next; a product designer uses it to see a real (in narrative terms) precedent for how another team implemented the same component
- **AI-generated content vs. static UI**: Static — this dashboard is itself an internal governance tool, not an AI feature; nothing on it is AI-generated. (Note: this is a deliberate contrast with every other screen in this set, which is the point — the dashboard is where the design-system discipline is visible, not the AI behavior itself.)
- **State variations**:
  - Full adoption (all tracked teams shown adopted, for a mature component)
  - Partial adoption / in-progress (mixed grid, the state most representative of a v1 rollout)
  - `[UNDERSPECIFIED: brief doesn't specify what "not adopted" looks like on a governance view — does it read as a failure state?]` **(decision):** "not started" is shown neutrally (gray, not red/warning-coded), consistent with the Confidence Indicator's own lesson about avoiding accidental error-coding — a team not yet on the library isn't a failure state, it's a rollout-in-progress state, and coding it as an error would undercut the same adoption goal this dashboard exists to support

---

## Consistency Check

- [x] Every screen ties back to a specific pain point from the discovery file (pain points #1-#5 all covered)
- [x] Component terminology matches the brief's HOW → Key interaction patterns and the discovery doc's Design & Iteration section exactly (Confidence/Certainty Indicator, Citation/Source Card, Streaming-Response State, Correction/Feedback Control, Human-Handoff Banner — no invented names; Empty/No-Answer State correctly excluded as deferred backlog, not fabricated as shipped)
- [x] AI-generated vs. static content is explicitly distinguished on each screen
- [x] Underspecified areas were flagged, then resolved with explicit design decisions (who the "user" is for a specimen sheet; combining Correction Control + Handoff Banner into one flow while keeping them independently documented; the streaming-interruption state; the dashboard's "not adopted" treatment) rather than left open or silently guessed
- [x] Screen order follows a logical flow: three single-instance component specimens in the order the discovery doc's pain points name them (confidence → citation → streaming), then the paired correction/handoff flow, then the governance dashboard that ties adoption across all five together
