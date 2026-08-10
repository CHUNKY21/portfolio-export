# Wireframes — Meridian Research Agent (Epic 1)
Source: `01-meridian-research-agent.md` (WHAT/HOW) + `01-meridian-research-agent-discovery.md` (Discovery & Research pain points).

**Screens covered:** Query Entry → Answer View (cited response) → Source Detail Expand

---

## Screen: Query Entry

- **Purpose**: Let an analyst start an investigation in plain language with no special syntax, resolving discovery pain point #2 — "no consistent starting point — every analyst improvises their own process."
- **Key elements**:
  - Plain-language query input field (brief HOW: "query input")
  - Recent/past investigations list (so an analyst can resume or reference a prior question)
  - Optional context chips if the agent is invoked from within a specific account/position record (not confirmed by the brief — noted as reasonable, not required)
- **Primary user action**: Analyst types a research question and submits → goes to Answer View
- **AI-generated content vs. static UI**: Static — the input field and past-investigations list. Nothing AI-generated on this screen; generation starts on submit.
- **State variations**: Empty state (first-time use), populated state (past investigations visible)

---

## Screen: Answer View

- **Purpose**: Deliver a synthesized, cited answer and make the agent's confidence legible by default — this is the concept's central design answer to discovery pain point #3, "no way to show your work after the fact," and directly implements brief HOW's "cited answer format" and "confidence/certainty signal."
- **Key elements**:
  - **Cited answer text** — synthesized response with inline source markers (brief HOW: "every answer is delivered with its source(s) visible inline, not hidden behind a 'show sources' click")
  - **Confidence signal** — a clear, non-technical indicator distinguishing a confident answer from a partial one (brief HOW; discovery: shown on *every* answer, not just low-confidence ones — testing showed this increased trust)
  - **Show-your-work expand control** on each citation, linking to Source Detail Expand
  - **Flag/feedback control** — lets the analyst mark an answer incorrect or incomplete (brief Acceptance criteria: "feedback is visibly acknowledged")
- **Primary user action**: Analyst reads the answer, expands a citation to verify if needed, and either accepts the answer or flags it
- **AI-generated content vs. static UI**: AI-generated — the answer text, the confidence signal, the citation markers, the fallback/handoff message when present. Static — the flag-feedback control chrome and the expand affordance itself (not its content)
- **State variations**:
  - Confident-answer state (full synthesized answer, high-confidence signal)
  - Partial-answer state (confidence signal shows partial; answer states what it does and doesn't know)
  - Fallback/handoff state — discovery doc: early versions used a flat "I don't know," which testing showed was unhelpful; the resolved design names what the agent does know and routes to a specific next step rather than dead-ending
  - Flagged state — after the analyst uses the feedback control, a visible acknowledgment appears (brief Acceptance criteria requires this be visible, not silent)

---

## Screen: Source Detail Expand

- **Purpose**: Let the analyst verify a citation against the underlying record without leaving the agent, resolving discovery pain point #1 ("manually opening 4-5 systems for a single research question") by keeping verification in one place, and pain point #3 (auditability).
- **Key elements**:
  - The underlying record/data the citation points to
  - A clear link back to which part of the answer this source supports
- **Primary user action**: Analyst reviews the source, then returns to the Answer View
- **AI-generated content vs. static UI**: Static — the underlying record is real system data, not agent-generated. The link between the citation and this specific record is agent-determined (part of the original synthesis), but the record content itself is not.
- **State variations**: Not applicable beyond the parent Answer View states — this is an expand/drill-down, not an independent flow

---

## Consistency Check

- [x] Every screen ties back to a specific pain point from the discovery file
- [x] Component terminology matches the brief's HOW → Key interaction patterns exactly (query input, cited/sourced answer, confidence signal, show-your-work expand, fallback — no invented names)
- [x] AI-generated vs. static content is explicitly distinguished on each screen
- [x] No underspecified areas required flagging — the brief and discovery doc were specific enough to resolve screen structure directly
- [x] Screen order follows a logical flow: entry point (Query Entry) → core response (Answer View) → verification drill-down (Source Detail Expand)
