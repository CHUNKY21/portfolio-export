# Meridian Identity System — Decision Log

Working log for the Meridian brand identity build in Figma file `wR1jR86W4zV1umY9tK6D8Z`
("Meridian — Brand Identity System"). Written incrementally so a fresh session can resume
without re-deriving anything. If this log and the live Figma file ever disagree, the Figma
file is the source of truth for what actually got built — treat this log as the rationale
layer, not the pixel-accurate record.

## Ownership / scope

- This agent owns: Page 1 "Meridian — Parent Brand" and Page 2 "Research Agent — Sub-Identity".
- A sibling agent owns Page 3 "Exception Manager — Sub-Identity" separately — do not edit that page.
- Figma pages confirmed created: Page 1 id `0:1` (renamed from default "Page 1"),
  Page 2 id `1:2` ("Research Agent — Sub-Identity").

## Brand concept

"Meridian" = a line of longitude, a fixed reference point used to establish location with
precision. That's the whole brand idea: in a regulated, skeptical-by-default financial-ops
environment, the product's value is being a fixed, trustworthy reference point analysts can
verify against — not a flashy assistant.

**Icon mark concept:** a circle (the globe / the instrument lens) bisected by a full-height
vertical line (the meridian line itself, running pole to pole) with a single small solid dot
at the exact center where the line crosses the circle's mid-point. The dot is the "fixed
point" — literally the navigational fix a meridian establishes. It doubles as a quiet nod to
the confidence-signal language used throughout both case studies (a single precise point of
certainty, not noise). This reads as a minimal survey/geodesic mark — closer to a cartography
instrument or a precision reticle than a consumer logo — deliberately in the Bloomberg
Terminal / Palantir Foundry register, not a consumer AI chat-bubble mark.

Built as real vector shapes: an ellipse (stroke only, no fill) + a line (vertical, full
diameter) + a small filled ellipse (the center dot). Confirmed it holds up at favicon/app-icon
scale — the three elements stay legible down to ~16px because there are only three strokes/
shapes total, no fine detail.

**Wordmark:** "Meridian" set in IBM Plex Sans, Medium weight, all standard case (not a custom
logotype) — deliberately typographic/plain rather than a stylized script, to keep the register
enterprise/instrument-grade rather than consumer-startup. Primary lockup = icon mark + wordmark
side by side, icon to the left.

## Color system

Figma variable collection: **"Meridian Palette"** (single mode, `Value`) — created on Page 1,
file-scoped so it's available to both pages (and importable by the Exception Manager sibling
page if useful). Explicitly distinct from the portfolio deck's coral/terracotta/lime palette
(`#D54E2B`, `#F5805C`, `#BFFD20`, etc. — see project `CLAUDE.md`) — Meridian is the fictional
product's own brand, not Michael's portfolio brand.

Rationale: deep navy as primary (financial, calm authority, not black — black reads as
severe/cold for a long-session daily-use tool). One sharp cobalt accent used sparingly for
interactive/active state, not decoration. Semantic trio (confidence-high / confidence-low /
alert) deliberately desaturated relative to typical UI red/green/amber — this is a regulated
financial context, not a game HUD; the colors should read as informative, not alarming.

| Token | Hex | Role |
|---|---|---|
| `primary/navy` | `#0E2A47` | Primary brand color — logo, headers, primary UI chrome |
| `secondary/slate` | `#4A5C6E` | Secondary text, dividers, muted UI elements |
| `accent/signal-blue` | `#2E6FF2` | Single sharp accent — interactive/active states only |
| `semantic/confidence-high` | `#1E8A6E` | High-confidence answer/ranking signal (deep, not neon green) |
| `semantic/confidence-low` | `#C67C1E` | Partial/low-confidence signal (muted amber, not warning-yellow) |
| `semantic/alert` | `#B23B34` | Critical/escalation signal (brick red, not fire-engine) |
| `neutral/bg` | `#F5F6F8` | App/page background |
| `neutral/surface` | `#FFFFFF` | Card/panel surface |
| `neutral/ink` | `#0F1620` | Primary text |
| `neutral/border` | `#DADFE4` | Hairlines, dividers, input borders |

Note for whoever builds Exception Manager's sub-identity: consider leaning that sub-brand
toward the `confidence-low` / `alert` end of this same palette (it's the ambient/alerting
product) to differentiate from Research Agent's blue without introducing new brand colors —
not a requirement, just a suggestion so the two sub-identities read as siblings, not clones.

## Typography

**IBM Plex Sans** — primary typeface for the whole system (headings, body, UI). Chosen over
Inter/Poppins because it reads as more "instrument-grade" (IBM's own heritage as an enterprise/
technical brand) while remaining a clean, modern, highly legible grotesque — appropriate for
long-session daily use by detail-oriented analysts. Explicitly NOT Poppins (that's the
portfolio deck's font, reserved for Michael's own portfolio brand, not Meridian).

