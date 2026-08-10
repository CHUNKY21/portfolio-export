# The AI-Native UX Process — Framework & Requirements
Companion to `case-study-concepts.md` and `case-study-requirements.md` in this same folder. This is the shared spine all five case studies should be written against, so each one doesn't have to re-explain "why this is still UX" from scratch.

**Open item:** you mentioned course/class material from yesterday that may be relevant here — paste it in or point me to the file whenever you find it, and I'll fold it into this document rather than starting a separate one.

---

## The core claim
The UX process doesn't get replaced by AI. The same spine — discovery, problem definition, ideation, design/iteration, testing, delivery — still runs every project, including the four in your existing deck. What changes is what has to happen *inside* each stage, because the thing being designed can now act, guess, be wrong, and change its mind. This document defines what's new at each stage, and gives a standard requirements template so all five case studies produce comparable, complete write-ups.

---

## Part 1 — Stage-by-stage: what's the same, what's new

### 1. Discovery & Research
**Same as always:** interviews with users, stakeholders, SMEs. Persona development. Contextual inquiry.

**New in the AI-native version:**
- Map what the model/agent can plausibly know or infer vs. what only a human can judge — this didn't exist as a discovery question before AI
- Surface the user's *existing trust calibration* toward automated/algorithmic decisions in their domain (a compliance reviewer and a vehicle owner start from very different trust baselines)
- Identify where wrong-but-confident output would actually cause harm, not just inconvenience

### 2. Problem Definition / Pain Points
**Same as always:** synthesize interview findings into a clear problem statement and pain point list.

**New in the AI-native version:**
- Separate pain points that are "the workflow is slow/manual" (an AI feature can solve this) from pain points that are "I don't trust automated output in this domain" (a feature can't solve this — only the *design* of the interaction can)

### 3. Competitive / Pattern Analysis
**Same as always:** look at how other products solve the adjacent problem.

**New in the AI-native version:**
- Benchmark against how other AI features handle trust, error, and uncertainty — not just feature parity. What does the best-in-class competitor do when it's wrong?

### 4. Design Thinking / Ideation
**Same as always:** workshops, concept generation, thumbnail sketches, POCs.

**New in the AI-native version:**
- Ideation now includes designing the *behavior*, not just the screen — e.g., what should the system do when it's uncertain, when a user corrects it, when two agents disagree

### 5. Design Sprints & Iteration
**Same as always:** iterative rounds, weekly test cadence, demos and QA.

**New in the AI-native version:**
- Iterating on non-deterministic output is different from iterating on a fixed screen — the same input can produce a different response, so testing protocol has to account for that variance, not just visual/interaction variance

### 6. Usability Testing
**Same as always:** does the user understand the interface, can they complete the task.

**New in the AI-native version:**
- Test for trust and comprehension, not just task completion: does the user believe the output, do they know why they got this answer, do they know what to do when it's wrong
- Test the failure path deliberately — every AI case study should show what happens when the system gets it wrong, not just the happy path

### 7. Delivered Solution
**Same as always:** final screens, specs, a clear before/after.

**New in the AI-native version:**
- The "component" being delivered is often a *state or behavior* (a confidence indicator, a citation pattern, an escalation handoff) as much as it is a screen
- Delivery includes defining what the AI owns vs. what stays human-gated — this is a new artifact type, not just a new screen

### 8. Outcomes / Metrics
**Same as always:** time saved, adoption, error/drop-off rate, approval ratings.

**New in the AI-native version:**
- Add trust-specific metrics that didn't exist before: answer-acceptance rate, override/correction rate, escalation-to-human rate, repeat-question rate (a signal the AI didn't actually answer)

---

## Part 2 — New requirement categories every AI case study needs (that a traditional one didn't)

These are the categories a traditional UX requirements doc (like your existing Trade Ticket / mySMALLBUSINESS / MOCA / OBI work) didn't need to define explicitly, because the system was deterministic. An AI-native case study should address all five:

1. **Trust & Explainability** — how does the user know why the system said/did what it did
2. **Confidence & Uncertainty** — how is "the system isn't sure" represented, and what happens next
3. **Human-in-the-loop / Escalation** — what's fully automated, what requires human confirmation, and how that boundary is shown
4. **Agent Accountability & Legibility** — when more than one agent/process is involved, who did what and why (critical for Epics 4 and 5, which are multi-agent)
5. **Feedback & Correction Loops** — how a user tells the system it was wrong, and what visibly happens with that feedback

---

## Part 3 — Standard UX story template (use this for all five case studies)

This is the same Who/What/When/Why/How structure already used in `case-study-requirements.md` — repeated here as the standing template, so every case study going forward is written to it without renegotiating the format:

```
### Epic — [Name]

WHO
- Primary persona
- Secondary persona(s)
- Stakeholders

WHAT
- Problem
- Proposed solution

WHEN
- Trigger / interaction mode (pull, push/ambient, or both)
- Roadmap framing (real/shipped vs. concept/speculative)

WHY
- Business goal
- User goal
- Success metrics (include at least one trust-specific metric from Part 2)

HOW
- Design approach / process (map explicitly to Part 1 stages)
- Key interaction patterns
- Core design challenge (usually one of the five categories in Part 2)

User story
> As a [persona], I want to [action], so that [benefit].

Acceptance criteria
- ...

Out of scope / open questions
- ...
```

---

## Part 4 — Completeness checklist
Before a case study in this project is called "done," it should be able to check every box:

- [ ] Covers all 8 stages from Part 1 (even briefly), explicitly naming what's the same and what's new
- [ ] Addresses all 5 categories from Part 2, or explicitly notes which ones don't apply and why
- [ ] Written in the Part 3 template — Who/What/When/Why/How, user story, acceptance criteria
- [ ] Shows a failure/uncertainty path, not just the happy path
- [ ] States plainly whether it's real (shipped, anonymized as needed) or concept/speculative
- [ ] Includes at least one trust-specific metric alongside the standard business metric

---

## Next step
This is now the operating framework. When we build out each of the five epics into full case studies, each one gets checked against Part 4 before it's called finished.
