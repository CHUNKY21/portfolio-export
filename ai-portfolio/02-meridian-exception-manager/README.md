# Project 02: Meridian Exception Manager

**Status:** ✅ Real, shipped v1  
**Client:** Anchorpoint Capital / Meridian  
**Role:** Led design process from discovery through shipped experience  
**Type:** Push/Ambient AI concept  
**Phase:** AI-Enhanced UX (Research → Ideation → Prototyping → Testing → Handoff)

---

## 📋 Quick Overview

### The Problem
Operational exceptions arrived as a flat queue with no prioritization, routing, or context. Analysts spent time manually sorting and categorizing before investigation.

### The Solution
An AI layer that detects, prioritizes, and proposes remediation for operational exceptions — presenting them as an actionable worklist instead of a flat queue.

### The Impact
- ~40% time saved in exception triage workflow (estimated)
- Multi-step exceptions routed to appropriate analysts automatically
- Clear remediation proposals with confidence scores
- Ambient AI that surfaces what to do next

### The Key Insight
**"Push AI works when it surfaces what to do next (the proposal) without requiring an explanation of what went wrong. The goal is action, not education."**

---

## 🗂️ Project Structure

```
02-meridian-exception-manager/
├── README.md                    ← You are here
├── CLAUDE.md                    ← Project-specific guidance
└── design-system/               ← Project design system (independent)
```

### Referenced from Container
- **Brief:** `briefs/02-meridian-exception-manager.md`
- **Discovery:** `briefs/02-meridian-exception-manager-discovery.md`
- **Wireframes:** `briefs/02-meridian-exception-manager-wireframes.md`
- **Web Page:** `site/02-meridian-exception-manager.html`

---

## 🎯 Project Guidance

See **`CLAUDE.md`** in this folder for project-specific instructions on creating deliverables (slides, web pages, wireframes) for this concept.

---

## 🎨 Design System

This project has its own **independent design system** in the `design-system/` folder.

**Design System Purpose:** Project-specific color palette, typography, spacing, and component specs.

**Independence:** Does not inherit from container or subsection design systems.

---

## 📚 Content Map

### Research & Discovery
**File:** `briefs/02-meridian-exception-manager-discovery.md`
- Analyst workflows and pain points
- Supporting research on exception handling
- Timeline & project plan

### Case Study Brief
**File:** `briefs/02-meridian-exception-manager.md`
- UX Story (Who/What/When/Why/How)
- Strategy & Tactics
- Solution overview
- Design Rationale

### Wireframe Descriptions
**File:** `briefs/02-meridian-exception-manager-wireframes.md`
- Exception list view (prioritized & routed)
- Exception detail view (with AI proposals)
- Remediation confirmation flow
- Interaction patterns

### Web Case Study
**File:** `site/02-meridian-exception-manager.html`
- Full interactive case study detail page
- All 10 sections
- Responsive design

---

## 🔍 Process Overview

### Phase 1: Research (AI-Synthesized)
- Analyzed 6+ months of exception logs
- Interviewed analysts on triage workflows
- Extracted decision patterns from historical data
- Timeline: 2-5 days

### Phase 2: Ideation (AI Co-Design)
- Designed push notification vs. worklist patterns
- Explored confidence-score presentation
- Iterated on proposal clarity vs. brevity
- Timeline: 3-5 days

### Phase 3: Prototyping (AI-Generated)
- Generated exception list & detail screens
- Designed AI proposal cards
- Built interactive prototypes
- Timeline: 5-10 days

### Phase 4: Testing (AI-Analyzed)
- Tested with real analysts
- Measured time-to-action improvements
- Analyzed override patterns (feedback signals)
- Timeline: 1-2 weeks

### Phase 5: Handoff (Auto-Documented)
- Generated specs and interaction documentation
- Created exception handling playbooks
- Handed off with confidence scoring logic
- Timeline: 2-3 days

---

## 🎯 Design Rationale Highlights

### Why Worklist Over Notifications
Push notifications interrupt. A ranked worklist lets analysts batch exceptions and control their workflow. AI does the ranking; humans do the action.

### Why Proposals Over Flags
Instead of flagging exceptions and making analysts figure out remediation, the AI proposes the fix. This shifts the UX from "diagnosis mode" to "action mode."

### Why Confidence Scores Matter
Analysts need to know when to override. Confidence scores make the AI's certainty visible, enabling smarter human judgment about which exceptions need investigation.

---

## 🔗 Navigation

**Back to AI Portfolio:** See `../README.md`  
**Back to Container:** See `../../README.md`  

---

## 📋 Project Checklist

- [x] Brief created
- [x] Discovery documented
- [x] Wireframes described
- [x] Web page built
- [x] Design system created
- [x] Project README created (you are here)
- [ ] Project CLAUDE.md created (next step)

---

**Last updated:** 2026-08-10  
**Status:** ✅ Ready for use
