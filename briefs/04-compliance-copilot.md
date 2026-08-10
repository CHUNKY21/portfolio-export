# Epic 4 — Compliance Co-Pilot
*(Real client: Credit Suisse — extends the existing Outside Business Interests case study into a speculative multi-agent concept)*

Part of the AI UX portfolio (5 case studies). See `../case-study-requirements.md` for the index of all five, `../case-study-concepts.md` for the original pitch, and `../ai-ux-process-framework.md` for the shared Who/What/When/Why/How template and stage framework this follows.

---

**WHO**
- Primary persona: Risk & Compliance manager and Submitter/Employee personas, same as the existing OBI case study
- Secondary: Approver persona
- Stakeholders: compliance/legal (accuracy and auditability are non-negotiable here), risk management

**WHAT**
- Problem: a single submission (e.g., an outside business interest disclosure) today gets manually routed and reviewed step by step, with no visibility into why it's at a given stage or what's being checked
- Proposed solution (concept): a multi-agent system where a research agent gathers relevant context, a policy/compliance-check agent flags rule conflicts, and an escalation agent routes to the right human reviewer — with the UI always showing which agent acted, what it did, and why

**WHEN**
- Triggered whenever a submission enters the OBI-style workflow; each agent activates at its stage in the pipeline (detection → review & analysis → escalation → remediation, the same stages as your existing OBI case study)
- Explicitly framed as speculative/concept, not shipped — dated and scoped as a vision extension of real work

**WHY**
- Business goal: faster, more consistent compliance review with a clear audit trail
- User goal: reviewers and submitters understand what's happening to their submission at every step, instead of it feeling like a black box
- Success metrics (concept-stage, framed as hypotheses to validate): reduction in review cycle time, reduction in submissions returned for missing information (a real pain point already documented in your existing OBI case study), reviewer trust/confidence rating

**HOW**
- Design approach: extend the real discovery findings from your existing Credit Suisse OBI case study (interviews with reviewers, risk & compliance managers) into the multi-agent concept — this case study should explicitly reference and build on that prior work, not start from zero
- Core design challenge: legibility of multi-agent handoffs — when more than one agent touches a submission, the user needs to know who/what acted at each step, not just "processing"
- Key interaction pattern: a visible agent-activity trail/timeline on the submission (e.g., "Research agent reviewed disclosure history — Policy agent flagged a potential conflict — Routed to [Approver] for review")

**User story**
> As a compliance reviewer, I want to see which agent took which action on a submission and why, so that I can trust the system's recommendation instead of treating it as a black box.

**Acceptance criteria (draft)**
- Every submission has a visible, timestamped trail of agent actions and the reasoning behind each
- Every agent-flagged conflict links to the specific policy/rule it's based on
- A human reviewer can override any agent action, and that override is logged
- Clearly labeled throughout as a concept/vision extension, not a shipped feature

**Out of scope / open questions**
- Not designing the compliance rules engine itself
- Open: how much to reuse actual visuals/structure from your existing OBI case study vs. building fresh concept screens
