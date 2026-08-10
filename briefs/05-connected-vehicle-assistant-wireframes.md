# Wireframes — Connected Vehicle Assistant (Epic 5)
Source: `05-connected-vehicle-assistant.md` (WHAT/HOW) + `05-connected-vehicle-assistant-discovery.md` (Discovery & Research pain point, Design & Iteration decisions). This is the spec that would feed Figma mockups; no mockups exist yet for this concept.

**Surface: mobile app only**, per the explicit decision in the discovery doc's Design & Iteration section (the brief left in-vehicle vs. mobile vs. both open and recommended picking one; this concept commits to mobile-only, with an in-vehicle glanceable summary flagged as a plausible v2 extension, not designed here).

**Screens covered:** Unified Assistant Feed → Diagnostic Alert Detail → Service Recommendation Detail → Scheduling Suggestion — Action Screen

---

## Screen: Unified Assistant Feed

- **Purpose**: Give the owner one place to see everything the assistant has surfaced, resolving the discovery doc's real, documented pain point — fragmented, one-off notifications with no unified assistant tying scheduling, diagnostics, and service recommendations together.
- **Key elements**:
  - Chronological feed, one entry per item, each carrying a visible **agent label** (diagnostics, scheduling, or service-recommendation) per the brief's acceptance criteria ("each entry labeled by which agent generated it")
  - **Entry consolidation** — when a diagnostic alert and its related service recommendation concern the same underlying issue, they appear as one merged entry with sub-attribution (e.g., "Diagnostics flagged this — Service recommendation attached"), not two separate entries, per the discovery doc's Design & Iteration decision
  - Quick-glance status strip at the top (e.g., "Your vehicle is up to date" / "1 item needs your attention") so the owner doesn't have to read the whole feed to know if anything's urgent
  - Per-entry one-tap action where applicable (e.g., "Confirm appointment" directly on a scheduling entry)
- **Primary user action**: Owner scans the feed, taps an entry to see more → goes to the relevant detail screen (Diagnostic Alert Detail, Service Recommendation Detail, or the Scheduling Suggestion action inline)
- **AI-generated content vs. static UI**: AI-generated — every feed entry's content, the agent label, and the consolidation logic that merges related entries. Static — the feed shell, the status strip layout, navigation chrome
- **State variations**:
  - Empty/nominal state ("Your vehicle is up to date" — no open items)
  - Normal feed state (mixed entries from multiple agents)
  - Attention-needed state (a diagnostic entry visually distinct — e.g., a safety-relevant alert — surfaced at the top of the feed regardless of recency)

---

## Screen: Diagnostic Alert Detail

