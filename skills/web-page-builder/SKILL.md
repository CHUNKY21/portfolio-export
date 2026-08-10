---
name: web-page-builder
description: Build a Squarespace-ready HTML block from a paired brief + discovery file in /portfolio/briefs/. Use this whenever the user asks to build the web version, create the Squarespace page, generate the case study web page, or export any of the 5 portfolio concepts to HTML. Always use this skill rather than freehand HTML-writing to keep all 5 case study web pages structurally and visually consistent.
---

# Web Page Builder

Converts one case study concept (a brief + discovery file pair from `/portfolio/briefs/`) into a self-contained HTML block ready to paste into a Squarespace Code Block.

## Before You Start

1. Read `/portfolio/CLAUDE.md` if you haven't already this session — it defines the Design Style Guide (colors, typography, and the recurring structural components: breadcrumb headers, section dividers, KPI stat blocks, the four-column framework, callout boxes, persona cards) and the Squarespace HTML conventions this skill must follow. This is Michael's real, shipped visual language — reproduce it, don't invent a new one.
2. Read both files for the target concept: `NN-concept-name.md` (brief) and `NN-concept-name-discovery.md` (discovery).
3. Confirm which concept you're building if it's ambiguous, or whether this is a single case study detail page vs. a card for the index/landing page.

## Two Output Modes

Ask (or infer from context) which is needed:

**Mode A — Index Card**: A compact card for the case study grid on the portfolio landing page. Title, tagline, 2-3 headline metrics, click-through affordance. Matches the card pattern already established in the portfolio (see CLAUDE.md brand tokens).

**Mode B — Full Detail Page**: The complete case study as a standalone page/section, expanding all content from the brief and discovery files.

## Full Detail Page Structure (Mode B)

Reproduce the same structural components CLAUDE.md defines for the PDF, as HTML/CSS sections in this order:

1. **Cover/Hero**: title, tagline, one-line description, pull-quote from discovery Pain Points — coral gradient banner treatment, thin title typography, lime-green/rust accent bar
2. **Introduction**: "What's [Concept]?" description + teal target-audience badge (circular, from brief `audience`) + The problems (bulleted, from discovery) + role framing
3. **Discovery & Research**: KPI stat block component (oversized colored numbers, no borders) built from discovery Timeline/Research metrics; flag missing numbers with `[METRIC NEEDED: description]` rather than fabricating
4. **Pain points from interviews**: numbered list + supporting pull-quote
5. **Persona card**: bordered card component (photo placeholder, name/role, italic sentiment quote, Responsibilities/Key Challenges/Wishlist)
6. **Pain Points + Business Goals + UX Strategy = Feature Set**: the four-column colored framework (red/blue/green/purple), connected visually with `+` and `=`
7. **Design/Process**: map to Research→Ideation→Prototyping→Testing→Handoff (same phase language as CLAUDE.md and slide-builder), with green "what we learned" / red "unexpected challenge" callout boxes where source material supports them, and `<!-- VISUAL: description -->` HTML comments marking where screenshots/wireframes go
8. **Results**: KPI stat block component, final metrics
9. **Key Insight**: the brief's Design Rationale, in the pull-quote/emphasis treatment — per CLAUDE.md's mandatory rule, this must be visually prominent, not a small footnote
10. **CTA**: contact section, can reuse the coral gradient banner treatment from the cover

## Technical Requirements

- Self-contained: inline `<style>` tag, no external CSS/JS dependencies beyond system fonts
- Responsive: single-column stacking below 768px breakpoint
- Brand tokens (must match CLAUDE.md's Design Style Guide and the slide-builder output exactly):
  - Rust: `#C1592E` | Coral gradient: `#FF9966`→`#FF7E63`→`#FFB088` | Teal: `#1B9E96` | Green: `#3CAA6E` | Red/pink: `#D9534F` | Blue: `#3B9FD4` | Purple: `#7B5AA6` | Magenta: `#C23B8F` | Lime: `#C4E538`
  - Typography: thin/light geometric sans-serif for titles (e.g., `'Century Gothic', 'Futura', sans-serif` as a web-safe approximation), standard clean sans-serif for body text
- No `<html>`, `<head>`, or `<body>` tags — this is a block to paste into an existing Squarespace page, not a full document
- No fabricated metrics — use `[METRIC NEEDED: description]` placeholders if source files don't specify exact numbers

## Output Format

Deliver as a single HTML code block, ready to copy-paste into a Squarespace Code Block element. Include a one-line comment at the top noting which concept and which mode (A or B) this is.

## Consistency Check (do this before finishing)

- [ ] Colors/typography match CLAUDE.md's Design Style Guide and other case study pages exactly
- [ ] Structural components used (breadcrumb headers, section dividers, KPI stat blocks, four-column framework, callout boxes, persona cards) match the PDF style, not a generic layout
- [ ] Phase language matches slide-builder output (Research/Ideation/Prototyping/Testing/Handoff)
- [ ] Key Insight / Design Rationale section is visually prominent, not buried
- [ ] Responsive behavior included
- [ ] No fabricated metrics
- [ ] Visual placeholders marked clearly
