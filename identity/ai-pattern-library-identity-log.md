# AI Pattern Library — Brand Identity Log

Working log for the brand identity built for the fictional AI Pattern Library
design system (case study source: `../briefs/03-ai-pattern-library-discovery.md`).
Written incrementally so a fresh session can resume if this one is cut off.
**This file is load-bearing for the sibling agent building the component
library in the same Figma file** — the variable collection ID and variable
IDs below are what their component fills need to bind to.

Figma file: key `52GcdAWRbAgd40fVo0er1C` ("AI Pattern Library — Identity & Components")
Page: "Foundations & Identity" (renamed from default "Page 1", node id `0:1`)

Status as of this write (resumed session): variable collection created and
populated (21 variables, verified intact). Mark, wordmark/lockup, and
clear-space/min-size guide are built and verified by screenshot. Type ramp,
color swatch reference frame, voice & tone frame, and docs-header mockup
not yet built — see TODO at bottom.

**Note on path**: the brief that kicked off this resumed session pointed at
a nonexistent path (`~/Desktop/AI Class/case studies AI/portfolio-export/`).
The real project root is `/Users/michaelthibodeau/Projects/portfolio-export`
— this log, the discovery doc, and everything else referenced below live
there. Resuming agents should use that path.

---

## 1. Name: Sextant

**Chosen name: Sextant**

Reasoning:
- A sextant is a navigation instrument that fixes your position by measuring
  the angle between a known reference point (a star, the horizon) and your
  target. That is almost exactly what this component library does for AI
  interfaces: it gives product teams a fixed, shared reference for
  otherwise-fuzzy states (how sure is the system, where did this come from,
  is it still working, did it get this wrong, when should it hand off).
  "Sextant" reads as *the instrument you use to know where you actually
  stand* — a fitting metaphor for a confidence/trust component set.
- It fits the astronomical/navigation naming convention real design systems
  favor (Polaris, Lightning, Atlassian's own "wayfinding" language) while
  staying ownable — it isn't already a major design-system name the way
  "Compass" or "Beacon" effectively are.
- It's short, a real word, slightly abstract/technical without being cute —
  matches the brief's instruction to avoid both generic ("AI Components")
  and overly whimsical names.
- Bonus resonance with the component set itself: a sextant's graduated arc
  (the scale you read the angle off) is a segmented dial — which mirrors the
  actual Confidence Indicator component's chosen visual language from the
  case study (a "neutral intensity scale, filled-to-empty segments," adopted
  specifically to avoid the red/yellow/green traffic-light collision with
  error states). The wordmark/mark should lean into this: a graduated arc,
  not a compass rose or a generic AI sparkle.

Tagline (for docs header / cover use): **"A shared instrument for AI states."**

---

## 2. Color system

### Figma variable collection

- **Collection name:** `Sextant Foundations`
- **Collection ID:** `VariableCollectionId:2:2`
- **Mode:** single mode named `Default`, mode ID `2:0`
- **File:** `52GcdAWRbAgd40fVo0er1C`, created on page `0:1` ("Foundations & Identity") — variables are file-scoped, not page-scoped, so the sibling agent can bind to them from the "Components" page without switching pages.

All color variables were created with `scopes: ["ALL_FILLS", "STROKE_COLOR"]`
and a WEB code syntax (`--color-<group>-<name>`). All are type `COLOR`.

### Primitives

| Token (Figma name) | Variable ID | Hex | Notes |
|---|---|---|---|
| `color/brand/primary` | `VariableID:2:3` | `#2F5EDB` | Primary/brand accent — indigo-blue. Used sparingly (nav, links, primary buttons, focus rings) against mostly neutral tones, per the "credible infrastructure not flashy product" direction. |
| `color/neutral/50` | `VariableID:2:4` | `#F7F8FA` | Lightest neutral — page background. |
| `color/neutral/100` | `VariableID:2:5` | `#EDEFF2` | Surface / card background one step down from page bg. |
| `color/neutral/200` | `VariableID:2:6` | `#DCE0E5` | Default borders / dividers. |
| `color/neutral/400` | `VariableID:2:7` | `#9BA3AF` | Disabled text, placeholder text, subtle icons. |
| `color/neutral/600` | `VariableID:2:8` | `#5B6472` | Secondary body text. |
| `color/neutral/800` | `VariableID:2:9` | `#262B33` | Dark surfaces / inverse text on light. |
| `color/neutral/900` | `VariableID:2:10` | `#14171B` | Primary text, headlines. |

7-step cool-neutral gray scale (slight blue undertone to sit naturally next
to the brand blue). This is the scale the component library should use for
all non-semantic UI chrome (backgrounds, borders, default text).

### AI-state semantic colors — **what the component library binds to**

These are the actual tokens the 5 AI Pattern Library components (Confidence
Indicator, Citation/Source Card, Streaming-Response State, Correction/
Feedback Control, Human-Handoff Banner) should bind their fills to.

| Token (Figma name) | Variable ID | Hex | Maps to |
|---|---|---|---|
| `color/ai-state/confidence-high` | `VariableID:2:11` | `#1E8E5A` | Confidence Indicator — high confidence state |
| `color/ai-state/confidence-medium` | `VariableID:2:12` | `#C98A1F` | Confidence Indicator — medium/partial confidence state |
| `color/ai-state/confidence-low` | `VariableID:2:13` | `#7A5980` | Confidence Indicator — low confidence state |
| `color/ai-state/citation` | `VariableID:2:14` | `#0E7C86` | Citation/Source Card accent |
| `color/ai-state/streaming` | `VariableID:2:15` | `#7C5CFA` | Streaming-Response State accent (in-progress indicator) |
| `color/ai-state/error` | `VariableID:2:16` | `#D92D20` | Correction/Feedback Control — error/incorrect-answer flag state |
| `color/ai-state/handoff` | `VariableID:2:17` | `#C2410C` | Human-Handoff Banner accent |

**Important rationale — read before binding the Confidence Indicator:**
the case study's own iteration finding (Design & Iteration section) is that
a red/yellow/green traffic-light treatment for confidence collided with the
system's existing error-color language ("red read as error, not low
confidence") and was replaced with a neutral intensity scale (filled-to-empty
segments) *plus* a plain-text qualifier, specifically to make the signal
legible without relying on color alone. Consequences for the component
build:
- **Do not treat `confidence-low` as a second "error" color.** It's
  deliberately a muted plum/violet-gray, not red, so it never reads as a
  failure state. `color/ai-state/error` is reserved exclusively for the
  Correction/Feedback Control's actual error/flag state.
