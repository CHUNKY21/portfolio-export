# AI UX Portfolio — Index

A 5-concept portfolio addition demonstrating AI-native UX work, built to sit alongside Michael's existing shipped-work deck (`ThibodeauCaseB2B26.pdf`). Start here, then branch out based on what you need.

## Compiled deliverables
- **[`AI-UX-Case-Studies.pdf`](AI-UX-Case-Studies.pdf)** — single 48-page deck, all 5 case studies in the order below, cover + TOC + closing slide. Source: [`AI-UX-Case-Studies-deck-source.html`](AI-UX-Case-Studies-deck-source.html) (edit and re-print to update).
- **[`site/index.html`](site/index.html)** — single multi-page site, landing grid → 5 linked detail pages. Open locally to browse; the underlying per-concept fragments in `briefs/*-card.html` / `briefs/*-detail.html` are the Squarespace-Code-Block-ready versions.
- **[AI UX Portfolio — Master Deck (Figma)](https://www.figma.com/design/gOraS9lJs0dhFJERUF5or2)** — the compiled deck above AND the real 80-page `ThibodeauCaseB2B26.pdf` deck, both rebuilt as real, editable Figma content across 2 pages.

## Read first
- [`CLAUDE.md`](CLAUDE.md) — project structure, working agreements, the Design Style Guide (colors, typography, structural components) pulled from the real deck, and the Figma file index
- [`ai-ux-process-framework.md`](ai-ux-process-framework.md) — the shared 8-stage process spine and Who/What/When/Why/How template every case study must follow

## Background
- [`case-study-concepts.md`](case-study-concepts.md) — the original pitch for all 5 concepts: what each demonstrates, why these four/five, and the open questions Michael still needs to answer
- [`case-study-requirements.md`](case-study-requirements.md) — index and build status of the 5 briefs

## The 5 case studies
All 5 are fully built out: discovery narrative → wireframes → 9-slide sequence → index card + detail page. Epic 4 additionally has real Figma product-screen mockups.

| # | Concept | Pattern | Status |
|---|---|---|---|
| 1 | [Meridian Research Agent](briefs/01-meridian-research-agent.md) → [full narrative](briefs/01-meridian-research-agent-discovery.md) | Conversational agent (pull) | Real, shipped v1 |
| 2 | [Meridian Exception Manager](briefs/02-meridian-exception-manager.md) → [full narrative](briefs/02-meridian-exception-manager-discovery.md) | Ambient/push AI | Real, shipped v1 (metrics are illustrative — no sourced figure exists) |
| 3 | [AI Pattern Library](briefs/03-ai-pattern-library.md) → [full narrative](briefs/03-ai-pattern-library-discovery.md) | Design system for AI states | Synthesis case study — real leadership, constructed narrative |
| 4 | [Compliance Co-Pilot](briefs/04-compliance-copilot.md) → [full narrative](briefs/04-compliance-copilot-discovery.md) | Multi-agent (concept) | Concept/speculative — has real Figma mockups |
| 5 | [Connected Vehicle Assistant](briefs/05-connected-vehicle-assistant.md) → [full narrative](briefs/05-connected-vehicle-assistant-discovery.md) | Multi-agent (concept) | Concept/speculative |

Every discovery doc, wireframe set, and slide deck is in `briefs/NN-concept-name-*.md`. Every metric/quote synthesized beyond what a brief or discovery doc literally states is labeled inline as illustrative/target — none should be read as a real measured result except Epic 1's real "~45 minutes saved."

## Turning a case study into a deliverable
Each skill below reads `CLAUDE.md` for style, then the brief (+ discovery file) for content:
- [`skills/wireframe-describer/`](skills/wireframe-describer/SKILL.md) — brief's WHAT/HOW → screen-by-screen wireframe descriptions
- [`skills/slide-builder/`](skills/slide-builder/SKILL.md) — brief + discovery → 9-slide sequence
- [`skills/web-page-builder/`](skills/web-page-builder/SKILL.md) — brief + discovery → Squarespace-ready HTML (index card + detail page)

## Mockups
- [Figma — Compliance Co-Pilot Concept Mockups](https://www.figma.com/design/T0c8hGDQUcZsbxPZZlayC2) — Epic 4's 4 screens, built with the sampled Design Style Guide palette.

## Identity & design systems (in progress)
Full brand identity (logo, palette, type, voice) for each of the 5 concepts, plus a real Figma component library for Epic 3's AI Pattern Library. See `CLAUDE.md`'s "Identity & Design Systems" section for the file index, and `identity/*-identity-log.md` for each concept's decisions and rationale.

## Next step
Drop real images into the `[IMAGE: ...]` placeholders in the Figma master deck's real-deck section; finish the in-progress identity programs; once identities exist, consider real Figma mockups for the other 4 concepts (only Epic 4 has them); measure Squarespace's actual column breakpoints before treating the web fragments as final.