**IBM Plex Mono** — secondary/supporting typeface, used sparingly for data-like or
"show-your-work" microcopy (citation source labels, timestamps, record IDs) — reinforces the
precision/verifiability theme from the Research Agent case study without requiring a third
family.

Confirmed both families are available in this Figma file's font list, including weights:
Thin, ExtraLight, Light, Regular, Medium, SemiBold, Bold (note: style string is `SemiBold`,
no space — differs from Inter's `Semi Bold`).

Type ramp (Page 1):
| Style | Font / weight | Size | Line height |
|---|---|---|---|
| H1 | IBM Plex Sans SemiBold | 32px | 40px |
| H2 | IBM Plex Sans Medium | 24px | 32px |
| Body | IBM Plex Sans Regular | 16px | 24px |
| Caption | IBM Plex Sans Regular | 12px | 16px |
| Data/Mono (support) | IBM Plex Mono Regular | 12px | 16px |

## Voice & tone principles

Grounded directly in the two case study docs (citations-by-default, confidence signal shown
on every answer not just low-confidence ones, named handoff boundary, non-dead-end fallback
language).

1. **Precise, not chatty** — state the finding, not enthusiasm about finding it.
   - Do: "Confirmed: settlement mismatch, $12,400, Account 4471."
   - Don't: "Great news — I found something interesting about your account!"
2. **Shows its work by default** — the citation/source is part of the answer, never a
   click-to-reveal.
   - Do: "Balance verified via Custody Ledger (updated 9:41 AM). [View source]"
   - Don't: "This is correct — trust me." / burying the source behind "Show sources."
3. **Calm under uncertainty, never a dead end** — a partial answer names what it does and
   doesn't know, and gives a next step.
   - Do: "Confirmed trade date and counterparty. Could not confirm settlement status —
     recommend checking with Ops."
   - Don't: a flat "I don't know" with no next step.
4. **States its own boundary** — never implies a finality it hasn't earned; ownership vs.
   human-gated is always explicit.
   - Do: "Proposed match — a human confirms before this is marked resolved."
   - Don't: silently auto-resolving, or phrasing a proposal as if it were already final.

## Build status

Page 1 ("Meridian — Parent Brand", node `0:1`) is complete — six Section nodes laid out
left-to-right / top-to-bottom on the canvas:

- [x] `4:14` "01 — Logo Lockups" — primary lockup on light surface (`4:2`) and reversed lockup
      on navy (`4:8`). Icon mark built as a plain frame containing: Ellipse "Ring" (stroke
      only) + Line "Meridian Line" (vertical, full diameter) + Ellipse "Fixed Point" (filled,
      accent color). This 3-shape group (Ring/Meridian Line/Fixed Point) is the reusable icon
      mark — rebuild via the `buildMark(size, {circleVar, lineVar, dotVar})` pattern if you
      need more instances (not componentized as a Figma Component yet — see Known gaps below).
- [x] `4:59` "02 — Icon Scale (Favicon / App-Icon)" — same mark at 48px/32px/16px, confirmed
      legible down to 16px.
- [x] `4:68` "03 — Clear Space & Minimum Size" — dashed guide at `x` = fixed-point dot diameter,
      captions state min size 16px (icon alone) / 96px wide (full lockup).
- [x] `4:104` "04 — Color System" — swatch grid, all 8 primary/secondary/accent/semantic/neutral
      swatches bound live to the `Meridian Palette` variable collection (`VariableCollectionId:3:2`,
      mode `3:0` "Value"). Two additional neutrals (`neutral/bg`, `neutral/surface`) exist as
      variables but aren't shown as swatch cards (they're structural/background colors, not
      brand-facing swatches) — visible in the variable collection itself.
- [x] `4:133` "05 — Typography" — H1/H2/Body/Caption ramp in IBM Plex Sans + IBM Plex Mono
      label column.
- [x] `4:207` "06 — Voice & Tone" — 4 principle cards, DO in `semantic/confidence-high` green,
      DON'T in `semantic/alert` red.

Page 2 ("Research Agent — Sub-Identity", node `1:2`):

- [ ] Sub-mark/lockup pairing Meridian icon + "Research Agent" wordmark — not yet built
- [ ] App header/nav-bar mockup — not yet built
- [ ] App-icon-scale treatment — not yet built

## Known gaps / follow-ups if resuming

- The icon mark exists only as ad-hoc frames (multiple instances built independently), not as
  a single Figma `Component` with instances. If more mark instances are needed later (e.g. on
  Page 2), either reuse the `buildMark()` JS helper (copy from this log's build history / the
  `use_figma` call that created `4:14`) or promote one instance to a real Component first via
  `figma.createComponent()` / `node.detachInstance()` patterns — not done yet for time reasons,
  functionally identical either way for a static brand-identity deliverable.
- Variable collection is file-scoped (not a published library), so Page 2 (same file) can bind
  to it directly via `figma.variables.getLocalVariablesAsync()` — no import step needed.
