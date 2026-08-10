# Meridian Exception Manager — Sub-Identity Log

Working log for the Exception Manager sub-identity build in Figma file
`wR1jR86W4zV1umY9tK6D8Z` ("Meridian — Brand Identity System"), page
**"Exception Manager — Sub-Identity"**.

Written incrementally so a fresh session can resume without re-deriving
decisions. Update this file after every meaningful Figma change.

---

## Status

**IN PROGRESS** — started 2026-08-01.

Do not touch pages "Meridian — Parent Brand" or "Research Agent — Sub-Identity"
in this file; a sibling agent owns those in parallel.

---

## 0. Reconciliation flag (read first)

At the time this page was started, `get_metadata` on the file root showed
**only one page: "Page 1" (empty)** — the Meridian parent brand page and
its color-variable collection / logo mark did not exist yet (sibling agent
had not gotten there). Per instructions, this build proceeds on a **reasonable
placeholder assumption** for the parent brand:

- Placeholder parent palette: precise, cool navy fintech palette (see §2).
- Placeholder parent mark: geometric circle-and-meridian-line mark evoking
  a navigation/longitude-line motif (ties to the "Meridian" name).
- Placeholder typeface: Inter (see §3).

**TODO once the parent brand page exists:** re-check its actual color
variables / logo mark / type choice, and reconcile this page's palette,
mark, and type against them (rename/alias variables rather than duplicating
if the parent used different hex values or a different collection name).
The variable collection created here is deliberately named
`Meridian Palette (EM draft — reconcile)` to make it obvious this is
provisional and not the canonical shared collection.

---

## 1. Brand relationship / concept rationale

Meridian = a navigation/measurement metaphor (lines of longitude,
navigational precision instruments — sextant, compass, chronometer).
Exception Manager is the **ambient/push** counterpart to Research Agent
(pull, calm, precise, "answers when asked"). Exception Manager's job is to
be **watchful and prioritizing without being alarmist** — it flags points
along the "meridian" that need attention, always with a visible reason
(the case study's central lesson: bare scores get distrusted; unexplained
alerts get tuned out within weeks).

Mark concept: the shared Meridian mark (circle + vertical meridian line,
navy) gets a small **amber marker** placed on the line, off-center, with a
faint concentric "scan" ring around it — read as "a flagged point along the
line, being watched," not a siren. This is deliberately a **brass/instrument
metaphor** (ship's instrument brass tone), not a traffic-light red — it
supports the "attention, not alarm" brief requirement.

---

## 2. Color

### Placeholder parent/shared tokens (to reconcile against real parent brand)
| Token | Hex | Use |
|---|---|---|
| `meridian/navy` | `#0F2540` | Primary mark / wordmark ink, dark UI chrome |
| `meridian/ink` | `#1B2B3A` | Body text on light |
| `meridian/slate` | `#64748B` | Secondary text, low-emphasis UI |
| `meridian/cloud` | `#E2E8F0` | Borders, dividers |
| `meridian/paper` | `#F8FAFC` | App background |
| `meridian/white` | `#FFFFFF` | Surfaces |

### Exception Manager accent — 3-tier severity scale
Single **amber/gold/bronze hue family**, escalating in saturation/depth
rather than switching hue to red — this is the deliberate "attention, not
alarm" choice called out in the brief.

| Tier | Token | Hex | Meaning | Notes |
|---|---|---|---|---|
| 1 — Routine | `em/tier-1-routine` | `#E8CE84` (pale gold) | Newly flagged, low exposure, matches a known tolerated pattern | Barely a signal — visible in list, doesn't demand action |
| 2 — Elevated | `em/tier-2-elevated` | `#C99A2E` (brass/gold) | Needs attention this shift; primary Exception Manager accent/brand color | Used for the sub-mark accent itself |
| 3 — Escalated | `em/tier-3-escalated` | `#8C5A12` (deep bronze) | Aged past threshold and/or high exposure/regulatory relevance | Darker + heavier weight, never red, never flashing |

Rationale: escalation reads through **value/depth within one hue**, echoing
"aging escalation" from the brief (exceptions get visually heavier over
time, not redder/alarmed). Keeps the whole system calm even at tier 3.

Contrast checked informally against white/paper backgrounds for text use;
tier 2/3 are also used as fills with white or navy text on top, not as
small text-on-white by themselves where avoidable (tier 1 pale gold
especially needs dark text, not white).

---

## 3. Typography

**Placeholder: Inter** (parent brand's actual type choice not yet
confirmed — flag for reconciliation once "Meridian — Parent Brand" page
exists). Using Inter Semibold for marks/headers, Inter Medium/Regular for
UI and body — a neutral, precise, screen-native grotesque consistent with
an institutional fintech ops tool.

---

## 4. Voice & tone principles (Exception Manager–specific)

Grounded directly in the case study's design lesson (bare priority scores
were distrusted; the fix was a plain-language reason shown before any
click):

