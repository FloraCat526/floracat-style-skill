# Color System

## Core Palette

```css
:root {
  --color-paper: #E6EBED;                    /* Page background — warm gray-blue white */
  --color-ink: #1F2A33;                      /* Primary text — deep slate blue */
  --color-surface: #F2F5F7;                  /* Card/section background — lighter than paper */
  --color-muted: #627C8F;                    /* Secondary text, labels — Morandi blue */
  --color-line: rgba(98, 124, 143, 0.25);    /* Dividers, borders — translucent blue-gray */
  --color-accent: #496376;                   /* Interactive emphasis — deep Morandi blue */
}
```

### Semantic Mapping

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-paper` | `#E6EBED` | `<body>` background, page canvas |
| `--color-ink` | `#1F2A33` | Headings, primary body text |
| `--color-surface` | `#F2F5F7` | Card backgrounds, elevated panels |
| `--color-muted` | `#627C8F` | Secondary text, tags, timestamps |
| `--color-line` | `rgba(98,124,143,0.25)` | Borders, horizontal rules, separators |
| `--color-accent` | `#496376` | Links, active states, hover highlights |

## Hero / Dark Theme Palette

For dark hero sections or immersive full-bleed areas:

```css
--hero-bg: #0A1015;
--hero-text-primary: #D4DEE5;
--hero-text-secondary: #829AB1;
--hero-highlight: #60A5FA;
```

### Hero Text Gradient

```css
background: linear-gradient(to right, #E2F0FB, #A5C9E5, #60A5FA);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
```

Tailwind equivalent:
```
bg-gradient-to-r from-[#E2F0FB] via-[#A5C9E5] to-[#60A5FA] bg-clip-text text-transparent
```

## Gradient Combinations

### Product Card Gradients (light → light, Morandi range)

```css
/* Primary — cool blue mist */
background: linear-gradient(to bottom, #E2F0FB, #A5C9E5, #7196B5);

/* Neutral frost */
background: linear-gradient(to bottom, #E2E8F0, #F1F5F9);

/* Silver steel */
background: linear-gradient(to bottom, #CBD5E1, #E2E8F0);

/* Pale harbor */
background: linear-gradient(to bottom, #D4DEE5, #E9EDF0);
```

### Project Overlay Gradients (dark → medium)

```css
/* Deep ink → accent */
background: linear-gradient(to bottom right, #1F2A33, #496376);

/* Muted → light */
background: linear-gradient(to bottom right, #627C8F, #9BAEBA);
```

### Surface Gradients (subtle card backgrounds)

```css
background: linear-gradient(to bottom, #E1E6EB, #F2F4F6);
background: linear-gradient(to bottom, #D4DEE5, #E9EDF0);
background: linear-gradient(to bottom, #D8DCE0, #ECF0F3);
background: linear-gradient(to bottom, #C5D0D9, #E2E7EB);
```

## Shadow System

Shadows use the Morandi blue-gray family (`rgba(130,154,177,…)` or `rgba(73,99,118,…)`) — never pure black.

| Level | Value | Usage |
|-------|-------|-------|
| Subtle | `0 1px 3px rgba(130,154,177, 0.05)` | Navbar, floating bars |
| Medium | `0 20px 40px -15px rgba(130,154,177, 0.15)` | Cards at rest |
| Large | `0 40px 80px -20px rgba(130,154,177, 0.15)` | Cards on hover, hero images |
| Strong | `0 20px 40px -20px rgba(73,99,118, 0.35)` | Emphasized panels |
| Carousel | `0 30px 60px -15px rgba(130,154,177, 0.3)` | Active carousel card |
| Logo | `0 4px 16px -10px rgba(31,42,51, 0.6)` | Small branded elements |
| Glow | `0 0 8px rgba(133,150,164, 0.6)` | Particle/ambient effects |
| Hero drop | `drop-shadow(0 10px 40px rgba(96,165,250, 0.5))` | Hero floating elements |

## Transparency Layers

```css
/* Glass effect (navbar) */
background: var(--color-paper) / 70%;   /* Tailwind: bg-[var(--color-paper)]/70 */
backdrop-filter: blur(40px);            /* Tailwind: backdrop-blur-2xl */

/* Subtle overlay */
background: rgba(0, 0, 0, 0.10);       /* Image hover overlay */

/* Accent tint */
background: var(--color-accent) / 5%;   /* Tailwind: bg-[var(--color-accent)]/5 */

/* Muted tint */
background: var(--color-muted) / 40%;   /* Border/line variants */
```

## Tailwind Config Extension

```js
// tailwind.config.ts
module.exports = {
  theme: {
    extend: {
      colors: {
        paper: '#E6EBED',
        ink: '#1F2A33',
        surface: '#F2F5F7',
        muted: '#627C8F',
        accent: '#496376',
        line: 'rgba(98, 124, 143, 0.25)',
        hero: {
          bg: '#0A1015',
          text: '#D4DEE5',
          secondary: '#829AB1',
          highlight: '#60A5FA',
        },
      },
      boxShadow: {
        subtle: '0 1px 3px rgba(130,154,177, 0.05)',
        card: '0 20px 40px -15px rgba(130,154,177, 0.15)',
        'card-hover': '0 40px 80px -20px rgba(130,154,177, 0.15)',
        strong: '0 20px 40px -20px rgba(73,99,118, 0.35)',
        carousel: '0 30px 60px -15px rgba(130,154,177, 0.3)',
      },
    },
  },
};
```