- **Purpose**: Translate a diagnostics-agent alert into something the owner can actually act on, resolving the "what does this alert mean" pain point named in discovery's Outcomes framing and directly answering the trust-baseline concern raised in Discovery & Research (an owner reads a warning light as "is my car safe," not as an abstract code).
- **Key elements**:
  - Plain-language explanation of the alert, always paired with the underlying code/label — never the code alone, per the discovery doc's Design & Iteration pattern ("plain-language diagnostic translation")
  - Urgency indicator (**decision**: three plain-language levels — "Can wait for your next visit," "Schedule soon," "Get this checked now" — rather than exposing Honda's internal severity taxonomy directly to the owner, since the owner-facing goal is "what should I do," not "how is this classified internally")
  - Linked service recommendation, if the service-recommendation agent has attached one to this issue (surfaces the merged-entry relationship established on the Feed screen)
  - "Schedule service" action, leading into the Scheduling Suggestion screen
- **Primary user action**: Owner reads the explanation and urgency level, then either schedules service or dismisses (for a "can wait" item) back to the feed
- **AI-generated content vs. static UI**: AI-generated — the plain-language explanation, the urgency-level assignment, and the link to a related service recommendation. Static — the underlying diagnostic code/data itself (real vehicle telematics data, not agent-generated)
- **State variations**:
  - Informational-only state (no action needed, e.g., a routine reminder translated into plain language)
  - Attention-needed state (urgency indicator shown, scheduling action emphasized)
  - Safety-critical state (**decision**: this state overrides the normal ambient/pull balance — a safety-critical alert is pushed to the owner immediately rather than waiting to be discovered in the feed, and its detail screen leads with a direct next step, e.g., "Contact your dealer" or "Schedule service now," ahead of the explanation copy)

---

## Screen: Service Recommendation Detail

- **Purpose**: Show the reasoning behind a service-recommendation-agent suggestion on its own, for the case where a recommendation isn't tied to an active diagnostic alert (e.g., a mileage-based recommendation) — resolving the brief's business goal of strengthening the owner-to-dealer relationship by making a recommendation legible rather than a bare upsell.
- **Key elements**:
  - The recommendation itself in plain language (e.g., "Your service history and mileage suggest it's time for a brake inspection")
  - **Basis for the recommendation** (**decision**: shown as a short "why you're seeing this" line — e.g., "Based on your mileage and service history" — rather than exposing a raw model score or internal recommendation-engine detail, consistent with the plain-language-first pattern used on the Diagnostic Alert Detail screen)
  - "Schedule service" action, leading into the Scheduling Suggestion screen
  - Dismiss/not-now action, which does not delete the recommendation but returns it to the feed in a de-emphasized state (avoids the notification-pile-up risk named in The Problem — a dismissed recommendation shouldn't keep re-surfacing at full prominence)
- **Primary user action**: Owner reads the recommendation and its basis, then schedules or dismisses
- **AI-generated content vs. static UI**: AI-generated — the recommendation text and its stated basis. Static — the underlying service-history and mileage records it's drawn from
- **State variations**:
  - Standalone recommendation (not linked to a diagnostic alert)
  - Linked recommendation (arrived here via the Diagnostic Alert Detail screen's link)
  - Dismissed/de-emphasized state (owner has said "not now")

---

## Screen: Scheduling Suggestion — Action Screen

- **Purpose**: Let the owner act on a scheduling agent's suggestion in one step, resolving the brief's acceptance criterion that "scheduling suggestions are actionable in one step (not a handoff to a separate app/flow)."
- **Key elements**:
  - Proposed appointment slot(s) from the scheduling agent (**decision**: two to three proposed time options shown by default, sourced from dealer availability, rather than an open calendar picker — this keeps the "propose, owner confirms" pattern from the discovery doc's Ideation section fast and low-friction; an "see more times" path is available but not the default view)
  - What the appointment is for (pulled from the linked diagnostic alert or service recommendation, so the owner isn't scheduling blind)
  - Single confirm action — per the discovery doc's Ideation decision, the scheduling agent may propose a slot but never auto-books; the owner's tap is the action that finalizes it
  - Dealer/location selector, if the owner has more than one associated service location
- **Primary user action**: Owner picks a proposed slot (or requests more options) and confirms in one tap; confirmation is the action that hands off to the dealer per the brief's WHO → secondary persona
- **AI-generated content vs. static UI**: AI-generated — the proposed slots and the linkage back to why this appointment is being suggested. Static — actual dealer calendar availability (real scheduling data, not agent-generated) and the confirm/booking mechanism itself
- **State variations**:
  - Slots-available state (normal path)
  - No-slots-available state (**decision**: rather than a dead end, this state shows the next available date across nearby dealer locations, plus a "call your dealer" fallback — an agent that proposes but can't find a near-term slot still needs to leave the owner with a next step, consistent with the "agent hands off with a specific next step" pattern established in Epic 1)
  - Confirmed state (appointment booked; feed entry updates to reflect confirmed status rather than remaining an open action item)

---

## Consistency Check

- [x] Every screen ties back to a specific pain point or discovery-doc decision (fragmented notifications on the Feed; "what does this alert mean" on Diagnostic Alert Detail; owner-dealer relationship on Service Recommendation Detail; one-step scheduling on the Action Screen)
- [x] Component terminology matches the brief's HOW → Key interaction patterns and the discovery doc's Design & Iteration section exactly ("unified assistant feed/thread," agent labeling, one-tap/one-step scheduling — no invented component names)
- [x] AI-generated vs. static content is explicitly distinguished on each screen
- [x] Underspecified areas were flagged, then resolved with explicit design decisions (urgency-level taxonomy, safety-critical push override, recommendation basis disclosure, default slot count, no-slots-available fallback) rather than left open or silently guessed
- [x] Screen order follows a logical flow: entry point (Feed) → the two content-detail screens an entry can lead to (Diagnostic Alert Detail, Service Recommendation Detail) → the shared action screen both can lead into (Scheduling Suggestion)
