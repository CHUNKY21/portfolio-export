# Portfolio Design System — Figma Build Spec

Source of truth: `ThibodeauCaseB2B26.pdf` (Michael's existing shipped deck). This spec translates that visual language into a Figma-buildable system: color styles, text styles, spacing, and component specs for every recurring element used across all 5 case study concepts. Build these once in Figma as shared styles/components, then every concept's slides and web page reuse them — don't rebuild per concept.

---

## 1. Color Styles

Create these as Figma **Color Styles** (Local Styles → Color), named exactly as below so they're unambiguous in the layers panel.

| Style Name | Hex | Usage |
|---|---|---|
| `Brand/Rust` | `#C1592E` | Section divider backgrounds, breadcrumb accents |
| `Brand/Coral` | `#FF7E63` | Cover title text, gradient midpoint |
| `Brand/Coral-Light` | `#FFB088` | Gradient endpoint |
| `Brand/Coral-Warm` | `#FF9966` | Gradient startpoint |
| `Accent/Teal` | `#1B9E96` | Target audience badge |
| `Accent/Green` | `#3CAA6E` | "What we learned" callouts, Business-Goals-adjacent KPI stats, UX Strategy column |
| `Accent/Red` | `#D9534F` | "Unexpected Challenge" callouts, Pain Points column |
| `Accent/Blue` | `#3B9FD4` | Business Goals column, KPI stats |
| `Accent/Purple` | `#7B5AA6` | Feature Set column |
| `Accent/Magenta` | `#C23B8F` | KPI stat accent (rotation color) |
| `Accent/Lime` | `#C4E538` | Cover left-edge accent bar |
| `Neutral/Text-Primary` | `#2B2B2B` | Body copy |
| `Neutral/Text-Secondary` | `#6E6E6E` | Breadcrumb labels, captions |
| `Neutral/Background` | `#FFFFFF` | Default slide/page background |
| `Neutral/White` | `#FFFFFF` | Text on colored backgrounds |

**Gradient style** — `Brand/Cover-Gradient`: linear gradient, ~120°, stops at `Coral-Warm` (0%) → `Brand/Coral` (50%) → `Coral-Light` (100%). Overlay with a low-opacity (~8-12%) white circular line texture (concentric arcs) — build as a separate texture asset/component placed above the gradient fill.

---

## 2. Text Styles

Create as Figma **Text Styles**. Approximate a light/thin geometric sans (Century Gothic / Futura-alike). If those aren't licensed for the Figma file, use **Poppins Light** or **Century Gothic Pro** as the closest widely-available substitutes — flag this choice to Michael before finalizing, since exact typeface match matters for brand consistency with the existing PDF.

| Style Name | Font / Weight | Size | Usage |
|---|---|---|---|
| `Display/Cover-Title` | Light, 300 weight | 64px | Cover slide project title |
| `Display/Section-Divider` | Light, 300 weight | 48px | "Discovery", "Design" divider slides |
| `Heading/H1` | Regular, 400 weight | 32px | Slide primary headers |
| `Heading/H2` | Regular, 400 weight | 22px | Sub-section headers (e.g. "What's [Concept]?") |
| `Stat/KPI-Number` | Light, 300 weight | 56px | Oversized KPI numbers |
| `Body/Default` | Regular, 400 weight | 16px | Standard paragraph copy |
| `Body/Small` | Regular, 400 weight | 13px | Persona card labels, fine print |
| `Label/Breadcrumb` | Regular, 400 weight | 12px, uppercase or sentence case (match PDF) | Top-left breadcrumb header |
| `Label/Stat-Caption` | Regular, 400 weight | 13px | Label under each KPI number |
| `Quote/Pull-Quote` | Italic, 300 weight | 20px | Centered research quotes |

Line height: 1.4× for body text, 1.1–1.2× for display/stat sizes. Letter spacing: default, except `Label/Breadcrumb` which can take +2–4% tracking for a refined caption feel.

---

## 3. Spacing & Grid

- **Base unit**: 8px grid throughout.
- **Slide/page margin**: 64px on desktop/slide canvas, 24px on mobile web breakpoint.
- **Component gutter**: 32px between major components on a slide; 16px between related sub-elements (e.g., a KPI number and its caption).
- **Slide canvas**: build Figma frames at 1280×960 (4:3, matches the source PDF's slide proportions) for the deck; separate 1440px-wide frames (with 768px mobile variant) for the web page components.

---

## 4. Components to Build

Build each as a Figma **Component** (with variants where noted) so they're reusable via the Assets panel across all 5 concepts.

### 4.1 Breadcrumb Header
- Auto-layout row, top-left of every content slide/page
- Text: `Label/Breadcrumb` in `Neutral/Text-Secondary`
- Format: `Section Name    Project Title` (two text segments separated by generous spacing, not a literal pipe character — matches source PDF's spacing-based separator)
- **Variant property**: `section` (Discovery & Research / Design / Introduction / Results)

### 4.2 Cover / Closing Slide
- Frame: full slide canvas
- Elements: `Display/Cover-Title` (top-right aligned) in `Brand/Coral`, one-line description beneath in `Body/Default`, author name + site bottom-right in `Body/Small`
- Bottom third: `Brand/Cover-Gradient` rectangle spanning full width, with the circular line texture overlay
- Left edge: two vertical bars — `Accent/Lime` (outer, ~8px) and `Brand/Rust` (inner, ~24px)
- **Variant property**: `type` (Cover / Closing) — Closing swaps title for contact info

### 4.3 Section Divider Slide
- Frame: full slide canvas, fill `Brand/Rust`
- Title: `Display/Section-Divider` in `Neutral/White`
- Supporting paragraph: `Body/Default` in `Neutral/White` at ~85% opacity
- **Variant property**: `section-name` (Discovery / Design / Results / etc.)

### 4.4 KPI Stat Block
- Auto-layout column, no border/fill (transparent — the color lives in the number itself)
- Number: `Stat/KPI-Number`, color cycles through `Accent/Blue`, `Accent/Magenta`, `Accent/Teal`, `Accent/Green` across a set of stats on one slide (assign per-instance, not fixed per component)
- Caption: `Label/Stat-Caption` in `Neutral/Text-Secondary`, directly beneath
- **Variant property**: `accent-color` (Blue / Magenta / Teal / Green)
- Build as a small set (e.g. 4 instances) that auto-lay-out horizontally or in a 2×2 grid on the Results/Discovery slides

### 4.5 Target Audience Badge
- Circle shape, fill `Accent/Teal`, sized to comfortably contain 2–3 short bullet lines
- Text inside: `Body/Small` in `Neutral/White`, centered
- Header label "Target audience" in `Heading/H2` sits above/outside the circle, not inside it (matches source layout)

### 4.6 Pain Points → Business Goals → UX Strategy → Feature Set Framework
- Four-column auto-layout row, equal-width columns, small gap between (~16px) with `+` glyphs (Heading/H1 weight, `Neutral/Text-Primary`) centered in the gaps between columns 1–2, 2–3, and an `=` glyph between columns 3–4
- Each column: solid-fill rectangle, full-bleed vertical, with a `Heading/H2` white header at top ("Pain Points" / "Business Goals" / "UX Strategy" / "Feature Set") and a bulleted list in `Body/Small` white beneath
- Column fills in order: `Accent/Red`, `Accent/Blue`, `Accent/Green`, `Accent/Purple`
- **Variant property**: none needed — this is a fixed 4-column set; build as one component with 4 nested list-content slots

### 4.7 Insight Callout Box
- Rounded-corner rectangle, solid fill, white text (`Body/Default`)
- **Variant property**: `type` (Learned / Challenge)
  - `Learned`: fill `Accent/Green`, header text "What we learned"
  - `Challenge`: fill `Accent/Red`, header text "Unexpected Challenge"
- Sized to sit alongside a supporting screenshot/sketch placeholder (leave a paired empty placeholder frame next to each instance)

### 4.8 Persona Card
- Bordered rectangle (1px, `Neutral/Text-Secondary` at low opacity), white fill
- Layout: photo placeholder (top-left, square), name/role/tenure (`Heading/H2` + `Body/Small`) beside it
- Below: `Quote/Pull-Quote` sentiment quote
- Below that: three labeled bulleted sections — "Responsibilities", "Key Challenges & Areas of Concern", "Wishlist" — each header in `Body/Default` bold-weight (or `Heading/H2` at smaller size), list items in `Body/Small`

### 4.9 Pull-Quote
- Centered text block, `Quote/Pull-Quote` style, `Neutral/Text-Secondary`
- No border or background — typography-only component
- Used sparingly: one per relevant slide

---

## 5. Figma File Organization

Recommended page structure inside the Figma file:

```
📄 Design System        ← all components + styles from this spec, built once
📄 00 - Index / Cover
📄 01 - Compliance Alert Triage Copilot
📄 02 - Conversational Risk Assessment Tool
📄 03 - Intelligent Portfolio Dashboard
📄 04 - AI-Personalized Investment Onboarding
📄 05 - Smart Report Generator
📄 Web - Squarespace Components   ← web-breakpoint variants of the same components
```

Each concept page reuses instances of the Design System page's components — populate content per concept from that concept's brief + discovery file, but never redefine a component's structure inside a concept page. If a component needs to change, change it once on the Design System page so it propagates everywhere.

---

## 6. What's Not in This Spec

This spec defines structure and style, not final content or imagery. Actual screenshots, app mockup screens, and photography (persona headshots) are separate assets to source or design per concept — this system tells you where they go and how they're framed, not what they show.
