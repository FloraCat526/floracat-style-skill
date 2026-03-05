# FloraCat Design System

A Morandi gray-blue design language plugin for Claude Code. Instantly apply a refined, elegant visual style to any project — muted tones, light typography, fluid animations, and generous whitespace.

## Installation

### Option 1: Plugin directory flag

```bash
claude --plugin-dir ~/Desktop/floracat-design-system
```

### Option 2: Copy into your project

```bash
cp -r ~/Desktop/floracat-design-system/.claude-plugin /your/project/.claude-plugin
cp -r ~/Desktop/floracat-design-system/skills /your/project/.claude-plugin/skills
```

### Option 3: Symlink for all projects

```bash
ln -s ~/Desktop/floracat-design-system ~/.claude/plugins/floracat-design-system
```

## Usage

Once loaded, invoke the skill in any Claude Code session:

```
/floracat-design-system:apply-style Apply the Morandi gray-blue design to this project
```

Claude will:

1. Detect your tech stack (Next.js, Tailwind, plain CSS, Vue, etc.)
2. Add CSS custom properties for colors, typography, and shadows
3. Configure font imports (Inter + serif/mono stacks)
4. Apply component patterns (navbar, cards, buttons, etc.)
5. Wire up the signature animation system
6. Set up layout foundations and responsive breakpoints

## What's Included

| File | Content |
|------|---------|
| `color-system.md` | Full Morandi palette, gradients, shadows, transparency layers |
| `typography.md` | Font stacks, size scale, weight/spacing/line-height rules |
| `components.md` | Navbar, cards, buttons, timeline, carousel, badges |
| `animation.md` | Easing curves, durations, entrance effects, hover states |
| `layout.md` | Containers, spacing scale, grids, responsive breakpoints |

## Design Highlights

- **Palette**: 6 core CSS variables — `paper`, `ink`, `surface`, `muted`, `line`, `accent`
- **Easing**: Signature `cubic-bezier(0.16, 1, 0.3, 1)` across all motion
- **Typography**: Light weight (300) default, serif headlines, mono metadata
- **Shadows**: Blue-gray tinted — never pure black
- **Spacing**: Generous padding and relaxed line-heights for breathing room

## Tech Stack Compatibility

| Stack | Support |
|-------|---------|
| Next.js + Tailwind CSS | Full — outputs utility classes and config extensions |
| React + CSS Modules | Full — outputs CSS custom properties |
| Vue / Nuxt | Full — framework-agnostic CSS variables |
| Plain HTML/CSS | Full — raw CSS output |
| Svelte / SvelteKit | Full — CSS variables work natively |

## License

MIT — see [LICENSE](./LICENSE).
