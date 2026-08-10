# Compliance Co-Pilot — Brand Identity Log

Status tracker for the brand identity build in Figma file **"Compliance Co-Pilot — Brand Identity"** (key `S3QAQmsdoS8cFGGxkxSYkZ`). Written incrementally so a fresh session can resume without re-deriving decisions. This is a **concept/speculative** identity — see `../briefs/04-compliance-copilot-discovery.md` for the underlying case study. Not a real Credit Suisse trademark asset; designed to plausibly sit inside a bank's internal tools ecosystem, not reproduce Credit Suisse's actual visual identity.

---

## Design brief (self-reference)

Central UX challenge driving the identity: **agent-accountability legibility** — showing which of three agents (research, policy-check, escalation) acted and why, with a human reviewer confirming every material action. Identity should read as precise, auditable, "shows its work." Avoid: cartoon mascots, chat-bubble cuteness, black-box AI-startup visual tropes.

Chosen visual motif: **the trail** — a sequence of linked checkpoints/nodes connected by a line, echoing the product's actual core feature (the timestamped activity trail / chain of custody across agent handoffs).

---

## Naming

"Compliance Co-Pilot" — kept as given, positioned as a plausible internal sub-product name (the kind of name a bank's internal tools group would ship — descriptive, not cute), not a public consumer brand.

---

## Color system

Figma variable collection: **"Compliance Co-Pilot Palette"** (single mode: "Default" — this is a light-UI enterprise tool, no dark mode variant scoped for this pass).

### Primary / neutrals

| Token | Hex | Role |
|---|---|---|
| `primary/ink-navy` | `#1B2C4D` | Primary brand color — wordmark, primary buttons/chrome, icon fill |
| `neutral/ink` | `#0E1A2B` | Body text, near-black navy (never pure black) |
| `neutral/slate` | `#5B6B82` | Secondary/muted text, timestamps, metadata labels |
| `neutral/border` | `#D8DEE7` | Hairlines, dividers, card borders |
| `neutral/paper` | `#F7F8FA` | Page/app background, cool near-white |

Rationale: deep slate-navy rather than a brighter "trust blue" — reads as restrained/institutional rather than startup-SaaS. Deliberately avoids replicating Credit Suisse's actual brand blue; this is a distinct, plausible-but-different navy for a fictional internal tool.

### Functional / agent-state colors

| Token | Hex | Role |
|---|---|---|
| `state/agent-proposed` | `#3D6FB4` | An agent has proposed/suggested an action, not yet confirmed by a human. Cooler, lighter blue than the primary ink-navy — reads as "in progress," clearly in the same family as the brand so it doesn't feel like an alarm. |
| `state/agent-proposed-surface` | `#E8F0FA` | Light tint for "proposed" badge/chip backgrounds |
| `state/human-confirmed` | `#2E6B4F` | A human reviewer has confirmed/finalized an action. Muted forest green — deliberately desaturated, not a bright "success" green, to stay consistent with a compliance tool's serious register. |
| `state/human-confirmed-surface` | `#E7F1EC` | Light tint for "confirmed" badge/chip backgrounds |
| `state/policy-conflict` | `#B8791E` | A policy-check agent flagged a potential conflict. Amber/ochre, not red — attention-worthy without reading as alarmist/emergency. Consistent with brief's instruction that compliance flags should feel "serious, not scary." |
| `state/policy-conflict-surface` | `#FBF0E0` | Light tint for "conflict flagged" badge/chip backgrounds |

Deliberately did **not** use red anywhere in the functional palette — red is reserved (unused) in case a true system-error/destructive state is needed later; policy conflicts are a normal, expected part of the workflow, not an error state.

---

## Typography

**IBM Plex Sans** — UI text, wordmark, headings, body. Chosen over Inter for a slightly more technical/engineered character appropriate to compliance software (IBM Plex's origin as an enterprise/technical typeface fits the "audit tool," not "consumer AI assistant," register).

**IBM Plex Mono** — reserved for anything that reads as a system record: timestamps, agent IDs, policy/rule citation codes in the activity trail. Using a monospace for the audit-trail metadata (not body copy) visually reinforces "this is a log, not a conversation" — directly supporting the agent-accountability-legibility goal.

Both families confirmed available in the Figma file via `listAvailableFontsAsync` (styles: Thin/ExtraLight/Light/Regular/Medium/SemiBold/Bold, each with italics).

### Type ramp (planned — see status below for build progress)

| Style | Family | Size/Line-height | Weight | Use |
|---|---|---|---|---|
| Display | IBM Plex Sans | 32/40 | Medium | Wordmark lockup, cover/hero |
| H1 | IBM Plex Sans | 24/32 | SemiBold | Page/section titles |
| H2 | IBM Plex Sans | 18/26 | SemiBold | Card/panel titles |
| Body | IBM Plex Sans | 14/22 | Regular | Default UI text |
| Body Medium | IBM Plex Sans | 14/22 | Medium | Emphasis within body |
| Label/Eyebrow | IBM Plex Sans | 12/16 | Medium, tracked +2% | Section labels, badges |
| Mono/Meta | IBM Plex Mono | 12/18 | Regular | Timestamps, agent IDs, policy citation codes |

---

## Logo / mark

**Standalone mark**: three small circular nodes connected by a horizontal line — representing the three agents (research → policy-check → escalation) — with the final node rendered as a ring/checkmark state to represent the human-confirmation checkpoint that closes every trail. This is a direct, literal translation of the product's real activity-trail feature into a mark, not an abstract/decorative symbol.

**Wordmark**: "Compliance" + "Co-Pilot" in IBM Plex Sans Medium, set in `primary/ink-navy`, normal case (not all-caps — reads as calmer/more institutional than a shouty startup wordmark). No mascot, no chat bubble, no gradient.

**Lockup**: mark + wordmark horizontal lockup for headers; mark alone at app-icon scale (rounded-square container, `primary/ink-navy` fill, mark in white/paper).

**Clear space**: minimum clear space = height of one node-circle in the mark, on all sides. Minimum size: mark alone not smaller than 24px (digital) / wordmark lockup not smaller than 120px wide.

---

## Voice & tone principles

1. **State what happened, not what it might mean.** Trail entries describe the agent's action in plain, factual language ("Research agent reviewed 3 prior disclosures") — never speculative framing ("this looks fine," "probably not a conflict"). Judgment stays with the human reviewer.
2. **Every claim links to its source.** A policy-conflict flag always names and links the specific rule it's based on — never a bare "flagged for review" with no citation. Directly extends the case study's "policy-conflict linking" requirement.
3. **Confirmed and proposed are never visually or verbally ambiguous.** Language always distinguishes an agent's proposal ("Policy agent flagged...") from a human's confirmed action ("Approved by [Reviewer]") — no passive voice that blurs who actually decided.

---

## Build status in Figma

- [x] Variable collection "Compliance Co-Pilot Palette" created with tokens above — collection id `VariableCollectionId:2:2`, mode id `2:0`
- [x] Standalone mark (vector) built — node id `2:14` ("Mark / Standalone", 96x96, at x=400,y=0). Three nodes on a horizontal trail line: node 1 (research agent, solid circle, x=22), node 2 (policy-check agent, solid circle, x=48), node 3 (escalation → human-confirmed, ring + center dot, x=74). All bound to `primary/ink-navy`.
- [x] Wordmark text built — node id `2:22` ("Compliance Co-Pilot", at x=400,y=140). "Compliance" in IBM Plex Sans Medium, " Co-Pilot" in IBM Plex Sans Light — weight-contrast lockup pattern (echoes, without copying, Michael's real wordmark's weight-contrast approach). Bound to `primary/ink-navy`. Character range indices: Medium=[0,10), Light=[10,19) — note "Compliance Co-Pilot" is 19 chars, not 20 (no trailing space after "Co-Pilot").
- [x] Lockup composed (mark + wordmark) — node id `2:23` ("Lockup / Horizontal", horizontal auto-layout, itemSpacing 14, at x=400,y=260). Mark scaled to 40x40 via `node.rescale(40/96)` (NOT `resize()` — resize() on a frame with absolute-positioned children clips them instead of scaling; rescale() scales children proportionally). Wordmark clone at fontSize 22.
- [x] Clear-space / minimum-size guidance frame — node id `4:24` ("Clear Space & Minimum Size", 328x365, at x=650,y=40). Dashed clear-space diagram around the mark plus the min-size copy block (24px mark alone / 120px lockup minimum).
- [x] Type ramp frame — node id `4:2` ("Type Ramp", 512x320, at x=1050,y=40). All 7 styles (Display, H1, H2, Body, Body Medium, Label/Eyebrow, Mono/Meta) shown as label + live example pairs, using real activity-trail copy as the sample text.
- [x] Voice & tone text block — node id `4:38` ("Voice & Tone", 420x365, at x=40,y=520). All 3 principles present with headline + supporting copy, matching the log's principles verbatim.
- [x] Application: activity-trail header mockup — node id `4:49` ("Application / Activity Trail Header", 520x422, at x=520,y=520). Full OBI-submission header with 4 trail entries (research agent, policy agent, escalation agent, human reviewer), each with timestamp (Mono), actor name, status badge, and description. Badges confirmed bound to the three functional-state variables (`state/agent-proposed`, `state/policy-conflict`, `state/human-confirmed` + their surface tints) via `get_variable_defs` — not hardcoded hex.
- [x] Application: app-icon-scale treatment — node id `2:31` ("App Icon / 1x (mark on navy)", 64x64, cornerRadius 14, at x=550,y=0). Navy fill (`primary/ink-navy`), mark redrawn in `neutral/paper` (white) at icon scale — not a rescaled clone, drawn fresh at icon proportions for crisper rendering at small size.
- [x] Final full-page screenshot review — completed 2026-08-09 (resumed session; the 2026-08-01 session had built all of the above but was cut off before this last checklist item and before updating this log — file state was verified ahead of the log). Reviewed via full-canvas screenshot (node `0:1`, not the background rect `5:4` — that node has no children so it renders blank) plus individual high-res screenshots of every foundation/application node. Layout: two clean rows (FOUNDATIONS / APPLICATIONS section labels), no overlaps, no clipped text, no orphaned placeholder content. Visual QA passed with no fixes needed.

**Gotcha for future sessions:** when scaling a clone of a non-auto-layout frame with absolute-positioned children, use `node.rescale(factor)`, not `node.resize(w, h)` — resize only changes the frame's own bounding box and children get clipped by `clipsContent`, not scaled. Also: to screenshot the whole board, screenshot the page/canvas node (`0:1`), not a background rectangle — the background rect is a sibling of the content frames, not a parent, so screenshotting it alone renders blank.

_(This checklist is updated as work completes — check the actual Figma file state if this log and the file ever disagree; the file is the source of truth for what's built.)_

---

## Session notes

- 2026-08-01: Brief read, whoami confirmed "Michael Thibodeau's team", Figma file confirmed empty (single blank page, "Page 1"). IBM Plex Sans + IBM Plex Mono confirmed available. Color/type/voice decisions above finalized before any Figma writes. Proceeding to build variable collection next. (This session went on to build all remaining foundation and application elements — confirmed present in the file on 2026-08-09 — but was cut off before writing those results back to this log.)
- 2026-08-09: Resumed session. Log was stale (showed 5 items unchecked that were actually already built). Verified full Figma file state via `get_metadata` + `get_variable_defs` + targeted screenshots of all 7 major nodes plus a full-canvas screenshot. All deliverables from the brief confirmed present and correct: wordmark, standalone mark, lockup, app icon, clear-space/min-size guide, full type ramp, "Compliance Co-Pilot Palette" variable collection (primary/neutrals + 3 functional states with surface tints), voice & tone (3 principles), and both requested application contexts (activity-trail header + app-icon scale). No fixes required. This log updated to match reality; status closed out.