1. **Explain before you interrupt.** Never surface a ranked/flagged item
   without a plain-language reason attached inline — not behind a click,
   not a bare score. ("flagged: exposure above threshold, no prior
   tolerated pattern match" — not "Priority: 87.")
2. **Never a bare number.** Severity and ranking are always paired with
   the reason a human can act on. A number alone reads as a black box;
   a reason reads as a colleague's judgment call.
3. **Say when you're not sure.** When confidence is not high, the system
   says so rather than ranking silently — uncertainty is visible, not
   hidden inside a score.
4. **Acknowledge dismissals out loud.** "Not actually an issue" gets a
   visible response ("got it — deprioritizing similar patterns"), not
   silent disappearance — the feedback loop has to be legible in the
   moment to be trusted.

Tone in copy: plain, specific, unhurried — describes *what* and *why*,
never uses urgency language ("Act now," "Critical!!") even at tier 3.
Escalation is communicated through visual weight (color depth, icon,
position) not through alarmed language.

---

## 5. Figma build log

(Updated as work proceeds — node IDs recorded so a fresh session can find
things without re-deriving.)

- File key: `wR1jR86W4zV1umY9tK6D8Z`
- Page created: "Exception Manager — Sub-Identity" — id `2:2`
- Confirmed via `get_metadata` before starting: file had only empty "Page 1"
  (id `0:1`) — no parent brand page, no existing variable collections. This
  build is the placeholder assumption path described in §0.
- Variable collection `Meridian Palette (EM draft — reconcile)` — id
  `VariableCollectionId:2:3`, mode "Value". Variable IDs:
  - `meridian/navy` → `VariableID:2:4`
  - `meridian/ink` → `VariableID:2:5`
  - `meridian/slate` → `VariableID:2:6`
  - `meridian/cloud` → `VariableID:2:7`
  - `meridian/paper` → `VariableID:2:8`
  - `meridian/white` → `VariableID:2:9`
  - `em/tier-1-routine` → `VariableID:2:10`
  - `em/tier-2-elevated` → `VariableID:2:11`
  - `em/tier-3-escalated` → `VariableID:2:12`
  - All scoped to `FRAME_FILL, SHAPE_FILL, TEXT_FILL, STROKE_COLOR`.

### Build steps
- [x] Page created (`2:2`)
- [x] Variable collection created with parent placeholder + EM tier colors
- [x] Sub-mark / lockup (Meridian mark + amber marker + "Exception Manager"
      wordmark) — heading `4:15`, standalone icon frame `4:16` (96x96, at
      x100/y110), lockup `4:28` (at x300/y110, contains small icon `4:34`,
      wordmark row `4:29` with "Meridian" `4:30` / amber divider `4:31` /
      "Exception Manager" `4:32`). Icon design: navy circle + vertical
      meridian line + faint slate equator line + amber marker dot on the
      line with a faint amber "scan ring" around it (radar/watching cue,
      not a badge/alert dot). NOTE: built the small lockup icon as a
      from-scratch scaled copy (44px), not `frame.resize()` on a clone —
      `resize()` does not proportionally scale a frame's children, which
      caused an overlap bug on the first attempt (fixed in the same
      session).
- [x] Severity scale legend (3-tier swatches with labels) — heading `4:105`,
      row `4:106` at x100/y300, three cards `4:107` (Tier 1), `4:111`
      (Tier 2), `4:115` (Tier 3), each a swatch + label + plain-language
      description. Verified visually: reads as one warm hue family getting
      denser/heavier, not a stoplight.
- [x] Type ramp (Inter, placeholder) — heading `4:134` flags reconciliation
      need, disclaimer text `4:135`, ramp `4:136` at x100/y525 with 3
      sample rows (`4:137` heading, `4:140` UI label, `4:143` body/reason
      text), each using realistic Exception Manager copy as the sample
      string (not lorem ipsum) so type + voice can be checked together.
- [x] Voice & tone panel (principles from §4) — heading `4:146`, panel
      `4:147` at x100/y780 (height 270), 4 numbered principle rows
      (`4:148`, `4:153`, `4:158`, `4:163`), numerals in `em/tier-2-elevated`
      amber, everything else navy/slate.
- [x] Worklist-header mockup — heading `4:208`, container `4:209` (760px
      wide, white surface, cloud-colored 1px border, x100/y1120): breadcrumb
      `4:210` ("Meridian / Exception Manager"), title row `4:214`
      ("Exceptions" + count/ranking-basis subtitle), tier-count pill row
      `4:217` (3 pills bound to the tier variables — escalated pill uses
      white text on the dark tier-3 fill for contrast, other two use navy
      text), divider `4:224`, two example worklist rows (`4:225`, `4:231`)
      each with a tier-colored left accent bar, bold title, and a reason
      line written in the case study's actual "flagged: ..." voice —
      demonstrates the "never a bare number" principle directly in a
      realistic UI context, not just as a stated rule.
- [x] App-icon-scale treatment — heading `4:283`, master 128px icon `4:284`
      (rounded-square navy tile `cornerRadius 28`, containing a
      **simplified** glyph: white circle + white vertical line + single
      amber marker dot — deliberately dropped the faint scan-ring and
      equator line from the full mark, since those wash out below ~48px),
      scale strip `4:288` at x100/y1780 with clones rescaled via
      `node.rescale()` (NOT `resize()` — see the earlier lockup bug) to
      512/128/64/32/16px (`4:290`, `4:296`, `4:302`, `4:308`, `4:314`).
      Verified visually: glyph stays legible/identifiable down to 16px.
- [x] Final page layout pass + full-page screenshot — see below.

*(Details/node IDs added as each step completes.)*
