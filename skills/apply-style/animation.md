# Animation & Motion

## Signature Easing

The entire system uses a single primary easing curve for a snappy, buttery-smooth feel:

```css
cubic-bezier(0.16, 1, 0.3, 1)
```

This curve starts fast and decelerates gently — giving interactions a responsive "snap" followed by an elegant settle. Use it as the default for all component transitions.

Secondary easing for simpler transitions:
```css
ease-out
```

## Duration Scale

| Token | Value | Usage |
|-------|-------|-------|
| `duration-300` | 300ms | Quick micro-interactions: color changes, icon shifts |
| `duration-500` | 500ms | Medium transitions: tag hover, border changes, node states |
| `duration-700` | 700ms | **Standard** — card lifts, navbar changes, carousel slides, underline reveals |
| `duration-[1s]` | 1000ms | Slow transitions: nav indicator slide, decorative movements |
| `duration-[1.5s]` | 1500ms | Cinematic: image zoom on hover, hero entrance, project image scale |

### Choosing a Duration

- **Hover color/opacity**: 300ms
- **Component state changes**: 500–700ms
- **Layout/position animations**: 700ms
- **Background image transforms**: 1.5s
- **Staggered entrances**: 1.2–1.5s base + stagger delay

## Entrance Animation: fade-in-up

The primary entrance animation for elements appearing on screen.

```css
@keyframes fade-in-up {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in-up {
  animation: fade-in-up 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards;
}
```

### Staggered Entrance

Apply increasing delays to child elements for a cascading reveal:

```css
.stagger-1 { animation-delay: 0s; }
.stagger-2 { animation-delay: 0.5s; }
.stagger-3 { animation-delay: 1.0s; }
```

All staggered elements should start with `opacity: 0` and use `animation-fill-mode: forwards`.

### Tailwind Config

```js
// tailwind.config.ts
module.exports = {
  theme: {
    extend: {
      keyframes: {
        'fade-in-up': {
          from: { opacity: '0', transform: 'translateY(30px)' },
          to: { opacity: '1', transform: 'translateY(0)' },
        },
      },
      animation: {
        'fade-in-up': 'fade-in-up 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards',
      },
    },
  },
};
```

## Hover Effects

### Card Lift

```css
/* Card rises on hover */
transform: translateY(0);
transition: all 700ms cubic-bezier(0.16, 1, 0.3, 1);

&:hover {
  transform: translateY(-16px);  /* -translate-y-4 */
}
```

Smaller variant for compact cards: `translateY(-8px)` (`-translate-y-2`).

### Image Zoom

```css
/* Image scales gently within its container */
transform: scale(1);
transition: transform 1.5s ease-out;

&:hover {
  transform: scale(1.05);
}
```

Container must have `overflow: hidden` and matching `border-radius`.

### Scale Pop

```css
/* Element slightly enlarges */
transition: transform 300ms ease-out;

&:hover {
  transform: scale(1.05);
}
```

Used for buttons, small interactive elements.

### Underline Reveal

```css
/* Line grows from left to right */
.underline-bar {
  width: 0;
  height: 1px;
  background: var(--color-accent);
  transition: width 700ms cubic-bezier(0.16, 1, 0.3, 1);
}

&:hover .underline-bar {
  width: 100%;
}
```

### Icon Shift

```css
/* Arrow or icon moves right on hover */
transition: transform 500ms ease-out;

&:hover {
  transform: translateX(4px);  /* translate-x-1 */
}
```

Larger variant: `translateX(12px)` (`translate-x-3`).

### Opacity Fade-in

```css
/* Element fades in on group hover */
opacity: 0;
transition: opacity 500ms ease-out;

.group:hover & {
  opacity: 1;
}
```

## Continuous Animations

### Scroll Indicator Bounce

```css
@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-8px); }
}

animation: bounce 2.5s ease-in-out infinite;
```

### Pulse (Sleeping Cat)

```css
animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
```

Standard Tailwind `animate-pulse`.

### Fade Out (Ephemeral Text)

```css
@keyframes fade-out {
  from { opacity: 1; }
  to { opacity: 0; }
}

animation: fade-out 3s ease-out forwards;
```

## Transition Shorthand Reference

```css
/* Standard component transition */
transition: all 700ms cubic-bezier(0.16, 1, 0.3, 1);

/* Quick color-only */
transition: color 300ms ease-out;

/* Transform + opacity */
transition: transform 700ms cubic-bezier(0.16, 1, 0.3, 1),
            opacity 500ms ease-out;

/* Cinematic image */
transition: transform 1.5s cubic-bezier(0.16, 1, 0.3, 1);
```

## Intersection Observer Pattern

Elements should animate in when they enter the viewport. A simple pattern:

```tsx
// Start hidden
<div className="opacity-0 translate-y-8">

// On intersection, add:
className="opacity-100 translate-y-0 transition-all duration-700 ease-[cubic-bezier(0.16,1,0.3,1)]"
```

Or use the `animate-fade-in-up` class with `animation-play-state: paused` until observed.
