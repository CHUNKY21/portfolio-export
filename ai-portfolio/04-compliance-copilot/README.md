# Project 04: Compliance Co-Pilot

**Status:** ✅ Speculative concept  
**Client:** Credit Suisse (extends real OBI case study)  
**Role:** Concept design & vision piece  
**Type:** Multi-agent compliance workflow  
**Phase:** AI-Enhanced UX (Research → Ideation → Prototyping → Testing → Handoff)

---

## 📋 Quick Overview

### The Problem
Manual submission review with no visibility into the pipeline. Submissions returned for missing info with no clear explanation. No consolidated view of submitter's disclosure history.

### The Solution
Three specialized agents (research, policy-check, escalation) handle parts of submission review instead of purely manual step-by-step processing. Every action is visible on a timestamped activity trail.

### The Impact
- ~30% faster review cycle (target)
- ~50% fewer missing-info returns (target)
- ≥80% reviewer trust target
- Full audit trail for compliance

### The Key Insight
**"When more than one agent can act on a case, the UX problem shifts from 'is the AI right' to 'can the user tell who did what and why.' The activity trail isn't a feature bolted onto the workflow — it's the design's answer to that question."**

---

## 🗂️ Project Structure

```
04-compliance-copilot/
├── README.md                    ← You are here
├── CLAUDE.md                    ← Project-specific guidance
└── design-system/               ← Project design system (independent)
```

### Referenced from Container
- **Brief:** `briefs/04-compliance-copilot.md`
- **Discovery:** `briefs/04-compliance-copilot-discovery.md`
- **Wireframes:** `briefs/04-compliance-copilot-wireframes.md`
- **Web Page:** `site/04-compliance-copilot.html`

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
**File:** `briefs/04-compliance-copilot-discovery.md`
- Real OBI case study background
- Compliance officer workflows and challenges
- Supporting research on multi-agent trust
- Timeline & concept plan

### Case Study Brief
**File:** `briefs/04-compliance-copilot.md`
- UX Story (Who/What/When/Why/How)
- Multi-agent architecture (research, policy-check, escalation agents)
- Strategy & Tactics
- Design Rationale

### Wireframe Descriptions
**File:** `briefs/04-compliance-copilot-wireframes.md`
- Submission detail view with agent activity trail
- Policy conflict drill-down screen
- Agent decision explanations
- Override & logging flows

### Web Case Study
**File:** `site/04-compliance-copilot.html`
- Full interactive case study detail page
- All 10 sections
- Responsive design

---

## 🔍 Concept Architecture

### Three Specialized Agents

#### 1. Research Agent
- Gathers context about the submitter
- Pulls disclosure history
- Surfaces relevant precedents
- Highlights any red flags

#### 2. Policy-Check Agent
- Analyzes submission against policies
- Flags conflicts or ambiguities
- Suggests policy interpretations
- Proposes remediation actions

#### 3. Escalation Agent
- Routes submissions to appropriate reviewers
- Prioritizes based on complexity & risk
- Handles escalations for edge cases
- Manages queue assignments

### Visibility Through Activity Trail
Every agent's action is logged:
- What did the agent do?
- When did it happen?
- What reasoning did it use?
- What did the human decide?

This creates an **audit trail** that satisfies compliance requirements while building reviewer trust.

---

## 🎯 Design Rationale Highlights

### Why Three Agents Instead of One
A single agent trying to do research + policy-check + routing gets confused about priorities. Specialization makes each agent more accurate and reasoning more transparent.

### Why Activity Trail is Critical
When multiple agents can touch one case, reviewers need to understand who did what and why. The activity trail isn't a nice-to-have logging feature — it's the UX solution to the trust problem.

### Why Agent Proposes, Human Confirms
The agents never execute final decisions. They research, analyze, and propose. Humans always confirm. This keeps compliance authority where it belongs.

### Why This Extends the Real OBI Case Study
Michael's real Credit Suisse OBI work was purely manual. This concept explores the next evolution: how would you redesign that workflow if agents could help?

---

## 🔍 Process Overview (Concept Phase)

### Phase 1: Research (AI-Synthesized)
- Analyzed real OBI case study from prior engagement
- Researched multi-agent AI architectures
- Studied compliance officer trust factors
- Timeline: 2-5 days

### Phase 2: Ideation (AI Co-Design)
- Designed three-agent architecture
- Explored activity trail patterns
- Iterated on agent transparency approaches
- Debated one agent vs. multiple agents
- Timeline: 3-5 days

### Phase 3: Prototyping (AI-Generated)
- Generated wireframes for submission workflow
- Designed activity trail UI
- Built policy conflict screen
- Created agent decision cards
- Timeline: 5-10 days

### Phase 4: Concept Refinement
- Validated design approach with stakeholders
- Refined agent role definitions
- Clarified escalation logic
- **Note:** Not yet user-tested; this is a vision piece
- Timeline: 1-2 weeks

### Phase 5: Documentation (Auto-Documented)
- Generated concept specs
- Documented agent roles & responsibilities
- Created architecture diagrams
- Handed off as a vision brief (not a shipped product)
- Timeline: 2-3 days

---

## 📌 Important Note

**This is a speculative concept, not a shipped product.** It extends Michael's real Credit Suisse OBI case study into a forward-looking vision of what a multi-agent compliance workflow could look like. No user testing results are fabricated or claimed.

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
