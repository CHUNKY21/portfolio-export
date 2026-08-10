# Design System Audit & Migration Plan

**Date:** 2026-08-10  
**Status:** In Progress  
**Priority:** High (Maintainability & Consistency)

---

## Executive Summary

Your portfolio site pages are currently using **hardcoded hex values and concept-specific CSS variables** instead of a centralized design system. This violates the design system rule: *"Never hardcode a hex value — use the token names."*

**What we've created:**
1. ✅ **`/design-system/tokens.css`** — Centralized design system with all color, spacing, and typography tokens
2. ✅ **`/site/04-compliance-copilot-updated.html`** — Template page showing the correct approach (uses tokens.css + semantic CSS classes)
3. 📋 **This audit document** — Step-by-step migration guide

---

## Problem Analysis

### Current State (❌ Not Compliant)

**Example from `/site/index.html`:**
```html
<div class="cc-card" style="--cc-rust:#D54E2B;--cc-coral1:#F5805C;--cc-coral2:#FF8C7A;--cc-coral3:#FFB088;--cc-lime:#BFFD20;--cc-body:#4A4A4A;--cc-label:#8A8A8A;--cc-kpi-blue:#1059FF;...">
```

**Problems:**
- ❌ Hardcoded hex values scattered throughout inline styles
- ❌ Concept-specific variable names (`--cc-*`, `--mtc-*`) instead of standardized tokens
- ❌ No single source of truth for colors
- ❌ Global color changes require editing 6+ files
- ❌ Inconsistent naming across pages
- ❌ Typography sizes hardcoded (`font-size:15px` instead of `var(--font-size-body)`)
- ❌ Spacing hardcoded (`padding:48px 32px` instead of `var(--padding-section)`)

### Desired State (✅ Compliant)

**From `/site/04-compliance-copilot-updated.html`:**
```html
<link rel="stylesheet" href="../design-system/tokens.css">
<style>
  .section { padding: var(--padding-section); }
  .hero { background: linear-gradient(135deg, var(--color-coral-1), var(--color-coral-2) 55%, var(--color-coral-3)); }
</style>
```

**Benefits:**
- ✅ Single centralized token file
- ✅ Standardized naming across all pages
- ✅ Easy global updates
- ✅ Explicit semantic meaning
- ✅ Follows design system spec exactly
- ✅ Matches component library conventions

---

## Token Reference

### Core Tokens Defined in `tokens.css`

| Token Name | Value | Usage |
|---|---|---|
| `--color-primary` | #C1592E | Nav/brand anchor (rust) |
| `--color-hero-coral` | #F4967D | Hero gradient midpoint |
| `--color-coral-1` | #F5805C | Gradient start (concept pages) |
| `--color-coral-2` | #FF8C7A | Gradient middle |
| `--color-coral-3` | #FFB088 | Gradient end |
| `--color-accent-lime` | #BFFD20 | Cover edge accent |
| `--color-headline-navy` | #1E2A6E | Hero headline text |
| `--color-footer` | #E91E8C | Footer/magenta |
| **Framework Colors** | | Four-column framework |
| `--color-pain-points` | #DF505C | Pain points column (red) |
| `--color-business-goals` | #8AD9F8 | Business goals column (blue) |
| `--color-ux-strategy` | #41854F | UX strategy column (green) |
| `--color-feature-set` | #7C417E | Feature set column (purple) |
| **KPI Colors** | | Stat block accent rotation |
| `--color-kpi-blue` | #1059FF | Blue accent |
| `--color-kpi-purple` | #AF00EF | Purple accent |
| `--color-kpi-cyan` | #00BCD9 | Cyan accent |
| `--color-kpi-magenta` | #FF40F4 | Magenta accent |
| **Text Colors** | | |
| `--color-text-primary` | #2B2B2B | Body text, headings |
| `--color-text-secondary` | #8A8A8A | Labels, captions |
| `--color-text-active` | #1A1A1A | Active/emphasis |
| `--color-text-white` | #FFFFFF | White on colored BG |
| **Backgrounds** | | |
| `--color-bg-white` | #FFFFFF | Main background |
| `--color-bg-gray` | #FAFAFA | Section (very light) |
| `--color-bg-section` | #F2F2F2 | Section (light) |
| `--color-border` | #E5E5E5 | Borders/dividers |

