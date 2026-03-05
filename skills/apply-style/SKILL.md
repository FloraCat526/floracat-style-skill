---
name: apply-style
description: Apply the FloraCat Morandi gray-blue design system to any project — colors, typography, components, animations, and layout patterns.
user-invocable: true
---

# FloraCat Design System

Apply a refined Morandi gray-blue design language to the current project. This system emphasizes understated elegance through muted blue-gray tones, light typography, fluid animations, and generous whitespace.

## Design Philosophy

- **Morandi Palette**: Muted gray-blue tones that convey calm sophistication — never loud or saturated.
- **Light Typography**: Predominantly `font-weight: 300` with serif headlines and monospace metadata.
- **Fluid Motion**: A signature cubic-bezier `(0.16, 1, 0.3, 1)` easing across all transitions.
- **Generous Breathing Room**: Large section padding, wide letter-spacing, and relaxed line-height.
- **Layered Depth**: Subtle directional shadows and glassmorphism (backdrop-blur) for hierarchy.

## Quick Reference: Core CSS Variables

```css
:root {
  /* Morandi Gray-Blue Palette */
  --color-paper: #E6EBED;
  --color-ink: #1F2A33;
  --color-surface: #F2F5F7;
  --color-muted: #627C8F;
  --color-line: rgba(98, 124, 143, 0.25);
  --color-accent: #496376;

  /* Font Stacks */
  --font-sans: "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  --font-serif: "Noto Serif CJK SC", "Source Han Serif SC", "Songti SC", "Times New Roman", serif;
  --font-mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
}
```

## Quick Reference: Typography

| Role | Font | Weight | Size | Tracking |
|------|------|--------|------|----------|
| Hero title | serif | 700 | 4xl → 7rem | tighter |
| Section heading | serif | 300 | 4xl → 6rem | tighter |
| Card title | serif | 300 | 2xl–3xl | normal |
| Body text | sans | 300 | base–lg | 0.05em |
| Tag / label | mono | 400 | 9–10px | 0.2em |
| Metadata | mono | 400 | 10–11px | 0.3em |

## Quick Reference: Signature Animation

```css
transition: all 700ms cubic-bezier(0.16, 1, 0.3, 1);
```

## Detailed Specifications

For implementation details, consult these companion files in this directory:

- **color-system.md** — Full palette, gradients, shadows, and transparency layers
- **typography.md** — Font families, size scale, weight usage, and spacing
- **components.md** — Navbar, cards, buttons, timeline, carousel, badges
- **animation.md** — Easing curves, durations, entrance effects, hover states
- **layout.md** — Containers, spacing scale, grid systems, responsive breakpoints

## How to Apply

When the user invokes this skill, follow these steps:

1. **Detect the tech stack** (Next.js/Tailwind, plain CSS, Vue, etc.) and adapt output accordingly.
2. **Install the color variables** — Add the CSS custom properties to the project's global stylesheet.
3. **Configure typography** — Set up font imports (Inter from Google Fonts, plus serif/mono stacks) and base text styles.
4. **Apply component patterns** — Use the component specs to style navbars, cards, buttons, etc. as needed.
5. **Wire up animations** — Add the signature easing and `fade-in-up` keyframe to the project.
6. **Set layout foundations** — Configure container widths, section spacing, and responsive breakpoints.

Always prefer Tailwind utility classes when Tailwind is present. For plain CSS or other frameworks, output raw CSS variables and rulesets. Respect existing project structure — modify in place rather than overwriting.
