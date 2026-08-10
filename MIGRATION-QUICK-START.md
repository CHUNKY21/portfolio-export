# Quick Start: Design System Migration

**TL;DR:** Use the template page as a starting point for each site page migration. Takes ~30 min per page once you understand the pattern.

---

## The 3-Minute Overview

**Problem:** Site pages hardcode colors (❌ `--cc-rust:#D54E2B`) instead of using centralized tokens (✅ `var(--color-primary)`)

**Solution:** Link `tokens.css` + use semantic CSS classes instead of inline styles

**Result:** Single source of truth for all design values. Global color changes take seconds instead of hours.

---

## Template to Copy From

**File:** `/site/04-compliance-copilot-updated.html`

This file shows:
1. ✅ How to link `tokens.css`
2. ✅ How to structure HTML with semantic classes
3. ✅ How to style all 10 case study sections properly
4. ✅ How to make it responsive

**Use this as your template for all 5 detail pages.**

---

## Step-by-Step for Each Detail Page

### Step 1: Copy the Template Structure
Open `04-compliance-copilot-updated.html` and use its structure as your starting point.

Key elements to preserve:
```html
<head>
  <link rel="stylesheet" href="../design-system/tokens.css">
  <style>/* All reusable CSS classes */</style>
</head>
<body>
  <!-- Navbar -->
  <div class="navbar">...</div>
  
  <!-- Content wrapper -->
  <div class="detail-wrapper">
    <!-- 10 sections: hero, intro, discovery, pain points, persona, framework, design, results, insight, cta -->
  </div>
</body>
```

### Step 2: Update the Content
Replace placeholder content with the real content from the original page.

