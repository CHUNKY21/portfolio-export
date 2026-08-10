# Portfolio Export — UX/AI Portfolio Project

**Author:** Michael Thibodeau  
**Email:** michaelthbd@yahoo.com  
**Website:** michaeljthibodeau.com

---

## 🎯 Project Overview

A UX/AI portfolio for job applications in UX and AI-integrated product design roles, built on 15+ years in financial services (Wells Fargo, Credit Suisse, UBS, American Express, ADP, E*Trade).

The portfolio demonstrates the **AI-Enhanced UX Process**: Research → Ideation → Prototyping → Testing → Handoff, delivered in 1.5-2 months instead of traditional 4-6 months.

---

## 📂 Folder Structure

### Top-Level Organization

```
portfolio-export/
├── README.md                    ← You are here
├── CLAUDE.md                    ← Main project guidance
├── design-system/               ← Container design system
├── docs/                        ← General documentation
├── briefs/                      ← All case study briefs (5 concepts)
├── site/                        ← All rendered web pages (5 concepts)
│
├── ai-portfolio/                ← Subsection: AI Portfolio (5 projects)
│   ├── README.md               ← Navigation for AI portfolio
│   ├── CLAUDE.md               ← AI portfolio specific guidance
│   ├── design-system/          ← AI portfolio shared design system
│   │
│   ├── 01-meridian-research-agent/       ← Individual Project 1
│   ├── 02-meridian-exception-manager/    ← Individual Project 2
│   ├── 03-ai-pattern-library/            ← Individual Project 3
│   ├── 04-compliance-copilot/            ← Individual Project 4
│   └── 05-connected-vehicle-assistant/   ← Individual Project 5
│
└── (identity/, skills/, etc.)
```

---

## 🗂️ Content Organization

### Case Study Briefs & Discovery
**Location:** `briefs/`

All case study research and narrative:
- `NN-concept-name.md` — Brief (UX Story, Strategy, Tactics, Solution, Design Rationale)
- `NN-concept-name-discovery.md` — Discovery (Pain Points, Research, Timeline, Project Plan)
- `NN-concept-name-wireframes.md` — Wireframe descriptions
- `NN-concept-name-slides.md` — Slide deck content

**Access:** Read briefs at the container level; each individual project folder references its corresponding briefs.

### Rendered Web Pages & Case Study Sites
**Location:** `site/`

All HTML pages for web delivery:
- `index.html` — Landing page with 5 case study cards
- `01-meridian-research-agent.html` through `05-connected-vehicle-assistant.html` — Individual case study detail pages

**Access:** Each project folder can reference its corresponding site page.

---

## 🎨 Design Systems (Three Levels)

### Level 1: Container Design System
**Location:** `design-system/` (top-level)

**Purpose:** Shared design tokens and specifications for the entire portfolio.

**Files:**
- `tokens.css` — Centralized CSS custom properties
- `design-system.md` — PDF deck design spec (Figma build guide)
- `design-system-web.md` — Website design spec
- `components-web.html` — Component library for web pages

**Use this when:** Building portfolio-wide components or establishing baseline visual standards.

---

### Level 2: AI Portfolio Design System
**Location:** `ai-portfolio/design-system/`

**Purpose:** Shared design specifications specific to the 5 AI projects.

**Independence:** Has its own INDEPENDENT design rules (does not inherit from container).

**Use this when:** All 5 AI projects share specific design patterns or constraints different from the broader portfolio.

---

### Level 3: Individual Project Design Systems
**Locations:** `ai-portfolio/01-*/design-system/`, `ai-portfolio/02-*/design-system/`, etc.

**Purpose:** Project-specific design system (color palette, typography, spacing, components unique to that project).

**Independence:** Each project has its own INDEPENDENT design rules.

**Use this when:** A specific project needs unique visual language or component specs.

---

## 🚀 Quick Navigation

### For Project Managers & Stakeholders
- **Project overview:** Read `CLAUDE.md` (main container)
- **All briefs:** `briefs/` folder
- **Live pages:** `site/` folder
- **Status updates:** See `ai-portfolio/` for per-project details

### For Designers & Developers
- **Container design system:** `design-system/` folder
- **AI portfolio design system:** `ai-portfolio/design-system/` folder
- **Per-project design system:** `ai-portfolio/NN-project-name/design-system/` folder
- **Per-project guidance:** `ai-portfolio/NN-project-name/CLAUDE.md`

### For AI-Enhanced UX Process
- **Research phase:** `briefs/NN-*-discovery.md`
- **Ideation phase:** `briefs/NN-*-slides.md`
- **Prototyping & Testing:** See individual project folders
- **Handoff:** `site/NN-*.html` + `briefs/NN-*.md`

---

## 📋 Files by Purpose

### Documentation
- `CLAUDE.md` — Main project guidance (this container)
- `README.md` — Navigation & structure (you are here)
- `VALIDATION-SUMMARY.md` — Design system validation results
- `AUDIT-DESIGN-SYSTEM.md` — Audit of design system compliance
- `MIGRATION-QUICK-START.md` — Guide for migrating site pages to new design system
- `TYPOGRAPHY-CONSISTENCY-UPDATE.md` — Typography consolidation documentation

### Design System
- `design-system/` — Container-level design system
- `ai-portfolio/design-system/` — AI portfolio-level design system
- `ai-portfolio/01-*/design-system/` through `ai-portfolio/05-*/design-system/` — Project-level design systems

### Content
- `briefs/` — All case study briefs and discovery docs
- `site/` — All rendered web pages
- `docs/` — General documentation

---

## 🔗 Access & Navigation

### From Container Level
→ See **all projects** in the `ai-portfolio/` folder  
→ See **all briefs** in the `briefs/` folder  
→ See **all web pages** in the `site/` folder  

### From AI Portfolio Level
→ See **subsection overview** in `ai-portfolio/README.md`  
→ See **subsection guidance** in `ai-portfolio/CLAUDE.md`  
→ Access **5 individual projects** in numbered folders  

### From Individual Project Level
→ See **project overview** in `ai-portfolio/NN-*/README.md`  
→ See **project guidance** in `ai-portfolio/NN-*/CLAUDE.md`  
→ See **project design system** in `ai-portfolio/NN-*/design-system/`  
→ Reference **briefs** at `../../../briefs/NN-*`  
→ Reference **web pages** at `../../../site/NN-*`  

---

## 📌 Key Principles

### AI-Enhanced UX Process
Every deliverable is framed through the five-phase process model:
1. **Research** (2-5 days, AI-synthesized)
2. **Ideation** (3-5 days, AI co-design)
3. **Prototyping** (5-10 days, AI-generated)
4. **Testing** (1-2 weeks, AI-analyzed)
5. **Handoff** (2-3 days, auto-documented)

### Design Rationale is the Differentiator
Every case study surfaces the brief's **Design Rationale** section prominently. This shows tradeoffs Michael weighed, not just what shipped.

### AI Amplifies Human Judgment
Every case study includes a moment where a human (Michael or a persona) made a judgment call the AI couldn't make alone. This separates the portfolio from generic "I used AI" narratives.

---

## 👤 Contact

**Michael Thibodeau**  
Email: michaelthbd@yahoo.com  
Website: michaeljthibodeau.com  
Phone: 646.436.2876

---

**Last updated:** 2026-08-10  
**Status:** Structure established, ready for per-project development