---

## File-by-File Migration Guide

### 1. `/site/index.html` (Landing Page)

**Current:** 424 lines, uses inline `--cc-*` and `--mtc-*` variables  
**Action:** Refactor card components to use centralized CSS + tokens.css

**Steps:**
1. Add `<link rel="stylesheet" href="../design-system/tokens.css">` to `<head>`
2. Create a `<style>` block with reusable card classes (`.card`, `.card-gradient`, `.card-stats`, etc.)
3. Replace inline `style` attributes with class names
4. Remove hardcoded color definitions (`--cc-rust:`, `--mtc-rust:`, etc.)
5. Use token names instead (e.g., `background: var(--color-coral-1)`)

**Example transformation:**
```html
<!-- BEFORE -->
<div style="--cc-rust:#D54E2B;--cc-coral1:#F5805C;..." 
     style="color:var(--cc-body);">

<!-- AFTER -->
<div class="card">
  <!-- Color comes from tokens.css -->
</div>
```

---

### 2. `/site/01-meridian-research-agent.html` (Case Study Page)

**Current:** 149 lines, hardcoded colors in hero + inline styles  
**Reference:** Use `/site/04-compliance-copilot-updated.html` as template  
**Status:** Shortest detail page — good second migration target

**Steps:**
1. Copy structure from `04-compliance-copilot-updated.html`
2. Update content from original 01 file
3. Link to `../design-system/tokens.css`
4. Remove all inline `style=` color definitions
5. Test at desktop (1280px) and mobile (375px)

---

### 3. `/site/02-meridian-exception-manager.html` (Case Study Page)

**Current:** 549 lines (longest detail page)  
**Reference:** Use `04-compliance-copilot-updated.html` as template  
**Status:** Most complex — migrate after simpler pages establish pattern

**Steps:**
1. Use same structure as 04-updated
2. Update content sections
3. Verify all 10 sections render correctly
4. Test KPI blocks, persona card, four-column framework

---

### 4. `/site/03-ai-pattern-library.html` (Case Study Page)

**Current:** 520 lines  
**Reference:** Use `04-compliance-copilot-updated.html` as template

---

### 5. `/site/04-compliance-copilot.html` (Case Study Page)

**Current:** 144 lines  
**Status:** ✅ **COMPLETE** — See `/site/04-compliance-copilot-updated.html`  
**Action:** Replace original with updated version after testing

---

### 6. `/site/05-connected-vehicle-assistant.html` (Case Study Page)

**Current:** 140 lines  
**Reference:** Use `04-compliance-copilot-updated.html` as template  
**Status:** Shortest — good final target to ensure pattern holds

---

## Semantic CSS Classes Available in Updated Template

Once you've created the shared CSS, use these semantic classes instead of hardcoded styles:

### Sections & Layout
```html
<div class="section">...</div>
<div class="section bg-alternate">...</div>
```

### Typography
```html
<h2 class="...">Heading</h2>
<div class="section-eyebrow">Label</div>
<p class="...">Body copy</p>
```

### Components
```html
<div class="hero">Hero/Cover section</div>
<div class="audience-badge">Target audience</div>
<div class="kpi-group"><div class="kpi-block">...</div></div>
<div class="persona-card">Persona</div>
<div class="framework">Four-column framework</div>
<div class="callout callout-learning">Learning box</div>
<div class="callout callout-challenge">Challenge box</div>
```

---

## Migration Checklist

### Phase 1: Setup (Complete ✅)
- [x] Create `/design-system/tokens.css`
- [x] Create `/site/04-compliance-copilot-updated.html` as template
- [x] Create this audit document

### Phase 2: Test Template
- [ ] Open `04-compliance-copilot-updated.html` in browser
- [ ] Verify desktop layout (1280px)
- [ ] Verify tablet layout (768px)
- [ ] Verify mobile layout (375px)
- [ ] Check all colors match original
- [ ] Verify all 10 sections render correctly

