# Design System — MASTER
## Samir Akkawi Jewelry

> Source of truth for all visual decisions. Page-specific overrides live in `design-system/pages/`.  
> Generated via ui-ux-pro-max skill data + project analysis.

---

## Pattern

**Product type:** Luxury/Premium Brand  
**Primary pattern:** Storytelling-Driven + Feature-Rich Showcase  
**Style:** Dark & Luxurious (Liquid Glass-inspired surfaces on near-black)  
**Era:** Contemporary luxury editorial (2020s)

---

## Colors

```css
:root {
  /* Backgrounds */
  --color-bg:          #0F0F0F;  /* Main page bg */
  --color-surface:     #1A1A1A;  /* Cards, nav, elevated */
  --color-border:      #2C2C2C;  /* Dividers, outlines */

  /* Gold accent — extracted from logo #akkawi-logo-3.jpg */
  --color-gold:        #C9A84C;  /* Primary accent */
  --color-gold-light:  #D4B86A;  /* Hover states */
  --color-gold-dim:    #8A7235;  /* Gold on light surfaces */

  /* Text */
  --color-text:        #F0EBE0;  /* Primary — warm off-white */
  --color-text-muted:  #9A9585;  /* Secondary, captions */
  --color-white:       #FFFFFF;  /* Overlays, logo fill */
}
```

**Skill reference match:** Luxury/Premium Brand palette — `#1C1917` · `#CA8A04` · `#FAFAF9`

---

## Typography

**Pairing:** Luxury Serif (ui-ux-pro-max typography.csv #12)  
*Explicitly recommended for jewelry brands.*

```css
/* Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap');

:root {
  --font-serif: 'Cormorant Garamond', Georgia, serif;
  --font-sans:  'DM Sans', system-ui, sans-serif;
  --font-size-base: 16px;
  --line-height-body: 1.65;
  --line-length-max: 68ch;
}
```

| Use | Font | Weight |
|---|---|---|
| Page titles, section headings | Cormorant Garamond | 300–600 |
| Pull quotes, hero sub-headline | Cormorant Garamond italic | 300i |
| Nav, body, labels, buttons | DM Sans | 300–500 |
| Captions, metadata | DM Sans | 300 |

---

## Spacing

4px base unit.

```css
:root {
  --space-1:  4px;
  --space-2:  8px;
  --space-3:  16px;
  --space-4:  24px;
  --space-5:  40px;
  --space-6:  64px;   /* Section padding mobile */
  --space-7:  96px;   /* Section padding desktop */
  --space-8:  128px;  /* Hero breathing room */
}
```

---

## Effects

```css
:root {
  /* Transitions */
  --transition-fast:   150ms ease-out;
  --transition-base:   200ms ease-out;
  --transition-slow:   300ms ease-out;

  /* Borders */
  --radius-sm:   4px;
  --radius-md:   8px;
  --radius-lg:   16px;
  --radius-full: 9999px;

  /* Gold glow — use sparingly on CTAs */
  --shadow-gold: 0 0 24px rgba(201, 168, 76, 0.25);

  /* Surface shadow */
  --shadow-card: 0 4px 24px rgba(0, 0, 0, 0.4);
}
```

---

## Motion

- Micro-interactions: `var(--transition-fast)` — color, opacity, border
- Scroll reveals: `translateY(20px) → 0`, `opacity 0 → 1`, 300ms
- Page transitions: Astro ViewTransitions, fade ~250ms
- `@media (prefers-reduced-motion: reduce)` → disable all non-essential animations

---

## Component Patterns

### Button — Primary
```css
.btn-primary {
  background: var(--color-gold);
  color: var(--color-bg);
  font-family: var(--font-sans);
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  font-size: 0.8rem;
  padding: var(--space-3) var(--space-5);
  border-radius: var(--radius-sm);
  transition: background var(--transition-fast);
  cursor: pointer;
}
.btn-primary:hover {
  background: var(--color-gold-light);
}
```

### Button — Ghost
```css
.btn-ghost {
  background: transparent;
  color: var(--color-gold);
  border: 1px solid var(--color-gold);
  /* same typography as primary */
  transition: color var(--transition-fast), background var(--transition-fast);
}
.btn-ghost:hover {
  background: rgba(201, 168, 76, 0.08);
}
```

### Card
```css
.card {
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-card);
  transition: border-color var(--transition-base);
}
.card:hover {
  border-color: var(--color-gold-dim);
}
```

---

## Anti-Patterns

- Never use `#FFD700` (bright yellow-gold) — use `--color-gold` only
- Never use emojis as icons — SVG (Heroicons or Lucide)
- Never `transform: scale()` on hover — causes layout shift
- Never `backdrop-filter` on body text — glass effects for overlays only
- Never hardcode color values — reference tokens only
- Never `client:load` on static components

---

## Page Overrides

See `design-system/pages/` for any page-specific deviations.  
If no file exists for a page, this MASTER applies entirely.
