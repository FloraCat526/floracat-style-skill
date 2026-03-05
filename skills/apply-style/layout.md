# Layout & Responsive Design

## Container Widths

| Token | Value | Usage |
|-------|-------|-------|
| `max-w-sm` | 384px | Narrow content (forms, alerts) |
| `max-w-md` | 448px | Medium panels |
| `max-w-2xl` | 672px | Narrow article body |
| `max-w-3xl` | 768px | Article containers, centered content |
| `max-w-5xl` | 1024px | Hero sections, feature grids |
| `max-w-6xl` | 1152px | Wide sections |
| `max-w-7xl` | 1280px | Full-width sections with padding |
| `max-w-[1400px]` | 1400px | Absolute max page width |

All containers are centered with `mx-auto` and have horizontal padding: `px-6 md:px-8 lg:px-12`.

## Section Spacing

Vertical rhythm between major sections:

| Context | Padding | Tailwind |
|---------|---------|----------|
| Standard section | 80–96px top/bottom | `py-20 md:py-24` |
| Large section | 96–128px top/bottom | `py-24 md:py-32` |
| Hero / immersive | 96–160px top/bottom | `py-24 md:py-40` |
| Between elements (within section) | 32–48px | `space-y-8 md:space-y-12` |

## Spacing Scale

The system follows Tailwind's default 4px base unit. Commonly used spacings:

| Value | Pixels | Typical use |
|-------|--------|-------------|
| `gap-2` | 8px | Tight element spacing |
| `gap-4` | 16px | Compact grids |
| `gap-6` | 24px | QR code grids, tight lists |
| `gap-8` | 32px | Standard card grid gap |
| `gap-12` | 48px | Wide card grid gap |
| `gap-16` | 64px | Timeline items, generous grids |
| `gap-24` | 96px | Large feature sections |

## Grid Systems

### Blog Card Grid

```
grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 md:gap-12
```

Three equal columns on desktop, two on tablet, stacked on mobile.

### Article / Feature Grid

```
grid grid-cols-1 md:grid-cols-3 gap-12
```

Three columns starting at tablet.

### Timeline Grid

```
grid grid-cols-1 md:grid-cols-3 gap-16 md:gap-12
```

Wider gaps on mobile (stacked), tighter on tablet+ (side by side).

### Two-Column Feature

```
grid grid-cols-1 lg:grid-cols-2 gap-16 md:gap-24
```

Side-by-side on large screens with generous gap.

### Icon / Small Item Grid

```
grid grid-cols-2 md:grid-cols-4 gap-6 md:gap-8
```

## Flexbox Patterns

### Centered Column (Section)

```
flex flex-col items-center text-center
```

Most section headers use this pattern.

### Space-Between Row (Navbar)

```
flex items-center justify-between
```

### Project Layout (Text + Image)

```
flex flex-col lg:flex-row items-start gap-12 lg:gap-24
```

Text takes `lg:w-[40%]`, image takes `lg:w-[60%]`. Alternate with `lg:flex-row-reverse` for visual rhythm.

## Responsive Breakpoints

The system uses Tailwind's mobile-first breakpoints:

| Breakpoint | Min-width | Usage |
|------------|-----------|-------|
| (default) | 0px | Mobile layout: single column, compact spacing |
| `md:` | 768px | Tablet: multi-column grids, larger text, wider padding |
| `lg:` | 1024px | Desktop: full layouts, maximum container widths |

### Responsive Patterns

**Text scaling:**
```
text-4xl md:text-[5.5rem] lg:text-[7rem]   /* Hero */
text-4xl md:text-[4rem] lg:text-[6rem]     /* Section */
text-base md:text-lg                         /* Body */
```

**Padding scaling:**
```
px-6 md:px-8 lg:px-12      /* Horizontal */
py-20 md:py-24 lg:py-32    /* Vertical sections */
p-8 md:p-10                /* Card internal */
```

**Visibility toggles:**
```
hidden md:flex              /* Show nav items on tablet+ */
md:hidden                   /* Show hamburger on mobile only */
```

## Full-Bleed Sections

For immersive sections that span the full viewport:

```
w-full min-h-screen relative overflow-hidden
```

Content within is constrained by an inner container:
```
max-w-7xl mx-auto px-6 md:px-8
```

## Z-Index Layers

| Layer | Z-index | Usage |
|-------|---------|-------|
| Background | `z-0` | Decorative backgrounds, particle effects |
| Content | `z-10` | Standard content |
| Carousel hidden | `z-10` | Off-screen carousel items |
| Carousel adjacent | `z-20` | Flanking carousel items |
| Carousel active | `z-30` | Center carousel item |
| Navbar | `z-50` | Fixed navigation |
| Modal / Overlay | `z-[9999]` | Overlays, drawers |