- The confidence-high/medium/low tokens should be used as a **secondary,
  low-saturation accent** (e.g. a small label chip, an icon tint, a thin
  border) layered on top of the neutral intensity-scale fill (built from the
  `color/neutral/*` scale) — not as the fill of the whole indicator. Color
  is a reinforcing signal, not the only signal; the text qualifier
  ("High confidence" / "Partial — verify before use") carries the primary
  meaning, consistent with the accessibility/non-color-only-signaling pass
  called out in the case study's documentation standard.
- All 7 semantic hues (confidence-high/medium/low, citation, streaming,
  error, handoff) were chosen to be mutually distinguishable by hue, not just
  lightness, so they still read apart from each other for colorblind users —
  green / gold / plum / teal / violet / red / burnt-orange. Verify actual
  contrast ratios against the neutral backgrounds before shipping; these are
  accent/UI-component colors (3:1 AA threshold for non-text UI), not
  guaranteed to hit 4.5:1 text contrast on their own — pair with
  `semantic/text-primary` (near-black) for any text label inside a
  colored chip, don't set body copy directly in a semantic-state hue.

### Semantic aliases (layer on top of primitives — bind UI chrome to these, not raw neutrals)

| Token (Figma name) | Variable ID | Aliases → | Use |
|---|---|---|---|
| `color/semantic/text-primary` | `VariableID:2:18` | `neutral/900` | Headlines, primary body text |
| `color/semantic/text-secondary` | `VariableID:2:19` | `neutral/600` | Secondary/supporting text, captions |
| `color/semantic/border-default` | `VariableID:2:20` | `neutral/200` | Default borders, dividers, input outlines |
| `color/semantic/background-default` | `VariableID:2:21` | `neutral/50` | Page background |
| `color/semantic/background-surface` | `VariableID:2:22` | `neutral/100` | Card/panel background, one step above page bg |
| `color/semantic/brand-primary` | `VariableID:2:23` | `brand/primary` | Links, primary actions, focus rings — use sparingly |

**Total: 21 variables, 1 collection, 1 mode ("Default").**

---

## 3. Typography (planned — confirm against Figma state once built)

- **UI/doc sans:** Inter — confirmed available in this Figma file with full
  weight range (Thin through Black, incl. Semi Bold — note the space in
  "Semi Bold" / "Extra Bold" for Inter specifically).
- **Code/numeric mono:** IBM Plex Mono — confirmed available. Note style
  naming differs from Inter: Plex Mono uses `SemiBold` (no space), not
  `Semi Bold`. Used for the confidence-score numeric display and any
  code/token-name references in docs.
- Rationale: Inter is the de facto standard for technical docs-site UI
  (neutral, high legibility at small sizes, huge weight range for
  hierarchy without needing display fonts). IBM Plex Mono pairs cleanly
  with Inter (both from type families built for technical/software
  contexts), and its slightly warmer, more geometric mono forms read as
  "instrument readout" for the numeric confidence score — reinforcing the
  Sextant metaphor (a sextant gives you a numeric reading).

Type ramp — **not yet created as Figma text styles**, see TODO.

