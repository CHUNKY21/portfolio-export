# Project 01: Meridian Research Agent

**Status:** ✅ Real, shipped v1  
**Client:** Anchorpoint Capital / Meridian  
**Role:** Led design process from discovery through shipped experience  
**Phase:** AI-Enhanced UX (Research → Ideation → Prototyping → Testing → Handoff)

---

## 📋 Quick Overview

### The Problem
Investment operations analysts used to manually cross-reference 4-5 systems to answer a single research question. No consistent workflow, no auditable answers.

### The Solution
A conversational research agent embedded in Meridian that retrieves, synthesizes, and cites answers to plain-language research questions with confidence signals.

### The Impact
- ~45 minutes saved per investigation workflow (real, measured)
- ~82% answer acceptance rate (estimated)
- ~12% escalation rate (healthy signal)
- ~6% repeat-question rate (estimated)

### The Key Insight
**"The core design challenge wasn't making the agent accurate — it was getting a skeptical, detail-oriented analyst to actually act on an AI answer. Citations weren't an add-on; the citation was part of the answer."**

---

## 🗂️ Project Structure

```
01-meridian-research-agent/
├── README.md                    ← You are here
├── CLAUDE.md                    ← Project-specific guidance
└── design-system/               ← Project design system (independent)
```

### Referenced from Container
- **Brief:** `briefs/01-meridian-research-agent.md`
- **Discovery:** `briefs/01-meridian-research-agent-discovery.md`
- **Wireframes:** `briefs/01-meridian-research-agent-wireframes.md`
- **Web Page:** `site/01-meridian-research-agent.html`

---

## 🎯 Project Guidance

See **`CLAUDE.md`** in this folder for project-specific instructions on creating deliverables (slides, web pages, wireframes) for this concept.

---

## 🎨 Design System

This project has its own **independent design system** in the `design-system/` folder.

**Design System Purpose:** Project-specific color palette, typography, spacing, and component specs.

**Independence:** Does not inherit from container or subsection design systems. This project's design rules stand alone.

**When to use:** When building project-specific UI, components, or marketing materials that need unique visual language.

---

## 📚 Content Map

### Research & Discovery
**File:** `briefs/01-meridian-research-agent-discovery.md`
- Pain points from analyst interviews
- Supporting research & timeline
- Project plan & process

### Case Study Brief
**File:** `briefs/01-meridian-research-agent.md`
- UX Story (Who/What/When/Why/How)
- Strategy & Tactics
- Solution overview
- Design Rationale (the differentiator)

### Wireframe Descriptions
**File:** `briefs/01-meridian-research-agent-wireframes.md`
- Screen-by-screen descriptions
- UI element specs (query input, answer view, source expand, etc.)
- Interaction flow

### Slide Deck Content
**File:** `briefs/01-meridian-research-agent-slides.md`
- 1. Cover: Project title, tagline, quote
- 2. Introduction: What's the agent? Target audience, problems, role
- 3. Discovery & Research: KPI stats, discovery methods
- 4. Pain Points: Numbered list + supporting quote
- 5. Persona: Investment operations analyst card
- 6. Pain Points → Business Goals → UX Strategy → Feature Set (four-column framework)
- 7. Design/Process: Sprints & iterations with callout boxes
- 8. Results: KPI stats
- 9. Key Insight: Design rationale

### Web Case Study
**File:** `site/01-meridian-research-agent.html`
- Full interactive case study detail page
- All 10 sections (hero, intro, discovery, pain points, persona, framework, design, results, insight, CTA)
- Responsive design (desktop, tablet, mobile)

---

## 🔍 Process Overview

### Phase 1: Research (AI-Synthesized)
- Conducted interviews with investment operations analysts across experience levels
- Mapped the manual research workflow step-by-step to identify time sinks
- Extracted recurring decision patterns from real workflows
- Timeline: 2-5 days (accelerated via Claude analysis)

### Phase 2: Ideation (AI Co-Design)
- Brainstormed agent behavior concepts and interaction patterns
- Explored how to signal confidence and manage uncertainty
- Iterated on the "show sources by default" principle
- Timeline: 3-5 days (Claude and human designers working in parallel)

### Phase 3: Prototyping (AI-Generated)
- Generated wireframes and interaction flows
- Designed the "answer view" and "source expand" screens
- Built clickable prototypes for testing
- Timeline: 5-10 days

### Phase 4: Testing (AI-Analyzed)
- Ran usability testing with real analysts (happy path + failure scenarios)
- Watched whether analysts verified sources unprompted
- Analyzed feedback patterns and generated insights via Claude
- **Key Finding:** Analysts trusted the agent MORE when confidence was shown on every answer, not just low-confidence cases
- Timeline: 1-2 weeks

### Phase 5: Handoff (Auto-Documented)
- Generated specs from Claude analysis of test sessions
- Created final wireframes and interaction documentation
- Handed off to development with audit trail visible
- Timeline: 2-3 days

---

## 🎯 Design Rationale Highlights

### Why Citations Over Confidence Scores
Early versions surfaced confidence only when the agent flagged low confidence itself. Testing revealed analysts trusted the agent *more* when confidence was shown on every answer — it proved the agent was reasoning, not just returning cached results.

### Why Not Just a Search Tool
Manual step-by-step searches took as long as complex investigations because analysts spent time verifying sources. By baking verification into the answer format, we collapsed time across all query types.

### Why Plain Language Input
Analysts used different terminology and mental models. Plain language input (instead of structured forms) let each analyst ask in their own words, reducing cognitive load.

---

## 🔗 Navigation

**Back to AI Portfolio:** See `../README.md`  
**Back to Container:** See `../../README.md`  
**Container Guidance:** See `../../CLAUDE.md`  
**Subsection Guidance:** See `../CLAUDE.md`  
**Project Guidance:** See `CLAUDE.md` (this folder)  

---

## 📋 Project Checklist

- [x] Brief created (`01-meridian-research-agent.md`)
- [x] Discovery documented (`01-meridian-research-agent-discovery.md`)
- [x] Wireframes described (`01-meridian-research-agent-wireframes.md`)
- [x] Slide content written (`01-meridian-research-agent-slides.md`)
- [x] Web page built (`01-meridian-research-agent.html`)
- [x] Design system created
- [x] Project README created (you are here)
- [ ] Project CLAUDE.md created (next step)

---

## 👤 Project Contact

**Michael Thibodeau**  
Email: michaelthbd@yahoo.com  

**Questions?** See `CLAUDE.md` for project-specific guidance.

---

**Last updated:** 2026-08-10  
**Status:** ✅ Ready for use
