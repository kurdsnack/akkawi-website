# Design Tokens — Samir Akkawi Jewelry

> **Status: Decided.** All CSS must reference these tokens — no raw color or font values in components.

---

## Color palette — Dark & Luxurious

Extracted from `akkawi-logo-3.jpg`. The logo gold is warm and slightly desaturated — not yellow, not orange.

| Token | Value | Usage |
|---|---|---|
| `--color-gold` | `#C9A84C` | Primary accent — CTAs, borders, highlights, logo tint |
| `--color-gold-light` | `#D4B86A` | Hover states, subtle shimmer |
| `--color-gold-dim` | `#8A7235` | Gold used on light surfaces or as a muted accent |
| `--color-bg` | `#0F0F0F` | Main page background |
| `--color-surface` | `#1A1A1A` | Cards, nav, elevated surfaces |
| `--color-border` | `#2C2C2C` | Subtle dividers, card outlines |
| `--color-text` | `#F0EBE0` | Primary text — warm off-white, not pure white |
| `--color-text-muted` | `#9A9585` | Secondary text, captions, labels |
| `--color-white` | `#FFFFFF` | Overlays, logo background fill |

---

## Typography

| Token | Value | Usage |
|---|---|---|
| `--font-serif` | `'Cormorant Garamond', Georgia, serif` | Headlines, brand name, pull quotes |
| `--font-sans` | `'DM Sans', system-ui, sans-serif` | Body text, nav, labels, buttons |
| `--font-size-base` | `16px` | Body baseline |

Both via Google Fonts. Import string:
```
https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap
```

---

## Spacing scale (4px base unit)

| Token | Value | Usage |
|---|---|---|
| `--space-1` | `4px` | Tight gaps |
| `--space-2` | `8px` | Icon padding, small gaps |
| `--space-3` | `16px` | Component internal padding |
| `--space-4` | `24px` | Section internal spacing |
| `--space-5` | `40px` | Between components |
| `--space-6` | `64px` | Section padding (mobile) |
| `--space-7` | `96px` | Section padding (desktop) |
| `--space-8` | `128px` | Hero / large section breathing room |

---

## Notes
- **Logo:** `public/assets/images/brand/akkawi-logo-3.jpg` — gold on white, circular. On dark backgrounds, display inside a dark `--color-surface` circle, or request a transparent-bg PNG from the client.
- **Arabic text in logo:** The logo is bilingual (English + Arabic). If site copy ever goes bilingual, font stack will need an Arabic web font (e.g. Cairo, Tajawal from Google Fonts).
- Product photography: partial (diamond collection from old Wix site). Gold collection missing.
