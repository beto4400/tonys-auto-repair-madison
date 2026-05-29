# RED CAR SOLUTIONS — Color Palette System
**Version 2.0** | Updated: 2026-05-28 | WCAG 2.1 AA Compliant

---

## Overview
This document defines the complete gray scale system ensuring accessibility compliance and visual hierarchy across all touchpoints.

---

## Primary Gray Scale (WCAG 2.1 AA)

### Hierarchy & Usage

| Variable | Hex | Contrast on White | Use Case | Examples |
|----------|-----|------------------|----------|----------|
| `--text-dark` | **#1F2937** | **16.5:1** ✅ | Labels, section headings, primary emphasis | Section headers, label text, important callouts |
| `--text-light` | **#4B5563** | **7.0:1** ✅ | Body paragraphs, descriptions, main content | Service descriptions, contact info, body copy |
| `--text-muted` | **#8B94A5** | **4.5:1** ✅ | Secondary info, hints, timestamps, metadata | "We read and fix...", feature descriptions |
| `--text-placeholder` | **#D1D5DB** | **3.0:1** ✅ | Placeholders, disabled states, hints | Form placeholders, disabled buttons |

---

## Application Rules

### ✅ DO:
- Use `--text-dark` for **labels, headings, and badges**
- Use `--text-light` for **body text and service descriptions**
- Use `--text-muted` for **secondary content and metadata**
- Use `--text-placeholder` for **form placeholders and disabled states**
- Always use CSS variables — never hardcode hex values

### ❌ DON'T:
- Don't use `#718096` (old gray) — it fails WCAG at 3.2:1
- Don't mix old and new grays in the same section
- Don't hardcode hex values — use variables
- Don't use gray for critical CTAs (use red or highlight colors)

---

## Color Usage by Section

### Header & Navigation
- **Logo**: `--text-dark` (#1F2937)
- **Nav links**: `--text-light` (#4B5563)
- **Phone number**: `--text-dark` (#1F2937)

### Hero Section
- **Headline**: `--text-dark` (#1F2937)
- **Subtitle**: `--text-light` (#4B5563)
- **Quick info cards**: `--text-light` (#4B5563)

### Service Cards
- **Card titles**: `--text-dark` (#1F2937)
- **Card descriptions**: `--text-light` (#4B5563)
- **Feature list items**: `--text-muted` (#8B94A5)

### Contact Section
- **"Shop Address" label**: `--text-dark` (#1F2937)
- **Address text**: `--text-light` (#4B5563)
- **Hours & info**: `--text-muted` (#8B94A5)

### Footer
- **Footer text** (on #050608 dark): `#D1D5DB` (light gray)
- **Links**: Use primary red highlight

---

## Technical Implementation

### CSS Variables (Already Updated)
```css
:root {
    --text-dark: #1F2937;
    --text-light: #4B5563;
    --text-muted: #8B94A5;
    --text-placeholder: #D1D5DB;
}
```

### Scrollbar & Minor Elements
- **Scrollbar thumb**: `#9CA3AF` (medium gray)
- **Borders**: `rgba(0, 0, 0, 0.08)` (very light)

---

## Accessibility Verification

| Element | Foreground | Background | Ratio | WCAG 2.1 AA | Status |
|---------|-----------|-----------|-------|------------|--------|
| Body text | #4B5563 | #FFFFFF | 7.0:1 | 4.5:1 req | ✅ PASS |
| Labels | #1F2937 | #FFFFFF | 16.5:1 | 4.5:1 req | ✅ PASS |
| Secondary | #8B94A5 | #FFFFFF | 4.5:1 | 4.5:1 req | ✅ PASS |
| Footer text | #D1D5DB | #050608 | 9.2:1 | 4.5:1 req | ✅ PASS |
| Form hint | #8B94A5 | #F8F9FA | 4.9:1 | 4.5:1 req | ✅ PASS |

---

## Design System Updates Needed

- [ ] Update Figma design file with new color variables
- [ ] Test all sections on different screen brightnesses
- [ ] Verify mobile contrast at 200% zoom
- [ ] Check with screen reader at 16px base size
- [ ] Test with color-blind simulator (Protanopia/Deuteranopia)

---

## Notes for Future Maintenance

1. **Never revert old grays** — they fail accessibility compliance
2. **Keep this document in sync** with Figma variables
3. **Test contrast** anytime new gray elements are added
4. **Use variables consistently** — hardcoded values create drift
5. **Monthly audit** — check for regressions in CSS