**Keep these class names (don't change them):**
- `.navbar` — Top navigation bar
- `.detail-wrapper` — Content container
- `.hero` — Cover/hero section
- `.section` — Content sections
- `.section-eyebrow` — Section labels
- `.audience-badge` — Target audience badge
- `.kpi-block` — KPI stat blocks
- `.persona-card` — Persona cards
- `.framework` — Four-column framework
- `.callout` — Callout boxes (learning / challenge)
- `.insight-section` — Key insight section

### Step 3: Update the Title & Meta Tags
```html
<title>Your Case Study Name — AI UX Case Studies</title>
```

### Step 4: Delete the Original File
Once tested and verified, delete or archive the original inline-style version.

### Step 5: Test
- Desktop (1280px)
- Tablet (768px)
- Mobile (375px)
- All links work
- Colors look correct

---

## Files to Update (in this order)

### Round 1: Test the Pattern (2 pages)
1. **01-meridian-research-agent.html** ← START HERE
   - Shortest detail page (149 lines)
   - Simplest pattern to verify
   - ~30 min

2. **05-connected-vehicle-assistant.html**
   - Also short (140 lines)
   - Confirms pattern works consistently
   - ~30 min

### Round 2: Replace with Template (1 page)
3. **04-compliance-copilot.html**
   - Already has updated version created
   - Just replace original with `04-compliance-copilot-updated.html`
   - ~10 min

### Round 3: Mid-Length Pages (1 page)
4. **03-ai-pattern-library.html**
   - Medium length (520 lines)
   - Use template pattern
   - ~30 min

### Round 4: Longest Page (1 page)
5. **02-meridian-exception-manager.html**
   - Longest detail page (549 lines)
   - Most sections but same pattern
   - ~45 min

### Round 5: Landing Page (1 page)
6. **index.html**
   - Card grid layout (different from detail pages)
   - More complex refactor
   - ~1-2 hours
   - Do this last after pattern is proven

---

## Color Token Quick Reference

### Brand Colors
```css
var(--color-primary)           /* #C1592E (rust) */
var(--color-coral-1)           /* #F5805C (gradient start) */
var(--color-coral-2)           /* #FF8C7A (gradient mid) */
var(--color-coral-3)           /* #FFB088 (gradient end) */
var(--color-accent-lime)       /* #BFFD20 (accent bar) */
```

### Text Colors
```css
var(--color-text-primary)      /* #2B2B2B (body) */
var(--color-text-secondary)    /* #8A8A8A (labels) */
var(--color-text-white)        /* #FFFFFF (on colored BG) */
```

### Framework Colors (Four-Column)
```css
var(--color-pain-points)       /* #DF505C (red) */
var(--color-business-goals)    /* #8AD9F8 (blue) */
var(--color-ux-strategy)       /* #41854F (green) */
var(--color-feature-set)       /* #7C417E (purple) */
```

### KPI Stat Colors
```css
var(--color-kpi-blue)          /* #1059FF */
var(--color-kpi-purple)        /* #AF00EF */
var(--color-kpi-cyan)          /* #00BCD9 */
var(--color-kpi-magenta)       /* #FF40F4 */
```

### Background Colors
```css
var(--color-bg-white)          /* #FFFFFF */
var(--color-bg-gray)           /* #FAFAFA (very light) */
var(--color-bg-section)        /* #F2F2F2 (light) */
```

---

## Spacing Quick Reference

```css
var(--space-xs)    /* 4px (tight) */
var(--space-sm)    /* 8px (compact) */
var(--space-md)    /* 16px (standard) */
var(--space-lg)    /* 24px (section padding) */
var(--space-xl)    /* 40px (component gap) */
var(--space-2xl)   /* 64px (section spacing) */
var(--space-3xl)   /* 90px (hero padding) */
```

### Pre-built Spacing
```css
var(--padding-section)         /* 48px 32px (desktop) */
var(--padding-section-mobile)  /* 32px 20px (mobile) */
var(--gap-component)           /* 32px between components */
var(--gap-subcomponent)        /* 16px between sub-elements */
```

---

## Typography Quick Reference

```css
var(--font-family-body)        /* System fonts + Poppins */
var(--font-family-display)     /* Poppins, Century Gothic, Futura */
var(--font-family-script)      /* Caveat (sidebar header only) */

var(--font-size-h1)            /* 38px (case study title) */
var(--font-size-h2)            /* 28px (section header) */
var(--font-size-h3)            /* 16px (subsection header) */
var(--font-size-body)          /* 15px (body copy) */
var(--font-size-small)         /* 13px (small text) */
var(--font-size-micro)         /* 12px (footer, labels) */

var(--line-height-comfortable) /* 1.6 (body) */
var(--line-height-normal)      /* 1.4 (default) */
```

---

## Responsive Breakpoint

**Mobile:** 768px and below  
All pages should stack to single column at this width.

The template handles this automatically via:
```css
@media (max-width: 768px) {
  .framework { grid-template-columns: 1fr; }
  .section { padding: var(--padding-section-mobile); }
  /* etc. */
}
```

---

## Before & After Example

### ❌ BEFORE (Hardcoded, in original page)
```html
<style>
  .cc-detail { --rust:#D54E2B; --coral1:#F5805C; --coral2:#FF8C7A; --coral3:#FFB088; --lime:#BFFD20; --body:#4A4A4A; --label:#8A8A8A; --line:#E5E5E5; }
</style>
<div class="cc-detail" style="--rust:#D54E2B; --coral1:#F5805C; ...">
  <div style="background:linear-gradient(135deg,var(--coral1),var(--coral2) 55%,var(--coral3));padding:64px 32px;">
    <div style="position:absolute;left:0;top:0;bottom:0;width:6px;background:var(--lime);"></div>
  </div>
</div>
```

### ✅ AFTER (Tokenized, in updated template)
```html
<link rel="stylesheet" href="../design-system/tokens.css">
<style>
  .hero {
    background: linear-gradient(135deg, var(--color-coral-1), var(--color-coral-2) 55%, var(--color-coral-3));
    padding: var(--space-3xl) var(--space-xl);
  }
  .hero-accent-left { background: var(--color-accent-lime); }
</style>
<div class="detail-wrapper">
  <div class="hero">
    <div class="hero-accent-left"></div>
    <!-- content -->
  </div>
</div>
```

**Benefits:**
- 1 centralized file for all colors instead of 6 separate definitions
- Consistent naming across all pages
- Easy to find and update color values
- Follows design system spec exactly

---

## Gotchas & Tips

### Tip 1: Copy-Paste the CSS
Don't retype the `<style>` block. Copy-paste from the template to avoid typos.

### Tip 2: Preserve Media Queries
The responsive CSS in the template is critical. Don't skip or simplify it.

### Tip 3: Test Mobile First
After migrating each page, test at 375px width first to catch responsive issues early.

### Tip 4: Color Spot-Check
Use browser DevTools color picker to verify:
- Hero gradient colors match
- Framework column colors are correct
- Text contrast is readable

### Tip 5: Link Paths
Make sure `<link rel="stylesheet" href="../design-system/tokens.css">` works from each page's location:
- `/site/01-*.html` → `../design-system/tokens.css` ✅
- `/site/index.html` → `./design-system/tokens.css` ⚠️ (different path)

---

## Questions?

Refer to:
- **Full audit:** `/AUDIT-DESIGN-SYSTEM.md`
- **Template:** `/site/04-compliance-copilot-updated.html`
- **Token definitions:** `/design-system/tokens.css`
- **Design system spec:** `/docs/design-system.md`

---

## Time Estimates

| Page | Lines | Est. Time |
|---|---|---|
| 01-meridian-research-agent.html | 149 | 30 min |
| 05-connected-vehicle-assistant.html | 140 | 30 min |
| 04-compliance-copilot.html | 144 | 10 min (replace) |
| 03-ai-pattern-library.html | 520 | 45 min |
| 02-meridian-exception-manager.html | 549 | 45 min |
| index.html | 424 | 1-2 hrs |
| **Total** | **1926** | **3-4 hours** |

Once you understand the pattern (after page #1), each subsequent page gets faster.

---

**Ready to start? Begin with `/site/01-meridian-research-agent.html`. Use `/site/04-compliance-copilot-updated.html` as your template. You've got this! 🚀**
