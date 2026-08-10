# HondaLink Guide — Brand Identity Log

**Status: IN PROGRESS.** This file is written incrementally so a fresh session can resume without re-deriving decisions. Update the "Build status" section at the bottom every time Figma work happens.

Concept source: `../briefs/05-connected-vehicle-assistant-discovery.md` (speculative/concept, not shipped — American Honda). This identity is for the owner-facing multi-agent assistant described there (scheduling agent + diagnostics agent + service-recommendation agent, unified into one labeled feed).

Figma file: key `ZDzpeLBckTAk95gPLEhWBg` ("Connected Vehicle Assistant — Brand Identity"). File name left as-is per instructions; the product name lives inside the file (page names, frame names, variable collection name), not in the file title.

---

## 1. Product name

**HondaLink Guide** (short form used in-product: "Guide").

### Naming rationale
- Honda's real owner-facing connected-car platform is **HondaLink** (the actual app name for remote start, vehicle health alerts, etc.). Rather than inventing a brand-new standalone app name — which would be implausible; Honda would not ship a second, unrelated owner app — this concept is framed as a **named feature/sub-brand living inside HondaLink**, the way real automaker owner-app ecosystems work (e.g., Ford's "FordPass," Hyundai's "Bluelink," Subaru's "Starlink" are the umbrella; sub-features get their own short names underneath).
- "Guide" was chosen over alternatives considered:
  - *Advisor* — rejected: too easily confused with the human "service advisor" role at the dealership, which the brief explicitly keeps separate (agent proposes, human negotiates cost/timing).
  - *Concierge* / *Copilot* — rejected: reads as borrowed tech-startup/Big Tech vocabulary (Copilot especially — Microsoft Copilot, GitHub Copilot), which the brief explicitly says to avoid. Concierge overclaims a level of white-glove service beyond what a notification-consolidation feed does.
  - *Companion* — rejected: vaguer, doesn't carry the "translates something confusing into something clear" meaning.
  - *Guide* — kept: a guide's job is literally to translate something complex (a trail, a museum, a warning light) into plain language and a next step — which is exactly the concept's central mechanic (plain-language diagnostic translation, per the brief's Design & Iteration section). It's a plain, ordinary English word — not a coined tech name — consistent with how Honda actually names things (HondaLink, Honda Sensing, Honda Care).
- Full lockup: **HondaLink Guide**. In running case-study copy, shorten to "Guide" after first mention (e.g., "Guide's diagnostics agent flagged...").

---

## 2. Logo / wordmark / mark

### Wordmark
Two-weight lockup, same pattern real sub-brands use (e.g., "Apple Care", "PlayStation Plus" — master brand in a neutral weight, sub-brand name carrying the accent):
- **"HondaLink"** — set in Inter Medium, neutral ink color (`#20303B`) — represents the parent platform, restrained.
- **"Guide"** — set in Inter Bold, primary brand color (`#155D82` "Guide Blue") — the sub-brand name carries the color and weight emphasis.
- No literal reproduction of Honda's real "H" trademark or their actual wordmark typeface — this is a distinct, original sub-brand treatment that reads as "living inside" Honda's ecosystem without claiming to be Honda's real visual identity.

### Standalone mark (app icon / avatar scale)
Concept: **three arcs orbiting a solid core dot**, inside a rounded-square app-icon container.
- The center solid dot = one unified assistant voice.
- Three short arcs, one in each agent accent color (diagnostics teal, scheduling amber, recommendation violet), positioned at equal 120° intervals around the dot = the three agents feeding one center.
- This directly encodes the case study's core UX idea (three agents, one legible feed) rather than being decorative.
- Built as real vector shapes in Figma (ellipse arcs via stroke + arc data, not an imported icon asset).

### Clear space & minimum size
- Clear space: minimum padding around the full lockup (wordmark + mark) equal to the cap-height of "Guide" on all sides.
- Standalone mark minimum size: 24px (app-icon/favicon-scale use) — below this, arcs should simplify to solid dots of the same three colors rather than true arcs (documented as a fallback rule).
- Full lockup (mark + wordmark) minimum size: 120px wide.

---

## 3. Color system

Figma variable collection name: **"HondaLink Guide — Brand Colors"**.

| Token | Hex | Role | Rationale |
|---|---|---|---|
| `guide/primary` | `#155D82` | Primary brand color (Guide Blue) | Automotive-adjacent, trustworthy, tech-capable deep blue. Deliberately **not** red — Honda's real brand red is the distant reference point, but red is reserved *exclusively* for the safety-critical accent below so it never competes with an actual urgent alert. Blue also matches the mental model owners already have from other connected-car/telematics apps (Bluelink, ConnectedDrive, ancillary dashboard "info" blue). |
| `guide/diagnostics` | `#1F9E8C` | Diagnostics agent accent (vehicle health) | Teal-green — clinical/health association, distinct from primary and from the urgency red. |
| `guide/scheduling` | `#E0A63A` | Scheduling agent accent | Warm amber/gold — calendar/time association, friendly, non-alarming. |
| `guide/recommendation` | `#8464A8` | Service-recommendation agent accent | Violet/plum — signals "suggestion/insight." Chosen in the same family as Michael's real portfolio deck's Feature Set plum (`#7C417E`), so the identity has a quiet lineage back to his existing shipped case-study palette without literal reuse. |
| `guide/urgent` | `#D6432E` | Safety-critical / urgent accent | Warm confident red-orange — intentionally close to the red owners already associate with dashboard warning lights (so the color itself carries meaning transferred from the vehicle), tuned slightly warmer/less saturated than a pure alarm red so it reads "unmistakable" without being panic-inducing. Reserved *only* for safety-critical, push-immediately content per the brief — never reused for ordinary diagnostics content. |
| `guide/ink` | `#20303B` | Primary text / wordmark neutral | Dark neutral, not pure black — matches Michael's existing deck convention (no pure black body text). |
| `guide/surface` | `#F2F5F7` | Card/surface background | Light neutral gray-blue, calm background for feed cards. |
| `guide/background` | `#FFFFFF` | Page background | White base, per Michael's existing deck convention. |

Design rule carried into all mockups: **the urgent red is never used as a decorative or branding color** — it appears only on safety-critical feed entries, so its rarity is itself part of the signal.

---

## 4. Typography

**Typeface: Inter** (available natively in Figma; free, highly legible at small sizes — appropriate for glanceable use in/around a vehicle; friendly but not childish; a credible stand-in for the SF-Pro-adjacent system-font feel of a real connected-car app).

Type ramp (all Inter):
| Style | Size / Line height | Weight | Use |
|---|---|---|---|
| Display | 28 / 34 | Bold | App-icon-scale wordmark, splash |
| Title | 20 / 26 | Semi Bold | Feed section headers ("Today", "This week") |
| Body Emphasis | 16 / 22 | Semi Bold | Feed entry headline (e.g., "Battery health check recommended") |
| Body | 15 / 21 | Regular | Feed entry plain-language explanation |
| Label | 13 / 16 | Medium | Agent attribution label ("Diagnostics", "Scheduling", "Recommendation") — always paired with the agent's accent color |
| Caption | 12 / 16 | Regular | Timestamps, secondary metadata |

---

## 5. Voice & tone — 3 principles

Grounded directly in the case study's documented design lesson (fragmented notifications → unified, legible, plain-language feed):

1. **Plain language over dashboard codes.** A diagnostics-agent entry never surfaces a bare code or warning-light label alone — it always pairs the code with what it means and a recommended next step. This is the direct answer to the real, documented Honda pain point (owners calling the service center to ask what an alert means).
2. **One voice per entry, always labeled.** Every feed entry — even a consolidated/merged one — names which agent is speaking (Diagnostics / Scheduling / Recommendation), using the agent's accent color and label. Consolidation merges the *entry*, never the *attribution* — an owner can always tell which system said what.
3. **Propose, don't presume.** Anything with a scheduling or cost implication is phrased as an offer requiring the owner's one-tap confirmation ("Propose Tuesday 2pm?" not "Booked: Tuesday 2pm") — informational content (diagnostics, recommendations) can surface ambiently, but the assistant never states a scheduling/cost action as already done. This is the product's direct expression of the brief's human-in-the-loop boundary.

---

## 6. Applied contexts (deliverables)

1. **Unified feed header mockup** — shows the wordmark lockup at top, and 2-3 feed entries demonstrating the three agent-accent label treatment (including one consolidated/merged entry with sub-attribution, and one safety-critical entry in the urgent-red treatment).
2. **App-icon-scale treatment** — the standalone mark (3-arc + core dot) at app-icon scale on the rounded-square container, plus a small favicon-scale fallback (simplified to 3 dots) shown at actual minimum size for verification.

---

## Build status (update every session)

- [x] Brief read, name chosen, rationale documented (this file)
- [x] Figma file inspected — file was empty (single default "Page 1", node 0:1)
- [ ] Figma: page structure set up (Cover / Colors / Type / Logo / Mockups pages)
- [ ] Figma: variable collection "HondaLink Guide — Brand Colors" created with all 8 tokens
- [ ] Figma: wordmark built (HondaLink + Guide lockup)
- [ ] Figma: standalone mark built (3-arc + core dot, rounded-square container)
- [ ] Figma: clear-space/min-size guidance frame
- [ ] Figma: type ramp frame
- [ ] Figma: voice & tone frame (3 principles as text)
- [ ] Figma: unified feed header mockup
- [ ] Figma: app-icon-scale treatment frame
- [ ] Final screenshot pass / visual QA across all frames

*(Next action if resuming: check the above checklist, use `get_metadata` on the Figma file to see what pages/frames already exist, cross-reference against this log, and continue from the first unchecked item.)*
