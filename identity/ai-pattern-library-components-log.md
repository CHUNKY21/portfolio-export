# AI Pattern Library — Components Build Log

Working log for the 5 reusable Figma COMPONENT_SETs built for the AI Pattern
Library case study (source: `../briefs/03-ai-pattern-library-discovery.md`,
`../briefs/03-ai-pattern-library-wireframes.md`). Written incrementally so a
fresh session can resume if this one is cut off.

Figma file: key `52GcdAWRbAgd40fVo0er1C` ("AI Pattern Library — Identity & Components")
Page: **"Components"** (created by this session — did not exist before).
Sibling page "Foundations & Identity" (node `0:1`) owns brand identity + the
variable collection — **not touched by this session**.

## Resume note (found at session start)

- No prior "Components" page existed. No prior components log existed. This
  session starts fresh per the brief's fallback instruction.
- Sibling identity agent's log (`ai-pattern-library-identity-log.md`) confirms
  brand name **Sextant** and a Figma variable collection already built:
  - Collection: `Sextant Foundations`, id `VariableCollectionId:2:2`, 1 mode
    (`Default`, mode id `2:0`), 21 variables.
  - Verified live via `getLocalVariableCollectionsAsync` / `getLocalVariablesAsync`
    at the start of this session — all 21 variable IDs below match the log
    exactly, nothing stale.
  - **These are real tokens, not placeholders** — this build binds fills to
    them directly rather than using literal hex.

### Token IDs used by these components (verified live, not from memory)

| Token | Variable ID | Hex |
|---|---|---|
| `color/ai-state/confidence-high` | `VariableID:2:11` | `#1E8E5A` |
| `color/ai-state/confidence-medium` | `VariableID:2:12` | `#C98A1F` |
| `color/ai-state/confidence-low` | `VariableID:2:13` | `#7A5980` |
| `color/ai-state/citation` | `VariableID:2:14` | `#0E7C86` |
| `color/ai-state/streaming` | `VariableID:2:15` | `#7C5CFA` |
| `color/ai-state/error` | `VariableID:2:16` | `#D92D20` |
| `color/ai-state/handoff` | `VariableID:2:17` | `#C2410C` |
| `color/neutral/50..900` | `VariableID:2:4`..`2:10` | gray scale |
| `color/semantic/text-primary` | `VariableID:2:18` | → neutral/900 |
| `color/semantic/text-secondary` | `VariableID:2:19` | → neutral/600 |
| `color/semantic/border-default` | `VariableID:2:20` | → neutral/200 |
| `color/semantic/background-default` | `VariableID:2:21` | → neutral/50 |
| `color/semantic/background-surface` | `VariableID:2:22` | → neutral/100 |
| `color/semantic/brand-primary` | `VariableID:2:23` | → brand/primary |

Fonts confirmed available: Inter (`Regular`, `Medium`, `Semi Bold` — note the
space), IBM Plex Mono (`Regular`, `Medium`, `SemiBold` — no space).

## Status

- [x] "Components" page created — page id `6:2`
- [x] 1. Confidence/Certainty Indicator — Level: High/Medium/Low × State: Default/Compact
- [ ] 2. Citation/Source Card — State: collapsed/expanded
- [ ] 3. Streaming-Response State — State: streaming/complete/interrupted
- [ ] 4. Correction/Feedback Control — State: default/flagged/acknowledged
- [ ] 5. Human-Handoff Banner — State: proposed/confirmed

(updated as each component set completes, with component-set node IDs)

---

## 1. Confidence / Certainty Indicator — DONE

- **Component-set node ID:** `7:44` (name "Confidence / Certainty Indicator")
- **Variant properties:** `Level` = High/Medium/Low, `State` = Default/Compact (6 variants total)
- **Child variant IDs:** High/Default `7:2`, High/Compact `7:9`, Medium/Default `7:16`,
  Medium/Compact `7:23`, Low/Default `7:30`, Low/Compact `7:37`
- **Title text node:** `7:45`. **Usage-notes doc frame:** `7:46` (Usage / When NOT to
  use this / Accessibility, positioned directly below the component set).
- **Design:** neutral filled-to-empty 3-segment intensity scale (`neutral/800` filled,
  `neutral/200` empty) as the primary signal, a small accent dot bound to
  `color/ai-state/confidence-{high,medium,low}` as a *secondary* reinforcing signal,
  plus a plain-text qualifier ("High confidence" / "Partial confidence — verify
  before use" / "Low confidence — verify before use") that carries the primary
  meaning — directly implements the case study's "not color-only" iteration finding
  (avoids the red/yellow/green error-color collision). Compact state shrinks
  padding/segment size and shortens the qualifier to one word ("High"/"Partial"/"Low").
- **Token bindings:** all fills/strokes bound to `Sextant Foundations` variables (no
  hardcoded hex) — confirmed via `setBoundVariableForPaint`, not literal colors.
- **Verified via screenshot:** all 6 variants render distinctly; doc frame text
  initially clipped (`textAutoResize` order bug — `resize()` was called after
  setting `textAutoResize`, which resets sizing mode back to fixed; fixed by
  setting `textAutoResize = "HEIGHT"` *after* the resize call) — re-screenshotted,
  confirmed fixed, frame auto-hugged to 272px.