### Phase 3: Migrate Detail Pages (Recommended Order)
- [ ] **01-meridian-research-agent.html** (shortest, simplest pattern)
- [ ] **05-connected-vehicle-assistant.html** (short, confirms pattern)
- [ ] **04-compliance-copilot.html** (replace with updated)
- [ ] **03-ai-pattern-library.html** (mid-length)
- [ ] **02-meridian-exception-manager.html** (longest, most complex)

### Phase 4: Migrate Landing Page
- [ ] **index.html** (requires card component refactor)

### Phase 5: Verification
- [ ] Visual regression testing (compare before/after screenshots)
- [ ] Cross-browser testing (Chrome, Safari, Firefox)
- [ ] Mobile responsiveness check
- [ ] All links working
- [ ] All assets loading

### Phase 6: Cleanup
- [ ] Delete old versions of migrated files (or keep as backup)
- [ ] Update CLAUDE.md if needed to reference tokens.css
- [ ] Document any custom overrides used per-concept

---

## Why This Matters

### Maintainability
- **Before:** To change the hero gradient, edit 6 files × 10 places each = 60+ edits
- **After:** Edit one line in `tokens.css`

### Consistency
- **Before:** Subtle color variations across pages due to typos
- **After:** Every page uses identical tokens

### Scalability
- **Before:** Adding a 6th concept requires copying/pasting all color definitions
- **After:** New concept automatically inherits all tokens

### Design System Compliance
- **CLAUDE.md rule:** *"Never hardcode a hex value — use the token names above."*
- **Current state:** Violates this on every page
- **After migration:** 100% compliant

---

## Testing Strategy

### Visual Regression
Compare screenshots of updated pages vs. originals:
```bash
# Before: screenshot original page
# After: screenshot updated page
# Diff: should be pixel-perfect identical
```

### Responsive Testing
Test at these breakpoints:
- **Desktop:** 1280px (primary)
- **Tablet:** 768px (secondary breakpoint)
- **Mobile:** 375px (iPhone SE equivalent)

### Browser Compatibility
- Chrome/Edge (Chromium)
- Safari (Mac & iOS)
- Firefox

### Functional Testing
- [ ] All internal links work (`index.html` → case studies)
- [ ] Back links work (case study → `index.html`)
- [ ] All text is readable (sufficient contrast)
- [ ] Images load correctly
- [ ] No console errors

---

## Notes & Gotchas

### 1. Hero Gradient Variants
Two gradient definitions exist:
- `--color-hero-warm` / `--color-hero-coral` (design-system.md web edition)
- `--color-coral-1` / `--color-coral-2` / `--color-coral-3` (actual site colors)

Current pages use the second variant. `tokens.css` includes both for flexibility.

### 2. Favicon
Make sure favicon is linked in updated pages if original had one.

### 3. Metadata
Update `<meta>` tags (viewport, description) if they differ per concept.

### 4. Font Loading
Template uses system fonts + Google Fonts (Poppins, Caveat). Ensure fonts load correctly.

### 5. Performance
Centralizing CSS reduces overall page size. Monitor actual byte reduction after migration.

---

## Questions for Clarification

1. **Backup originals?** Should old HTML files be preserved as `*.backup.html` or deleted?
2. **Staging review?** Should Michael review each migrated page before going live?
3. **Analytics/tracking?** Any event tracking that might be affected?
4. **Future updates?** Once migrated, will `tokens.css` be the source of truth for all portfolio updates?

---

## Next Steps

1. **Test the template:** Open `04-compliance-copilot-updated.html` in browser (already visible in Browser pane)
2. **Visual spot-check:** Verify colors, spacing, typography match original
3. **Confirm approach:** Review this audit with Michael
4. **Begin migration:** Start with Phase 3 detail pages
5. **Final verification:** Full visual regression testing

---

**Document owner:** Claude Code  
**Last updated:** 2026-08-10  
**Status:** Ready for review & testing
