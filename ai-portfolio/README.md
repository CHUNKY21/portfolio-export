# AI Portfolio Subsection — Five AI-Native UX Concepts

**Part of:** Portfolio Export (Main Container)  
**Location:** `portfolio-export/ai-portfolio/`  
**Contains:** 5 individual AI-integrated product design projects

---

## 📂 Contents

This subsection contains **five AI-based UX case studies**, each demonstrating the AI-Enhanced UX process applied to real or speculative projects in financial services:

| Project | Folder | Type | Status |
|---------|--------|------|--------|
| **01. Meridian Research Agent** | `01-meridian-research-agent/` | Real, shipped v1 | ✅ Complete |
| **02. Meridian Exception Manager** | `02-meridian-exception-manager/` | Real, shipped v1 | ✅ Complete |
| **03. AI Pattern Library** | `03-ai-pattern-library/` | Design system | ✅ Complete |
| **04. Compliance Co-Pilot** | `04-compliance-copilot/` | Speculative concept | ✅ Complete |
| **05. Connected Vehicle Assistant** | `05-connected-vehicle-assistant/` | Speculative concept | ✅ Complete |

---

## 🎯 AI Portfolio Purpose

The AI Portfolio subsection groups these 5 projects under a **common theme**: Using Claude and Claude Code to demonstrate AI-Enhanced UX workflows in financial services contexts.

**Shared characteristics across all 5:**
- All leverage conversational AI / agents
- All show real or well-grounded speculative research
- All demonstrate the five-phase AI-Enhanced UX process
- All emphasize **human judgment over AI automation**

---

## 🗂️ Subsection Structure

```
ai-portfolio/
├── README.md                    ← You are here (subsection navigation)
├── CLAUDE.md                    ← Subsection-specific guidance
├── design-system/               ← Shared design system for these 5 projects
│
├── 01-meridian-research-agent/
│   ├── README.md               ← Project 1 navigation
│   ├── CLAUDE.md               ← Project 1 guidance
│   └── design-system/          ← Project 1 design system (independent)
│
├── 02-meridian-exception-manager/
│   ├── README.md
│   ├── CLAUDE.md
│   └── design-system/
│
├── 03-ai-pattern-library/
│   ├── README.md
│   ├── CLAUDE.md
│   └── design-system/
│
├── 04-compliance-copilot/
│   ├── README.md
│   ├── CLAUDE.md
│   └── design-system/
│
└── 05-connected-vehicle-assistant/
    ├── README.md
    ├── CLAUDE.md
    └── design-system/
```

---

## 📚 What's Where

### Shared Content (At Container Level)
These resources apply to **all 5 projects** and are centralized for maintainability:

**Briefs & Discovery**
- Location: `portfolio-export/briefs/`
- Contains: All research, narratives, wireframes, and slide content
- Access: Each project folder references its corresponding briefs

**Rendered Web Pages**
- Location: `portfolio-export/site/`
- Contains: All HTML landing page + 5 case study detail pages
- Access: Each project folder references its corresponding site pages

### Per-Project Resources
Each of the 5 project folders contains:

**Project Guidance**
- `CLAUDE.md` — Project-specific instructions for deliverables
- `README.md` — Project overview & navigation

**Project Design System**
- `design-system/` folder with project-specific design tokens and specifications
- **Independence:** Each project has its own design system (does not inherit from container or subsection)

---

## 🎨 Design System Hierarchy

### Level 1: Container Design System
**Location:** `portfolio-export/design-system/`  
**Applies to:** Entire portfolio (container-level design tokens & components)

### Level 2: AI Portfolio Design System (This Level)
**Location:** `ai-portfolio/design-system/`  
**Applies to:** These 5 AI projects collectively  
**Independence:** Separate from container design system

### Level 3: Individual Project Design Systems
**Locations:** `01-*/design-system/`, `02-*/design-system/`, etc.  
**Applies to:** Specific project  
**Independence:** Each project has unique design rules

---

## 🚀 Quick Start

### Navigate to a Specific Project
```
ai-portfolio/
├── 01-meridian-research-agent/README.md
├── 02-meridian-exception-manager/README.md
├── 03-ai-pattern-library/README.md
├── 04-compliance-copilot/README.md
└── 05-connected-vehicle-assistant/README.md
```

