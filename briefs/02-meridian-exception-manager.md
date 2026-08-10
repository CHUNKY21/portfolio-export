# Epic 2 — Meridian Exception Manager
*(Anonymized composite of real BlackRock work — same platform as Epic 1, different interaction mode)*

Part of the AI UX portfolio (5 case studies). See `../case-study-requirements.md` for the index of all five, `../case-study-concepts.md` for the original pitch, and `../ai-ux-process-framework.md` for the shared Who/What/When/Why/How template and stage framework this follows.

**Naming approach:** based on real BlackRock/Aladdin work but uses the same fictional client and platform name as Epic 1 — **"Anchorpoint Capital"** / **"Meridian"** — since it's the same underlying platform, different product within it.

---

**WHO**
- Primary persona: same operations analyst as Epic 1, but now in a reactive/triage mode rather than an investigative one
- Secondary: Team lead who owns prioritization across the exception queue
- Stakeholders: Risk/compliance (some exceptions have regulatory implications), engineering teams whose systems generate the underlying breaks/mismatches

**WHAT**
- Problem: Operational exceptions (trade breaks, mismatches, failed reconciliations) surface today through queues and manual triage, so prioritization depends on tribal knowledge of "which ones actually matter"
- Proposed solution: An AI layer that detects, prioritizes, and proposes remediation for exceptions automatically, presenting them as a ranked, actionable worklist instead of a flat queue

**WHEN**
- System-initiated (push), continuous/ambient — the AI is always watching, not waiting to be asked
- This is the direct interaction-mode contrast to Epic 1 (pull vs. push) — worth stating explicitly in the write-up

**WHY**
- Business goal: faster exception resolution, fewer missed or de-prioritized high-risk breaks
- User goal: stop manually figuring out which exceptions matter; trust the system's prioritization enough to act on it
- Success metrics: reduction in average time-to-resolution per exception, reduction in "aged" unresolved exceptions, reduction in exceptions manually re-prioritized by a human (signal that AI prioritization is trusted)

**HOW**
- Design approach: contextual interviews with the team currently doing manual triage, to capture the implicit rules experienced staff already use
- Key interaction patterns: prioritized worklist (not a flat queue), proposed-remediation card, workflow states (new/flagged → investigating → resolved) with clear ownership of what the AI decided vs. what a human must approve
- Core design challenge: alert fatigue and false-positive distrust — experienced staff will disengage fast if the AI over-flags or under-explains. The write-up should walk through how you designed against that (e.g., visible reasoning for why something was flagged, an easy "not actually an issue" dismissal path that feeds back into the system)

**User story**
> As an operations analyst, I want the system to detect and rank exceptions for me with a clear reason and suggested next step, so that I spend my time resolving the issues that matter most instead of triaging a flat queue.

**Acceptance criteria (draft)**
- Every flagged exception shows why it was flagged and a suggested remediation
- Analyst can dismiss a false positive, and that action visibly feeds back into future prioritization
- Clear visual/state distinction between AI-proposed and human-confirmed resolution
- Aged/unresolved exceptions are visually escalated over time rather than silently sitting in a queue

**Out of scope / open questions**
- Not covering the detection algorithm itself — UX case study, not a model case study
- Open: whether to present Epic 1 and Epic 2 as one combined "Meridian platform" case study with two chapters, or two fully separate case studies — recommend two separate, since they demonstrate distinct interaction modes and should each stand alone in a portfolio review
