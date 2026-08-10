# Design System Hierarchy & Structure

**Date:** 2026-08-10  
**Status:** ✅ Container & AI Portfolio levels defined; Project levels ready for customization

---

## 📐 Three-Level Design System Architecture

```
portfolio-export/
│
├── LEVEL 1: Container Design System
│   └── design-system/
│       ├── tokens.css                    ← Centralized CSS custom properties
│       ├── design-system.md              ← PDF deck design spec (Figma)
│       ├── design-system-web.md          ← Website design spec
│       ├── components-web.html           ← Component library
│       ├── figma-tokens.json             ← Figma PDF tokens
│       └── figma-tokens-web.json         ← Figma web tokens
│
├── LEVEL 2: AI Portfolio Design System
│   └── ai-portfolio/design-system/
│       ├── README.md                     ← (To be created)
│       ├── CLAUDE.md                     ← (To be created)
│       ├── tokens.css                    ← (To be created)
│       ├── design-system.md              ← (To be created)
│       └── components.html               ← (To be created)
│
└── LEVEL 3: Individual Project Design Systems (5x)
    ├── 01-meridian-research-agent/design-system/
    │   ├── README.md
    │   ├── CLAUDE.md
    │   ├── tokens.css
    │   ├── design-system.md
    │   └── components.html
    │
    ├── 02-meridian-exception-manager/design-system/
    ├── 03-ai-pattern-library/design-system/
    ├── 04-compliance-copilot/design-system/
    └── 05-connected-vehicle-assistant/design-system/
```

---

## 🎯 LEVEL 1: Container Design System

**Location:** `/design-system/`  
**Status:** ✅ **COMPLETE**  
**Purpose:** Shared design tokens for entire portfolio

### Files Present

#### `tokens.css` ✅
Centralized CSS custom properties with:
- **40+ color tokens** (primary, secondary, framework colors, KPI accents, semantic colors, text colors, backgrounds)
- **Typography tokens** (font families, sizes, weights, line heights, letter spacing)
- **Spacing scale** (8px base unit: xs, sm, md, lg, xl, 2xl, 3xl)
- **Border radius** (sm, md, lg, full)
- **Shadows** (sm, md, lg — reserved for future interactive elements)
- **Layout tokens** (max-widths, padding, gaps)
- **Utility classes** (color gradients, text utilities, backgrounds)

**Current state:** All inferred values confirmed ✓ | H2 font changed to Poppins ✓

#### `design-system.md` ✅
PDF deck design specification (Figma build guide):
- Color styles (Brand, Accent, Neutral)
- Text styles (Display, Headings, Body, Labels)
- Spacing & grid
- Components to build
- Usage rules & warnings

**Current state:** All tokens confirmed | Typography standardized on Poppins ✓

#### `design-system-web.md` ✅
Website design specification:
- Color styles (web-specific palette)
- Typography (Poppins + web layout patterns)
- Layout patterns (navbar, hero, work grid, sidebar, footer)

**Current state:** All values confirmed | Typography standardized on Poppins ✓

#### `components-web.html` ✅
Component library with 8 working components:
1. Navbar
2. Hero gradient statement
3. Work grid
4. Case study sidebar nav
5. Section labels
6. Process steps
7. Flow diagram nodes
8. Footer bar

**Current state:** Poppins font updated | Responsive | CSS variables used ✓

#### `figma-tokens.json` & `figma-tokens-web.json` ✅
Figma token exports (for design handoff)

---

## 🎯 LEVEL 2: AI Portfolio Design System

**Location:** `/ai-portfolio/design-system/`  
**Status:** 🔄 **FOLDER CREATED, FILES TO BE ADDED**  
**Purpose:** Shared design system for the 5 AI projects (independent from container)

### Files to Create

#### `README.md` (To create)
Navigation & overview for the AI Portfolio design system

#### `CLAUDE.md` (To create)
Project guidance specific to AI portfolio design work

#### `tokens.css` (To create)
Tailored CSS tokens for AI portfolio projects:
- May reuse some container colors
- May introduce new colors specific to AI UX patterns
- Typography aligned with Poppins
- Spacing for AI-specific components (confidence scores, agent cards, etc.)

#### `design-system.md` (To create)
AI Portfolio design specification:
- Focus on AI UX patterns (loading states, confidence signals, error handling)
- Component specs for agent interactions
- Color palette for uncertainty/confidence indicators

#### `components.html` (To create)
Component library specific to AI portfolio:
- Confidence score indicators
- Loading states
- AI agent cards
- Source/citation patterns
- Handoff components

---

## 🎯 LEVEL 3: Individual Project Design Systems

**Locations:** 5x folders under `/ai-portfolio/`  
**Status:** 🔄 **FOLDERS CREATED, FILES TO BE ADDED**  
**Purpose:** Project-unique design tokens (completely independent)

### Example: Project 01 Structure

```
01-meridian-research-agent/design-system/
├── README.md                    ← Project design overview
├── CLAUDE.md                    ← Project design guidance
├── tokens.css                   ← Project-specific tokens
├── design-system.md             ← Project design spec
└── components.html              ← Project-specific components
```