Click on any project's `README.md` for:
- Project overview & context
- Design system location
- Brief and web page references
- Status and next steps

### View Briefs & Web Pages
- **All briefs:** `portfolio-export/briefs/`
- **All web pages:** `portfolio-export/site/`

Each brief and page is named with the concept number (01-, 02-, etc.) for easy matching.

### Access Design Systems
- **This subsection's shared design system:** `ai-portfolio/design-system/`
- **Project-specific design systems:** `ai-portfolio/NN-project-name/design-system/`

---

## 📝 Project Summaries

### 01. Meridian Research Agent
**Status:** Real, shipped v1  
**Context:** Anchorpoint Capital investment operations platform  
**Challenge:** Analysts manually cross-reference 4-5 systems per research question  
**Solution:** Conversational agent retrieves, synthesizes, and cites answers with confidence scores  
**Key Insight:** Citations aren't a feature; they're the answer itself.

### 02. Meridian Exception Manager
**Status:** Real, shipped v1  
**Context:** Anchorpoint Capital investment operations workflow  
**Challenge:** Flat queue of exceptions with no prioritization or routing  
**Solution:** AI layer detects, prioritizes, and proposes remediation for operational exceptions  
**Key Insight:** Ambient AI that surfaces what to do next, not what went wrong.

### 03. AI Pattern Library
**Status:** Design system  
**Context:** Component library for AI-native product design  
**Challenge:** How do you design for AI states (thinking, uncertain, confident)?  
**Solution:** Reusable patterns for loading, confidence signals, error recovery, and human handoff  
**Key Insight:** AI UX is as much about communicating uncertainty as showing results.

### 04. Compliance Co-Pilot
**Status:** Speculative concept  
**Context:** Credit Suisse Outside Business Interests (OBI) review workflow  
**Challenge:** Manual step-by-step review with no visibility into pipeline or reasoning  
**Solution:** Three specialized agents (research, policy-check, escalation) with visible activity trail  
**Key Insight:** When multiple agents act on one case, the UX problem shifts from "is the AI right?" to "can the user tell who did what and why?"

### 05. Connected Vehicle Assistant
**Status:** Speculative concept  
**Context:** Automotive context (push/ambient AI in consumer product)  
**Challenge:** Drivers need proactive support without taking their attention from the road  
**Solution:** Ambient AI assistant that surfaces insights contextually without interruption  
**Key Insight:** Push AI works when it's high-confidence, relevant, and respectful of attention.

---

## 🔗 Cross-References

### From Container Level
To access this subsection:  
→ See `ai-portfolio/README.md` (this file)  
→ See `ai-portfolio/CLAUDE.md` for subsection-specific guidance  
→ Enter any project folder for project-specific info  

### From Individual Project Level
To access the subsection:  
→ See `../README.md` (parent folder)  
→ See `../CLAUDE.md` for subsection-specific guidance  

To access container:  
→ See `../../../README.md`  
→ See `../../../CLAUDE.md` for main container guidance  

---

## 📌 Key Principles

### AI-Enhanced UX Process
All 5 projects demonstrate the five-phase model:
1. **Research** — AI synthesis of interviews & data (2-5 days)
2. **Ideation** — AI co-design of concepts (3-5 days)
3. **Prototyping** — AI-generated wireframes & interactions (5-10 days)
4. **Testing** — AI analysis of feedback (1-2 weeks)
5. **Handoff** — Auto-documented specs (2-3 days)

### Human Judgment is Non-Negotiable
Every case study includes a moment where human judgment made a call the AI couldn't. This is what separates the portfolio from generic AI automation narratives.

### Design Rationale is the Story
Each project surfaces **why** Michael made specific choices, not just **what** shipped. This demonstrates strategic thinking and tradeoff analysis.

---

## 👤 Contact

**Michael Thibodeau**  
Email: michaelthbd@yahoo.com  
Website: michaeljthibodeau.com  
Phone: 646.436.2876

---

**Last updated:** 2026-08-10  
**Status:** All 5 projects complete and ready for review
