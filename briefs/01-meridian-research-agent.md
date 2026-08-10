# Epic 1 — Meridian Research Agent
*(Anonymized composite of real BlackRock work)*

Part of the AI UX portfolio (5 case studies). See `../case-study-requirements.md` for the index of all five, `../case-study-concepts.md` for the original pitch, and `../ai-ux-process-framework.md` for the shared Who/What/When/Why/How template and stage framework this follows. Full narrative build-out: [`01-meridian-research-agent-discovery.md`](01-meridian-research-agent-discovery.md).

**Naming approach:** based on real BlackRock/Aladdin work but uses a fictional client and platform name, since BlackRock is your current employer — **"Anchorpoint Capital"** and its internal platform **"Meridian"**, standing in for the real enterprise investment-operations context.

---

**WHO**
- Primary persona: Investment operations analyst / accounting ops user at Anchorpoint Capital, mid-to-senior level, handles research/investigation tasks as a recurring part of their workflow
- Secondary: Team lead who reviews escalated or high-stakes findings
- Stakeholders: Platform product owner, data/quant team supplying underlying research data, compliance (findings must be auditable)

**WHAT**
- Problem: Analysts manually pull data from multiple internal systems to answer a research question or investigate a discrepancy — slow, repetitive, and inconsistent in quality depending on who does it
- Proposed solution: A conversational research agent embedded in the platform. Analyst asks a question in natural language; agent retrieves from connected internal data sources, synthesizes an answer, and cites exactly where each piece came from

**WHEN**
- Triggered ad hoc, whenever an analyst needs to investigate something — no fixed schedule, this is a pull interaction
- Roadmap horizon: concept validated with real usage data (45 min/workflow saved) — positioned as a shipped v1 with a v2 backlog

**WHY**
- Business goal: reduce time-to-resolution on research/investigation tasks across a high-volume operations team
- User goal: get a trustworthy answer fast, without hopping across five systems
- Success metric (real, from your resume): ~45 minutes saved in investigation time per workflow
- Secondary metric candidates: agent-answer acceptance rate, escalation-to-human rate, repeat-question rate (signal the agent didn't fully answer)

**HOW**
- Design approach: Design Thinking + AI-specific validation (confidence in answers, source transparency) — interviews with analysts to map the manual research workflow before designing the agent's response structure
- Key interaction patterns: query input, cited/sourced answer format, confidence/certainty signal, "show your work" expand-to-source, fallback behavior when the agent can't find a confident answer
- Trust design: the core design challenge is getting a skeptical, detail-oriented ops user to *act* on an AI answer — walk through how citations and source traceability were used to earn that trust

**User story**
> As an investment operations analyst, I want to ask a research question in plain language and get a sourced, synthesized answer, so that I don't have to manually cross-reference multiple systems for routine investigations.

**Acceptance criteria (draft)**
- Every agent answer displays its source(s) and lets the user drill into the underlying record
- Agent clearly distinguishes a confident answer from a partial/uncertain one
- User can flag an incorrect or incomplete answer, and that feedback is visibly acknowledged
- Time-to-answer is measurably faster than the prior manual workflow (baseline to be captured before/after)

**Out of scope / open questions**
- Not building the underlying retrieval/LLM infrastructure — this is a UX/interaction case study, not a technical one
- Open: how much real UI detail can be shown vs. described, given the anonymization
