---
description: Development workflow for Ayni.AI landing page following the Andean High-Tech Editorial design system
---

# Ayni.AI Landing Page Development Workflow

## Pre-requisites

- Read `.agent/rules/design-system-rules.md` before writing ANY component.
- Read `.agent/docs/design-system.md` for full token reference.
- Read `.agent/docs/component-rules.md` for component patterns.

## Workflow Steps

### 1. Before Creating Any Component

// turbo-all

1. Verify the component follows the Andean High-Tech Editorial rules.
2. Check that no `<hr>`, solid borders, or generic SaaS patterns are used.
3. Confirm typography uses Space Grotesk (headlines) and Manrope (body).
4. Confirm color tokens come from the design system palette.

### 2. Component Creation Checklist

- [ ] Uses semantic HTML (`<section>`, `<header>`, `<main>`, `<footer>`).
- [ ] No dividers — spacing is 64px or 80px vertical.
- [ ] Glassmorphism on floating elements (40% opacity + blur 24px).
- [ ] Buttons use "Luminous" gradient (primary → secondary).
- [ ] Ghost borders only for accessibility, never decorative.
- [ ] Headline text uses `font-display` (Space Grotesk) with `tracking-tight`.
- [ ] Body text uses `font-body` (Manrope) with `font-light`.
- [ ] All interactive elements have unique descriptive IDs.
- [ ] Atmospheric depth effects where appropriate (radial gradients, orbs).

### 3. Section Spacing Pattern

```
Section A
  ↕ 64px–80px (padding/margin, NO hr or border)
Section B (different tonal background)
  ↕ 64px–80px
Section C
```

### 4. Quality Gate

Before committing:

- [ ] Visual hierarchy through tonal changes only, no borders.
- [ ] Asymmetric, intentional layout — not a generic SaaS template.
- [ ] All fonts loaded (Space Grotesk + Manrope).
- [ ] Responsive at all breakpoints.
- [ ] Accessible: contrast ratios, focus indicators, semantic HTML.
