# Project 05: Connected Vehicle Assistant

**Status:** ✅ Speculative concept  
**Context:** Automotive / Consumer product  
**Role:** Concept design for push/ambient AI  
**Type:** Push AI / Ambient intelligence  
**Phase:** AI-Enhanced UX (Research → Ideation → Prototyping → Testing → Handoff)

---

## 📋 Quick Overview

### The Problem
Drivers need proactive support (route optimization, maintenance alerts, fuel advice) but can't take their attention off the road. Push notifications interrupt; in-vehicle systems compete for attention.

### The Solution
An ambient AI assistant that surfaces insights contextually — at the right time, in the right modality — without interruption or cognitive load.

### The Impact
- Proactive support without interruption
- Reduced driver cognitive load
- Higher adoption than push notifications
- Safety-first design (never pulls attention from road)

### The Key Insight
**"Push AI works when it's high-confidence, relevant, and respectful of attention. The goal is to anticipate what the driver needs before they ask, not to interrupt with unnecessary alerts."**

---

## 🗂️ Project Structure

```
05-connected-vehicle-assistant/
├── README.md                    ← You are here
├── CLAUDE.md                    ← Project-specific guidance
└── design-system/               ← Project design system (independent)
```

### Referenced from Container
- **Brief:** `briefs/05-connected-vehicle-assistant.md`
- **Discovery:** `briefs/05-connected-vehicle-assistant-discovery.md`
- **Wireframes:** `briefs/05-connected-vehicle-assistant-wireframes.md`
- **Web Page:** `site/05-connected-vehicle-assistant.html`

---

## 🎯 Project Guidance

See **`CLAUDE.md`** in this folder for project-specific instructions on creating deliverables (slides, web pages, wireframes) for this concept.

---

## 🎨 Design System

This project has its own **independent design system** in the `design-system/` folder.

**Design System Purpose:** Project-specific design tokens and component specs for in-vehicle UI.

**Independence:** Does not inherit from container or subsection design systems.

---

## 📚 Content Map

### Research & Discovery
**File:** `briefs/05-connected-vehicle-assistant-discovery.md`
- Driver workflows and pain points
- Distraction/attention research
- Current in-vehicle UX patterns
- Safety considerations
- Timeline & project plan

### Case Study Brief
**File:** `briefs/05-connected-vehicle-assistant.md`
- UX Story (Who/What/When/Why/How)
- Push AI vs. pull AI comparison
- Strategy & Tactics
- Design Rationale

### Wireframe Descriptions
**File:** `briefs/05-connected-vehicle-assistant-wireframes.md`
- Ambient display patterns
- Context-aware information surfaces
- Interaction modalities (voice, haptic, visual)
- Safety constraints
- Information hierarchies

### Web Case Study
**File:** `site/05-connected-vehicle-assistant.html`
- Full interactive case study detail page
- All 10 sections
- Responsive design

---

## 🔍 Ambient AI Principles

### 1. Anticipation Over Reaction
The assistant predicts what the driver needs before they ask:
- Route changes based on real-time traffic
- Maintenance alerts before warning lights
- Fuel optimization for current driving patterns

### 2. Modality Matching
Different information channels for different urgency levels:
- **Visual:** Non-critical information (next destination reminder)
- **Haptic:** Medium urgency (fuel level optimization suggestion)
- **Voice:** High urgency (hazard alert, safety notice)
- **Never interrupts** with low-confidence predictions

### 3. High Confidence Only
Push AI only surfaces insights when confidence is high:
- Route change only if 80%+ time savings
- Maintenance alerts only if 90%+ confidence
- Never speculative or "maybe interesting" messages

### 4. Graceful Transparency
When the assistant acts, the driver understands why:
- "Optimized route saves ~8 minutes based on current traffic"
- "Service due soon: oil change recommended at next stop"
- "Updated fuel estimate: you can reach destination + 50 miles"

### 5. Always Optional
The driver can always override or disable:
- One-tap to dismiss suggestions
- Settings for urgency levels
- Quick disable during focused driving (red-light, highway merging)

---

## 🔍 Process Overview

### Phase 1: Research (AI-Synthesized)
- Analyzed driver attention patterns
- Researched in-vehicle UX best practices
- Studied push notification fatigue
- Reviewed safety guidelines
- Timeline: 2-5 days

### Phase 2: Ideation (AI Co-Design)
- Designed anticipation algorithms
- Explored modality matching approaches
- Debated confidence thresholds
- Prototyped information hierarchies
- Timeline: 3-5 days

### Phase 3: Prototyping (AI-Generated)
- Generated in-vehicle screen designs
- Created gesture/interaction flows
- Designed voice interaction patterns
- Built decision trees for information surfacing
- Timeline: 5-10 days

### Phase 4: Concept Refinement
- Validated design safety assumptions
- Refined confidence scoring logic
- Adjusted urgency modalities
- **Note:** Not yet real-world tested; this is a vision piece
- Timeline: 1-2 weeks

### Phase 5: Documentation (Auto-Documented)
- Generated concept specs
- Documented anticipation rules
- Created modality matrix
- Handed off as a vision brief
- Timeline: 2-3 days

---

## 🎯 Design Rationale Highlights

### Why Ambient Over Push
Push notifications fight for driver attention. Ambient surfaces information without interruption — it's there when the driver is ready for it.

### Why High Confidence Matters
In-vehicle AI failing is worse than not trying. A wrong route suggestion during a commute damages trust permanently. Only high-confidence predictions surface.

### Why Modality Matters
The same information can't be delivered the same way to a driver starting their morning vs. merging on the highway. Modality (voice, visual, haptic) adapts to context.

### Why This is Speculative
Connected vehicle tech is evolving rapidly. This concept explores the vision of AI-enhanced driving without claiming current feasibility. It's a north-star design.

---

## 📌 Important Note

**This is a speculative concept, not a shipped product.** It explores a vision of proactive, ambient AI in automotive contexts. The design is grounded in research but hasn't been tested in real vehicles.

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
**Status:** ✅ Concept complete and documented
