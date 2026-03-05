# Component Patterns

## Navbar

### Structure

Fixed top navigation with glassmorphism background.

```
Height: 96px (h-24)
Padding: px-8 md:px-20
Background: var(--color-paper) at 70% opacity + backdrop-blur-2xl
Shadow: 0 1px 3px rgba(130,154,177, 0.05)
Z-index: 50
Layout: flex items-center justify-between
```

### Logo

```
Image: w-9 h-9 md:w-10 md:h-10, rounded-full, object-cover
Border: 1px solid var(--color-line)
Shadow: 0 4px 16px -10px rgba(31,42,51,0.6)

Brand text: font-serif font-light text-xl md:text-[22px] tracking-[0.4em]
Color: var(--color-ink)
```

### Navigation Items

```
Font: font-mono text-[10px] md:text-xs uppercase tracking-[0.2em]
Color: var(--color-muted)
Active: var(--color-ink)
Hover: var(--color-accent)
Spacing: space-x-16
Transition: transition-colors duration-300
```

### Active Indicator Line

```
Position: absolute bottom-0, centered
Height: 1px
Color: var(--color-accent)
Active: w-full opacity-100
Hover: w-full opacity-50
Transition: all 1s cubic-bezier(0.16, 1, 0.3, 1)
```

### Scroll Behavior

On scroll down, the navbar can optionally reduce height and increase shadow. Transition uses `duration-700 ease-[cubic-bezier(0.16,1,0.3,1)]`.

---

## Cards

### Blog / Article Card

```
Background: var(--color-surface)
Border: 1px solid var(--color-line)
Radius: 36px (rounded-3xl)
Padding: p-8 md:p-10
Shadow: 0 20px 40px -15px rgba(130,154,177, 0.15)

Hover:
  transform: translateY(-16px)
  Transition: all 700ms cubic-bezier(0.16, 1, 0.3, 1)
```

#### Card Image

```
Aspect: 16/9
Overflow: hidden
Radius: rounded-2xl (within the card)
Hover: scale(1.05), transition 1.5s ease-out
Overlay on hover: bg-black/10
```

#### Card Title

```
Font: font-serif font-light text-2xl md:text-3xl leading-snug
Color: var(--color-ink)
Hover: var(--color-accent)
Clamp: line-clamp-2
```

#### Card Tags

```
Font: font-mono text-[10px] uppercase tracking-[0.2em]
Border: 1px solid var(--color-line), rounded-full
Padding: px-3 py-1.5
Hover: bg-[var(--color-muted)] border-[var(--color-muted)] text-white
Transition: duration-500
```

### Product / Carousel Card

```
Width: 260px md:300px
Height: 520px md:600px
Radius: 48px (rounded-[3rem])
Border: 4px solid white
Shadow: 0 30px 60px -15px rgba(130,154,177, 0.3)
Background: gradient (varies per product)
```

#### Carousel States

```
Active (center):    scale(1),    opacity 1,   blur(0),    z-30
Adjacent (±1):      scale(0.75), opacity 0.4, blur(2px),  z-20
Hidden:             scale(0.5),  opacity 0,   blur(10px), z-10
Transition: all 700ms cubic-bezier(0.16, 1, 0.3, 1)
```

---

## Buttons

### Primary Button

```
Background: var(--color-ink)
Text: white, font-medium, tracking-widest
Padding: px-8 py-4
Radius: rounded-full
Hover: scale(1.05)
Ripple effect: inner span scale-0 → scale-100 bg-white/10
Transition: duration-300
```

### Secondary / Link Button

```
Font: font-mono text-[10px] uppercase tracking-widest
Color: var(--color-muted)
Hover: var(--color-ink)
Arrow icon: translateX(0) → translateX(4px) on hover
Transition: duration-500
```

### Explore / Underline Link

```
Text: font-mono text-[10px] uppercase tracking-[0.2em]
Underline: 1px solid var(--color-line), initially w-0
Hover: underline expands to w-full, color changes to var(--color-accent)
Transition: width 700ms cubic-bezier(0.16, 1, 0.3, 1)
```

---

## Timeline

### Horizontal Line

```
Height: 1px
Color: var(--color-line)
Gradient variant: linear-gradient(to right, var(--color-line), var(--color-muted)/40, transparent)
```

### Node

```
Size: 16px (w-4 h-4)
Background: var(--color-paper)
Border: 1px solid var(--color-line)
Inner dot: 6px (w-1.5 h-1.5), bg-[var(--color-muted)]
Hover: border-[var(--color-muted)], inner dot bg-[var(--color-ink)]
Transition: duration-500
```

### Year Label

```
Font: font-mono text-[9px] uppercase tracking-[0.3em]
Color: var(--color-muted)
Hover: var(--color-ink)
```

### Year Number

```
Font: font-serif font-medium text-3xl
Color: var(--color-ink)
```

### Mobile Active Indicator

```
Width: 2px
Color: var(--color-accent)
Transition: all 700ms ease-out
Animated from h-0 → h-full on hover
```

---

## Badges / Tags

### Standard Tag

```
Font: font-mono text-[9px] md:text-[10px] uppercase tracking-[0.2em] md:tracking-widest
Border: 1px solid var(--color-line)
Padding: px-3 py-1.5
Radius: rounded-full
Background: transparent or var(--color-surface)
```

### Active / Accent Tag

```
Border: 1px solid var(--color-accent)
Background: var(--color-accent) at 5% opacity
Color: var(--color-accent)
```

### Hover State

```
Background: var(--color-muted)
Border: var(--color-muted)
Text: white
Transition: all 500ms
```

---

## Project Showcase

### Image Container

```
Width: 100% lg:60%
Height: 400px md:650px
Radius: rounded-3xl
Shadow: 0 40px 80px -20px rgba(133,150,164, 0.15)
Hover: scale(1.02)
Transition: 1.5s cubic-bezier(0.16, 1, 0.3, 1)
```

### Project Title

```
Font: font-serif font-light text-5xl md:text-[5rem]
Color: var(--color-ink)
Hover: var(--color-accent)
Line-height: 0.9
Tracking: tighter
```
