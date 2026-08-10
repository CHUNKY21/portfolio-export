# Epic 3 — AI Pattern Library (design system for AI states)
*(Synthesis case study — not tied to one employer; draws on design-system leadership at Wells Fargo, Credit Suisse, and BlackRock)*

Part of the AI UX portfolio (5 case studies). See `../case-study-requirements.md` for the index of all five, `../case-study-concepts.md` for the original pitch, and `../ai-ux-process-framework.md` for the shared Who/What/When/Why/How template and stage framework this follows.

---

**WHO**
- Primary persona: product designers across multiple teams who need to add an AI feature but only have a design system built for deterministic UI
- Secondary: design system governance team (you, in this role) responsible for consistency across products
- Stakeholders: engineering (component implementation), product leads (adoption), other design leads whose teams inherit the pattern set

**WHAT**
- Problem: standard design systems don't have components for AI-specific states — there's no established pattern for "here's a source citation," "here's how confident this answer is," "the response is still streaming in," "tell the AI it got this wrong"
- Proposed solution: a defined set of reusable AI UX components/patterns, documented and adopted across product teams, so every AI feature in the org speaks the same visual and interaction language

**WHEN**
- Not a single moment of use — this is infrastructure. Applies whenever any product team ships a new AI feature
- Roadmap framing: initial pattern set (v1) shipped and adopted by X teams, with a backlog of patterns still being defined as new AI use cases emerge

**WHY**
- Business goal: consistency and speed — product teams stop reinventing AI interaction patterns from scratch, and users get a predictable experience across products
- Design goal: prevent every team from independently (and inconsistently) solving "how do we show AI made a mistake" or "how do we show confidence"
- Success metrics: number of product teams adopting the pattern set, reduction in one-off/inconsistent AI UI patterns found in design review, designer time saved not re-solving solved problems

**HOW**
- Design approach: audit existing AI features shipped ad hoc across teams, identify the recurring unsolved problems, define and test a minimal component set, then run the same governance/adoption playbook you've already run for non-AI design systems (Wells Fargo, Credit Suisse)
- Component set to define (pick 4–6 for the case study): confidence/certainty indicator, citation/source card, streaming-response state, correction/feedback control, human-handoff banner, empty/no-answer state
- Core design challenge: governance and adoption, not just component design — the case study should walk through how you got competing product teams to actually use a shared pattern instead of shipping their own

**User story**
> As a product designer on any team shipping an AI feature, I want a documented set of AI interaction components already validated for trust and clarity, so that I don't have to solve "how do we show this is AI-generated and how confident it is" from scratch.

**Acceptance criteria (draft)**
- Each component has a defined use case, a "when NOT to use this" note, and an accessibility/WCAG pass
- At least 2-3 product teams shown adopting the same component (before/after comparison)
- Documentation lives in the same governance structure as the org's existing (non-AI) design system

**Out of scope / open questions**
- This case study is presentation-format-flexible — it could lean harder on the actual component specs/redlines than the other four, since that's the real deliverable of this kind of work
- Open: which 4-6 components make the strongest, most demoable set
