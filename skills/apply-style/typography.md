# Typography

## Font Family Stacks

```css
:root {
  --font-sans: "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;

  --font-serif: "Noto Serif CJK SC", "Source Han Serif SC", "Songti SC",
    STSong, "Times New Roman", Times, serif;

  --font-mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas,
    "Liberation Mono", "Courier New", monospace;
}
```

### Usage Rules

| Stack | When to use |
|-------|-------------|
| **Sans** (`--font-sans`) | Body text, UI elements, buttons, navigation labels |
| **Serif** (`--font-serif`) | Headlines, article titles, pull quotes, hero text, decorative numerals |
| **Mono** (`--font-mono`) | Tags, metadata, timestamps, code, small uppercase labels |

### Font Loading (Next.js)

```tsx
import { Inter } from "next/font/google";

const inter = Inter({
  subsets: ["latin"],
  variable: "--font-inter",
  display: "swap",
});

// Apply to <html>: className={inter.variable}
```

For non-Next.js projects, import Inter from Google Fonts:
```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;700&display=swap" rel="stylesheet">
```

## Size Scale

### Display Sizes (responsive)

| Token | Mobile | Tablet (md) | Desktop (lg) | Usage |
|-------|--------|-------------|---------------|-------|
| Hero title | `text-4xl` | `text-[5.5rem]` | `text-[7rem]` | Main hero headline |
| Section heading | `text-4xl` | `text-[4rem]` | `text-[6rem]` | Page section titles |
| Project title | `text-5xl` | `text-[5rem]` | — | Featured project names |

### Content Sizes

| Token | Size | Usage |
|-------|------|-------|
| Card title | `text-2xl` → `text-3xl` | Blog cards, project cards |
| Subtitle | `text-lg` → `text-xl` | Section descriptions, intros |
| Body | `text-base` → `text-lg` | Paragraph text |
| Body small | `text-sm` → `text-base` | Secondary descriptions |
| Caption | `text-[13px]` | Image captions, helper text |

### Micro Sizes (metadata, labels)

| Token | Size | Usage |
|-------|------|-------|
| Tag | `text-[10px]` | Category tags, badges |
| Meta small | `text-[9px]` | Small uppercase labels |
| Tiny | `text-[8px]` | Smallest annotations |

## Font Weights

The system is intentionally lightweight. Most text uses `font-light` (300).

| Weight | Value | Usage |
|--------|-------|-------|
| `font-light` | 300 | **Default** — body text, card titles, section headings, most elements |
| `font-normal` | 400 | Monospace text, tags, metadata |
| `font-medium` | 500 | Active navigation states, inline emphasis, timeline year numbers |
| `font-bold` | 700 | Hero title only |

## Letter Spacing

| Token | Value | Usage |
|-------|-------|-------|
| `tracking-tighter` | -0.05em | Large display headings |
| `tracking-[0.05em]` | 0.05em | Minimal expansion for body |
| `tracking-[0.1em]` | 0.1em | Subtitles, secondary headings |
| `tracking-[0.12em]` | 0.12em | Subtitle badges |
| `tracking-[0.15em]` | 0.15em | Medium-spaced labels |
| `tracking-[0.2em]` | 0.2em | **Standard tag/label spacing** |
| `tracking-[0.3em]` | 0.3em | Metadata, year labels |
| `tracking-[0.4em]` | 0.4em | Logo text, brand elements |
| `tracking-widest` | 0.1em+ | Download buttons, maximally spaced text |

## Line Heights

| Token | Value | Usage |
|-------|-------|-------|
| `leading-none` | 1.0 | Oversized display headings |
| `leading-[0.9]` | 0.9 | Tight multi-line headlines |
| `leading-snug` | 1.375 | Card titles |
| `leading-[1.3]` | 1.3 | Article headings |
| `leading-normal` | 1.5 | Default body text |
| `leading-relaxed` | 1.625 | Comfortable body paragraphs |
| `leading-[1.8]` | 1.8 | Slogan/tagline text |
| `leading-[2.1]` | 2.1 | List items in timelines |
| `leading-[2.2]` | 2.2 | Loose editorial paragraphs |

## Text Transform Patterns

Tags, labels, and navigation items consistently use:
```css
text-transform: uppercase;
font-family: var(--font-mono);
letter-spacing: 0.2em;
font-size: 10px;
```

Tailwind shorthand:
```
font-mono text-[10px] uppercase tracking-[0.2em]
```

## Prose / Long-form Content

For article pages using Tailwind Typography:

```
prose prose-lg md:prose-xl
prose-headings:font-serif prose-headings:font-medium
prose-p:font-light prose-p:leading-relaxed prose-p:text-[var(--color-ink)]/80
prose-a:text-[var(--color-accent)] prose-a:font-medium prose-a:no-underline hover:prose-a:underline
prose-blockquote:border-l-[var(--color-accent)] prose-blockquote:bg-[var(--color-accent)]/5 prose-blockquote:font-serif prose-blockquote:italic
prose-code:text-[var(--color-accent)] prose-code:bg-[var(--color-paper)] prose-code:px-1 prose-code:rounded
```
