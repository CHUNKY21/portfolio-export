# Portfolio Design System — Website Edition (michaeljthibodeau.com)

Source: live site screenshots (homepage hero, work grid, footer, AMEX MOCA case study detail page). This is a **second, related design system** — it shares the rust-orange brand color with the PDF deck system (`design-system.md`) but the website has its own distinct palette and layout patterns that the PDF doesn't use (navy headline text, magenta footer, light-gray section backgrounds, small-caps section labels, sidebar project nav, green flow-diagram palette). Use this system when building the Squarespace web pages for the 5 AI UX concepts, so the web output matches the *actual site* rather than the PDF deck's visual language.

---

## 1. Color Styles

| Style Name | Hex (approx.) | Usage |
|---|---|---|
| `Web/Nav-Rust` | `#C1592E` | Top navigation bar background |
| `Web/Hero-Gradient-Warm` | `#FFE8B5` | Hero gradient start (cream) |
| `Web/Hero-Gradient-Coral` | `#F4967D` | Hero gradient end (coral) |
| `Web/Headline-Navy` | `#1E2A6E` | Hero headline text, large statement copy |
| `Web/Footer-Magenta` | `#E91E8C` | Footer background |
| `Web/Section-Gray` | `#F2F2F2` | Work grid / body section backgrounds |
| `Web/Background-White` | `#FFFFFF` | Case study detail page background |
| `Web/Text-Primary` | `#2B2B2B` | Body copy |
| `Web/Text-Secondary` | `#8A8A8A` | Inactive sidebar nav links |
| `Web/Text-Active` | `#1A1A1A` | Active/current sidebar nav link |
| `Web/Diagram-Teal` | `#4FBFB0` | Flow diagram start-node (circle) |
| `Web/Diagram-Lime` | `#B4D468` | Flow diagram decision-node (diamond) |
| `Web/Diagram-Green` | `#7CB87C` | Flow diagram process boxes |
| `Web/White` | `#FFFFFF` | Text on rust/magenta/navy backgrounds |

---

## 2. Typography

Two distinct type treatments observed:

- **Brand/logo mark**: `THIBODEA(U|X)` — set in tracked white uppercase, small size, in the nav bar. Treat as a wordmark, not a reusable text style.
- **Hero statement**: large, lowercase, regular-weight sans-serif in `Web/Headline-Navy`, centered, generous line-height (~1.5×) — reads as a personal statement rather than a headline, sits directly on the gradient.
- **Section labels** (e.g. "THE PROBLEM", "OUR SOLUTION", "MY ROLE", "WHAT WE LEARNED THROUGH RESEARCH"): small, uppercase, letter-spaced/tracked, bold-ish weight, `Web/Text-Primary`
- **Case study title** (e.g. "AMEX MOCA" on the detail page): bold, sentence case, larger than section labels, black
- **Italic subtitle** beneath case study title (e.g. "Redesign and development process for desktop-based application"): italic, regular weight, `Web/Text-Primary`
- **Body copy**: standard regular-weight sans-serif, `Web/Text-Primary`, comfortable line-height
- **Sidebar nav ("The Work")**: header in Poppins light weight, list items in regular Poppins, active item in `Web/Text-Active`/bold, inactive items in `Web/Text-Secondary`
- **Footer text**: uppercase, letter-spaced, white, centered, on magenta

Use Poppins as the primary typeface across all typography — body, labels, headings, and sidebar navigation. Maintain consistency through weight and size variations rather than multiple typefaces.

---

## 3. Layout Patterns

### 3.1 Top Navigation
Full-width rust bar, wordmark left, nav links + a pill-shaped "DOWNLOAD CASE STUDIES" CTA button (outlined, white border/text) right. On the homepage variant, nav is minimal (just a hamburger icon); on interior/case-study pages, nav expands to show full link set (MY GOAL / THE WORK / MY ROLE / MY RESUME / MY CONTACT INFO).

### 3.2 Homepage Hero
Full-width radial gradient (warm cream center-left fading to coral), large centered navy statement text, generous vertical padding (feels like ~500-600px tall).

### 3.3 Work Grid (Homepage)
Light-gray (`Web/Section-Gray`) full-width section, two-column image grid of project screenshots (rotating through several projects), each with a simple caption label beneath (project name, regular weight, dark gray). No borders or cards — just image + caption, generous gutters.

### 3.4 Case Study Detail Page
Two-column layout below the nav:
- **Left sidebar** (narrower column): "The Work" header in the display face, followed by a vertical list of all project names — current project bold/black, others gray (inactive state)
- **Right content column** (wider): case study title, italic one-line subtitle, then stacked sections each with a small-caps tracked label header: THE PROBLEM, OUR SOLUTION, MY ROLE, WHAT WE LEARNED THROUGH RESEARCH, THE APPLICATION CONCEPT HAS A [N] STEP PROCESS (numbered sub-steps with bold numeral + label, then body paragraph each), followed by supporting diagrams/screenshots inline

A blurred/faded hero treatment of the project's UI screenshot sits behind a large lowercase project title + one-line value-prop statement at the top of the case study page, echoing the homepage hero's gradient-behind-statement pattern but using the project's own screenshot (blurred) instead of a flat gradient.

### 3.5 Process Flow Diagrams
Simple flowchart built from: one teal circle (start node), lime-green diamonds (decision points), and green rounded-rectangle boxes (process steps) connected by thin gray lines with arrowheads. Text labels inside/beneath each shape, small and centered. Caption beneath the whole diagram (e.g. "User Journeys were mapped out").

### 3.6 Footer
Full-width bright magenta bar, single centered line of uppercase tracked white text: location, phone, email, separated by generous spacing (not literal punctuation-heavy separators).

---

## 4. Components to Build in Figma

1. **Nav Bar** — variant property `context` (Homepage-minimal / Interior-full), rust background, wordmark, optional CTA pill
2. **Hero — Gradient Statement** — variant property `background` (Flat-gradient / Screenshot-blur-gradient), navy centered statement text
3. **Work Grid Item** — image + caption, used in a repeating grid
4. **Case Study Sidebar Nav** — display-face header + list, active/inactive list-item states
5. **Section Label** — small-caps tracked component, used for THE PROBLEM / OUR SOLUTION / MY ROLE / etc.
6. **Numbered Process Step** — bold numeral + label, body paragraph beneath, used in "3 step process" style sections
7. **Flow Diagram Node Set** — teal circle, lime diamond, green box, connecting arrow — as a small shape library to assemble diagrams from
8. **Footer Bar** — magenta background, centered tracked contact line

---

## 5. Relationship to the PDF Deck System (`design-system.md`)

Both systems share the rust-orange brand anchor (`#C1592E`), confirming brand consistency across Michael's PDF portfolio and personal site. But they diverge meaningfully:

| | PDF Deck System | Website System |
|---|---|---|
| Section dividers | Solid rust background | N/A — rust is nav-only |
| Stat/metric display | Oversized colored numbers (blue/magenta/teal/green rotation) | Not used on site |
| Accent framework | 4-column red/blue/green/purple | Not used on site |
| Headline color | Coral | Navy |
| Footer/closing | Coral gradient banner | Solid magenta bar |
| Diagram palette | N/A | Teal/lime/green flow nodes |
| Section labels | Plain headers | Small-caps tracked labels |

**Recommendation**: since the goal is Squarespace web pages that live on the actual site, build the Squarespace output using **this website system**, not the PDF system — visitors will land on these pages from the same domain and expect visual continuity with the rest of the site. Reserve the PDF deck system for the downloadable PDF only. Update `CLAUDE.md`'s Squarespace HTML Conventions to point here once this is confirmed.