### Files to Create (for each of 5 projects)

#### `README.md`
- Project design system overview
- Color philosophy
- Typography choices
- Component library guide

#### `CLAUDE.md`
- Project-specific design instructions
- Rationale for design decisions
- Constraints & considerations

#### `tokens.css`
Project-specific CSS variables:
- **Unique color palette** (e.g., Meridian Research: blues + teals for research themes)
- **Poppins typography** (consistent across all projects)
- **Project-specific spacing** (may differ based on layout needs)
- **Custom components** (e.g., citation patterns for research agent)

#### `design-system.md`
Complete design spec for the project:
- Color palette with usage rules
- Typography choices
- Component specifications
- Spacing & layout rules
- Design rationale

#### `components.html`
Project-specific component library:
- Unique components built for this project
- Examples: research card, confidence score display, source panel, etc.
- Interactive examples

---

## 🔍 Design System Independence

### What This Means

**Level 1 (Container):** Defines baseline design language  
**Level 2 (AI Portfolio):** Can override/extend container (independent)  
**Level 3 (Projects):** Complete freedom to define unique identity (independent)

### Example Scenarios

#### Scenario 1: Meridian Research Agent
- Uses **project-specific blue palette** (research theme)
- Uses **Poppins typography** (consistent across all)
- Defines **citation patterns** unique to this project
- Has **confidence score component** specific to research context

#### Scenario 2: AI Pattern Library
- Uses **multi-color palette** (showing different AI states)
- Uses **Poppins typography** (consistent across all)
- Defines **loading indicator patterns**
- Has **error state component** patterns

#### Scenario 3: Compliance Co-Pilot
- Uses **formal color palette** (compliance theme)
- Uses **Poppins typography** (consistent across all)
- Defines **agent activity trail** component
- Has **policy conflict** visual indicators

---

## ✅ Current Status

### Completed ✓
- [x] Container design system (6 files)
- [x] Container folder structure
- [x] AI Portfolio folder structure
- [x] All 5 project folders created
- [x] All 5 project README.md files created
- [x] Design system folders exist for all projects
- [x] Typography standardized to Poppins across all levels
- [x] All inferred values confirmed

### Ready for Development 🔄
- [ ] AI Portfolio design system (5 files to create)
- [ ] Project 01 design system (5 files to create)
- [ ] Project 02 design system (5 files to create)
- [ ] Project 03 design system (5 files to create)
- [ ] Project 04 design system (5 files to create)
- [ ] Project 05 design system (5 files to create)

---

## 📋 Next Steps

### For AI Portfolio Level (1-2 hours)
1. Create `/ai-portfolio/design-system/README.md` — Overview of shared design patterns
2. Create `/ai-portfolio/design-system/CLAUDE.md` — Guidance for AI portfolio design work
3. Create `/ai-portfolio/design-system/tokens.css` — Shared tokens for all 5 projects
4. Create `/ai-portfolio/design-system/design-system.md` — AI-specific design spec
5. Create `/ai-portfolio/design-system/components.html` — AI UX component library

### For Each Project Level (30 min per project = 2.5 hours total)
1. Determine project-specific color palette
2. Create `/project/design-system/README.md`
3. Create `/project/design-system/CLAUDE.md`
4. Create `/project/design-system/tokens.css` with unique colors
5. Create `/project/design-system/design-system.md` with full spec
6. Create `/project/design-system/components.html` with project components

---

## 🎨 Design Philosophy

### Container Level
**Purpose:** Define baseline visual language for entire portfolio  
**Audience:** All projects, all deliverables  
**Flexibility:** Foundational (colors, typography, spacing patterns)

### AI Portfolio Level
**Purpose:** Unified language for 5 AI-focused projects  
**Audience:** All 5 projects in this subsection  
**Flexibility:** Can introduce AI-specific patterns (confidence scores, loading states, agent cards)

### Project Level
**Purpose:** Unique visual identity for each project  
**Audience:** Single project  
**Flexibility:** Complete freedom (palette, components, special patterns)

---

## 📚 File Templates (Ready to Create)

### Template: `design-system/tokens.css`
```css
:root {
  /* ========== BRAND COLORS ========== */
  --color-primary: #XXX;
  --color-secondary: #XXX;
  
  /* ========== TYPOGRAPHY ========== */
  --font-family-body: 'Poppins', sans-serif;
  --font-size-h1: 28px;
  /* ... etc */
  
  /* ========== SPACING SCALE ========== */
  --space-xs: 4px;
  /* ... etc */
}
```

### Template: `design-system/design-system.md`
```markdown
# [Project Name] Design System

**Version:** 1.0  
**Date:** 2026-08-10  
**Type:** [Container | AI Portfolio | Project-specific]

## Color System
[Color palette table with hex values and usage rules]

## Typography
[Font families, sizes, weights, usage rules]

## Spacing Scale
[Spacing tokens and usage]

## Components
[Component specifications]

## Usage Rules
[Guidelines for applying the system]
```

---

**Total setup time:** ~4 hours (done ✓ at container level, 3.5 hours remaining for AI Portfolio + Projects)

**Status:** Architecture complete, ready for content creation.
