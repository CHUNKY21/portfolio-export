# AI UX Portfolio — Four Case Study Concepts
Prepared for Michael Thibodeau | Draft for review

## What I based this on
- Your resume (BlackRock, American Honda, Wells Fargo, Credit Suisse, UBS, Amex, ADP roles)
- Your existing case study deck (`ThibodeauCaseB2B26.pdf`) — Wells Fargo Trade Ticket, Wells Fargo mySMALLBUSINESS, Amex MOCA, Credit Suisse OBI. Those four are strong but only *mention* AI in passing (data-scientist collaboration callouts). The concepts below are chosen specifically to **not overlap** with that deck and to fill the gap: work where AI/agentic behavior is the core design problem, not a footnote.
- I could not open your LinkedIn profile — it redirected to a sign-in wall rather than showing the public page, so I didn't pull anything from it. If you want me to use it, the easiest path is pasting the relevant sections as text, or the profile in a PDF export.

## Why four, and why these four
You asked for range — across formats (conversational agent, ambient/system-initiated AI, reusable components, multi-agent orchestration). Each concept below demonstrates a *different* AI UX pattern, so together they read as range rather than four versions of the same idea.

---

## Concept 1 — The Research Agent (conversational/query-driven agent)
**Real anchor:** BlackRock, "AI-powered Research Agent... reduced investigation time by ~45 minutes per workflow."

**The pattern it demonstrates:** user-initiated agent — someone asks a question or starts an investigation, the agent retrieves, synthesizes, and cites, and the human verifies and acts. This is the "chat/copilot" archetype every AI UX portfolio needs at least one of.

**What the case study would walk through:**
- The workflow before AI (manual research across systems, the 45-min baseline)
- Trust and verification design: how the agent shows its sources/reasoning so an accounting/ops professional will actually act on it
- Handling uncertainty — what the agent does when it's not confident, partial data, conflicting sources
- The measurable outcome (time saved) and how you validated it

**Confidentiality note:** BlackRock is your current employer and Aladdin is a named, proprietary platform — different risk profile than your past employers (Wells Fargo, Amex, etc., which you named directly in the existing deck). Worth deciding upfront whether to name it directly, generalize it ("enterprise investment operations platform"), or fictionalize specifics while keeping the real problem/process/outcome. I'd flag this to whoever cleared your existing deck before publishing.

---

## Concept 2 — Exception Management (ambient/system-initiated AI)
**Real anchor:** BlackRock, "Exception Management experiences" — same role, distinct product.

**The pattern it demonstrates:** the opposite mode from Concept 1. Nobody asks the system anything — the AI notices something wrong (a break, a mismatched trade, an operational exception) and surfaces it, prioritized, with proposed remediation. This is proactive/ambient AI, not conversational, and it's a pattern most junior AI-UX portfolios never show.

**What the case study would walk through:**
- How exceptions used to surface (queues, manual triage, tribal knowledge of "which ones actually matter")
- Design for triage and prioritization when an algorithm is doing the flagging — how you prevent alert fatigue, false-positive distrust, "black box" pushback from experienced ops staff
- Workflow states: new/flagged → investigating → resolved, and what the AI owns vs. what stays human-gated
- Where this deliberately contrasts with Concept 1 (pull vs. push, conversational vs. status-driven)

Same confidentiality note as Concept 1 applies.

---

## Concept 3 — Designing the Components, Not Just the Screen (AI pattern library / design system)
**No single real anchor — this one is a synthesis case study**, built from your design-system leadership at Wells Fargo, Credit Suisse, and BlackRock ("define scalable UX standards, reusable interaction patterns... design system contributions in Figma").

**The pattern it demonstrates:** systems thinking. Instead of walking through one product, this case study is about the *reusable vocabulary* you had to invent because standard design-system components don't cover AI states: a citation/source card, a confidence or certainty indicator, a streaming-response state, a "the model got this wrong, tell it" correction pattern, an escalation-to-human handoff.

**What the case study would walk through:**
- The gap: what happens when product teams bolt AI onto a design system built for deterministic UI
- The component set you defined (pick 4–6: e.g., confidence indicator, citation card, streaming/loading state, correction/feedback control, human-handoff banner, empty/no-answer state)
- Governance — how you got adoption across multiple product teams (you've done this exact kind of rollout before, non-AI, at Wells Fargo and Credit Suisse)
- Before/after: screens from different products that now share the same AI vocabulary

**Why this one matters for the portfolio:** it's the concept a design leader/manager audience (not just an IC audience) will respond to most — it shows you don't just design one AI feature, you build the system so a whole org can.

---

## Concept 4 — Multi-Agent Orchestration (speculative/concept piece)
**Anchor:** a forward-looking concept, positioned honestly as speculative design rather than shipped work — every senior AI UX portfolio benefits from one piece that shows where you think the field is going, not just what you shipped.

**Two directions to choose from, both draw on real domain depth you have:**
- **Compliance Co-Pilot** — building on your Credit Suisse Risk & Compliance / Outside Business Interests background: a concept where a submission is handled by multiple specialized agents (a research agent, a policy/compliance-check agent, an escalation agent) that hand off to each other and to a human reviewer, with the UI showing *which* agent is acting and why at each step.
- **Connected Vehicle Assistant** — building on your American Honda service-design work: a concept for an in-vehicle or owner-app multi-agent assistant (a scheduling agent, a diagnostics agent, a service-recommendation agent) — gives you a second industry in the portfolio besides financial services, which helps range.

**The pattern it demonstrates:** orchestration and accountability — when more than one "agent" is involved, the UX problem shifts to making handoffs legible (who's acting, what changed, why), not just single-agent trust.

**What the case study would walk through:**
- The problem multi-agent systems create for users (opacity — "who decided this?")
- Your proposed interaction model for surfacing agent handoffs
- Explicitly framed as a concept/vision piece — dated, scoped, and honest about what's speculative vs. validated

---

## Suggested range check
| # | Format shown | Push/Pull | Real or concept |
|---|---|---|---|
| 1 | Conversational agent | Pull (user asks) | Real (BlackRock) |
| 2 | Ambient/system-initiated AI | Push (system flags) | Real (BlackRock) |
| 3 | AI component/pattern library | N/A — systems layer | Synthesis of real work |
| 4 | Multi-agent orchestration | Both | Speculative/concept |

## Open questions for you
1. Do 1 & 2 use the real BlackRock/Aladdin names, or do you want them generalized/fictionalized given it's your current employer?
2. For Concept 4 — Compliance Co-Pilot (fits your existing Credit Suisse case study) or Connected Vehicle (adds a second industry)? Or both, and we cut one of 1/2?
3. Format for the finished case studies — same slide-deck style as `ThibodeauCaseB2B26.pdf`, or something else (web page, PDF write-up, Figma)?

Once you pick a direction on these, I'll build out the full case study for each.