---

## 4. Voice & tone (planned)

Draft principles, grounded in the case study's actual governance/adoption
problem (teams route around governance and ship one-offs unless the
documentation itself makes adoption easy and the limits explicit):

1. **Prescriptive, not just descriptive.** Say what to do, not just what
   exists — every component page leads with the intended use, not a prop
   list.
2. **Explicit about limits, not just the ideal case.** Every component
   documents a "when NOT to use this" section as a first-class element, not
   a footnote — directly reflects the pilot-team finding that teams adopted
   the pattern *more* once the documentation was explicit about its limits.
3. **Shows the failure/uncertainty path, not just the happy path.** Low
   confidence, a flagged-wrong answer, a stalled stream, a handoff — these
   get the same documentation weight as the success state, because they're
   the trust-critical moments this library exists to standardize.
4. **Names what's shared vs. what's yours.** Every page is explicit about
   what the pattern standardizes (visual language, interaction behavior,
   accessibility baseline) vs. what stays product-specific (the actual
   model, confidence score, cited source, escalation destination) — so
   adopting teams know exactly where the library's authority ends and their
   own product decisions begin.

---

## 5. Mark / wordmark / clear-space — BUILT, verified by screenshot

Frame `3:7` "01 — Mark & Wordmark" (x=0, y=0, 680x414) on the Foundations &
Identity page. Contains:
- `3:2` "Sextant Mark — Standalone" (96x96 frame, `clipsContent: true`) — 4
  full-circle ELLIPSE nodes (`3:3`–`3:6`) each with pie/arc data forming
  quarter-segments, positioned at (-96,-96) sized 192x192 and clipped by the
  parent frame to produce the visible graduated-arc dial. Segment fills
  (outer→inner): `color/brand/primary` (×2, the two outermost/"filled"
  segments), `color/neutral/400`, `color/neutral/200` — reads as a dial
  fading from full brand-blue at the top down to near-empty at the tail,
  literally the "filled-to-empty segments" confidence-indicator language
  applied to the brand mark itself.
- `4:9` "Wordmark — Sextant" — Inter Semi Bold 28px, `-1px` letter-spacing,
  bound to `color/semantic/text-primary`.
- `4:10` "Primary Lockup" — small mark clone (`4:4`, 40x40) + wordmark, 12px
  gap, auto-positioned.
- Captions (`4:3`, `4:11`) in Inter Regular 12px bound to
  `color/semantic/text-secondary`.

Screenshot-verified: mark reads clearly as a graduated quarter-arc dial in
brand blue fading to neutral gray; wordmark lockup is clean. This satisfies
the brief's "real vector shapes" requirement (arc/pie ellipses, not an
image).

### Clear space & minimum size — BUILT, verified by screenshot

Frame `8:2` "02 — Clear Space & Minimum Size" (x=760, y=0, 680x520), same
background/border/heading style as frame 01 (fill `color/neutral/50`,
stroke `color/neutral/200`).
- Clear-space diagram: dashed boundary rectangle (`8:5`, 144x144, dash
  [4,4], stroke `color/neutral/400`) with a mark clone (`8:6`) centered
  inside with 24px padding on all sides. Label (`8:11`): "X = 24px minimum
  clear space (25% of mark height) on all sides, scaling proportionally
  with the mark."
- Minimum-size row: three mark clones rescaled via `node.rescale()` to
  32px / 20px / 12px height (ids `8:13`, `8:18` — wait, actual returned ids
  were `8:13, 8:18, 8:19, 8:24, 8:25, 8:30` — the three mark clones plus
  their three labels, alternating), captioned "32px — comfortable",
  "20px — recommended minimum", "12px — do not use" (last one in
  `color/ai-state/error` red to flag it as the failure case).

Both sections screenshot-verified together — full section reads cleanly at
680x520, no clipping/overlap.

---

## TODO / resume point

If resuming a cut-off session, this is what's done vs. not:

- [x] Name chosen and documented (Sextant)
- [x] Figma page renamed to "Foundations & Identity"
- [x] Variable collection `Sextant Foundations` created (`VariableCollectionId:2:2`), 21 variables (see tables above) — **done, verified via return values**
- [ ] Type ramp — Figma text styles for H1-H4, Body, Caption, Code (Inter + IBM Plex Mono, fonts confirmed available)
- [ ] Standalone mark (graduated-arc dial) as real vector shapes
- [ ] Wordmark lockup (mark + "Sextant" in Inter)
- [ ] Clear-space / minimum-size guidance frame
- [ ] Color swatch/token reference frame (visual, on-canvas, showing all 21 variables with hex + name)
- [ ] Voice & tone frame (the 4 principles above, laid out on canvas)
- [ ] Applied context mockup: simple docs-site header using the mark + wordmark + brand color
- [ ] Final screenshot verification pass of the full "Foundations & Identity" page
