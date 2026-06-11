# Product Requirements Document
## Samir Akkawi Jewelry — New Website

**Version:** 1.0  
**Date:** 2026-06-11  
**Stack:** Astro 5 · Static · GitHub Pages  
**Design direction:** Dark & Luxurious  
**Source analysis:** [akkawi-jewelry-site-analysis.md](../akkawi-jewelry-site-analysis.md)  
**Design tokens:** [design-tokens.md](design-tokens.md)  
**Brand voice:** [brand-voice.md](brand-voice.md)

---

## 1. Project Goals

| Goal | Measure |
|---|---|
| Replace broken Wix site with a clean, fast, maintainable static site | Deploys successfully to GitHub Pages |
| Fix all structural bugs from the old site | No broken links, no typo slugs, Gold Collection fully built |
| Present the brand as high-end and trustworthy | Design passes luxury brand visual audit (see Section 9) |
| Give customers a clear path to contact the store | Contact CTA present on every page; WhatsApp link on mobile |
| Load fast on mobile in Jordan (variable connectivity) | Lighthouse Performance ≥ 90 on mobile |

---

## 2. User Personas

### Primary: The Milestone Buyer
- Buying for an engagement, wedding, or birthday
- Trusts word-of-mouth; researches before visiting the store
- Uses mobile (likely) or desktop
- Wants to see what the store carries and verify legitimacy before visiting

### Secondary: The Returning Customer
- Already bought from Akkawi, looking to browse new pieces or get a repair
- Wants contact info and service details quickly

### Out of scope
- International buyer expecting online checkout — this is a brochure site; no e-commerce

---

## 3. Site Architecture

```
/ (Home)
├── /about
├── /services
├── /policies
├── /contact
└── /collections
    ├── /collections/diamond
    │   ├── /collections/diamond/rings
    │   ├── /collections/diamond/necklaces
    │   ├── /collections/diamond/bracelets
    │   ├── /collections/diamond/solitaire
    │   ├── /collections/diamond/earrings
    │   └── /collections/diamond/pendants
    └── /collections/gold
        ├── /collections/gold/rings
        ├── /collections/gold/earrings
        ├── /collections/gold/bracelets
        └── /collections/gold/necklaces
```

All slugs are clean and semantic. No "copy-of-*" patterns, no typos.

---

## 4. Page Requirements

### 4.1 Home (`/`)

**Purpose:** First impression. Establish brand, build trust, direct to collections or contact.

**Layout pattern:** Scroll-Triggered Storytelling + Hero + Social Proof  
*(Source: ui-ux-pro-max landing.csv — #10 Scroll-Triggered Storytelling)*

**Sections (in order):**

| Section | Content | Notes |
|---|---|---|
| **Hero** | Full-width image, headline: *"Jewelry You'll Always Want to Wear"*, sub-headline (1 line), CTA: "Explore Collections" | Dark overlay on image; gold CTA button |
| **Brand Story** | Heading + 2–3 paragraphs. 30+ year origin story. | Scroll-reveal animation on text |
| **Collections Preview** | Two large tiles: Diamond Collection / Gold Collection, each with image + short description + "Explore" link | Equal-weight tiles |
| **Services Strip** | 4 icons with short labels: Diamond Jewelry · Gold Jewelry · Repair · Appraisals | Horizontal row on desktop, 2×2 grid on mobile |
| **Testimonials** | 3–5 customer quotes, name + city | Requires client to supply 2–4 additional quotes beyond the existing one |
| **Contact Strip** | Address, phone (with WhatsApp link), email, map link | Sticky CTA on mobile: "Contact Us" |
| **Footer** | Logo, nav links, socials, copyright (auto-update year) | |

---

### 4.2 About (`/about`)

**Purpose:** Brand story, values, human connection.

**Sections:**
- Hero banner image (store or jewelry photo)
- Heading: *"When Creativity and Quality Meet"*
- Brand narrative (from existing site, refined)
- Values list: 6 items (keep existing, improve formatting)
- Optional: store/Samir photo

---

### 4.3 Services (`/services`)

**Purpose:** Explain what the store offers.

**Sections:**
- Page heading + intro paragraph
- 4-tile grid: Diamond Jewelry · Gold Jewelry · Repair & Maintenance · Appraisals & Consultancy
- Each tile: image, title, 2–3 sentence description

---

### 4.4 Policies (`/policies`)

**Purpose:** Build trust through transparent policies. Scannable.

**Sections:**
- Diamond Jewelry Exchange & Returns (30-day free; after: 30% return / 15% exchange)
- Gold Jewelry Exchange & Returns (market price; deductions for manufacturing + stones)
- Warranty (market-price guarantee + complimentary polishing/service)

**Format:** Accordion or clearly separated cards. No walls of text.

---

### 4.5 Contact (`/contact`)

**Purpose:** Make it easy to reach the store.

**Sections:**
- Contact form: Name, Email, Phone, Subject, Message
- Store details: address, phone (WhatsApp link), email
- Embedded map or address block (Google Maps link)
- Social links: Facebook, Instagram

**Note:** Form needs a backend or static form service (Formspree, Netlify Forms, or similar) — GitHub Pages has no server. Decide before building the form component.

---

### 4.6 Collections Hub (`/collections`)

**Purpose:** Routing page. Two choices only.

**Layout:** Two large equal tiles, full-height on desktop. Image + label + description + CTA.

---

### 4.7 Diamond Collection (`/collections/diamond`)

**Purpose:** Category index for diamond pieces.

**Layout:** 6-tile image grid. Each tile: category image + label + link.

**Categories:** Rings · Necklaces · Bracelets · Solitaire · Earrings · Pendants

---

### 4.8 Diamond Category Pages (e.g. `/collections/diamond/rings`)

**Purpose:** Gallery of pieces in this category.

**Layout:** Masonry or grid of product photos. No pricing. No individual product pages (brochure site). Optional: short intro paragraph.

**Content:** Photography from client.

---

### 4.9 Gold Collection + Category Pages

Same structure as Diamond. **Content is entirely missing** — client must supply photography before these pages can be built.

---

## 5. Design System

### 5.1 Visual Style

**Primary style:** Dark & Luxurious  
**Source match:** "Luxury/Premium Brand" (ui-ux-pro-max products.csv #35)  
Liquid Glass-inspired surfaces on near-black background. Gold accent only — never overused.

**Anti-patterns to avoid:**
- Yellow or bright gold (use `#C9A84C`, never `#FFD700`)
- Emojis as icons — use SVG (Heroicons or Lucide)
- Glassmorphism on body text — glass effects for overlays/cards only
- Scale-on-hover layout shift — use `opacity` / `color` transitions only

---

### 5.2 Color Tokens

| Token | Value | Source |
|---|---|---|
| `--color-bg` | `#0F0F0F` | Dark base |
| `--color-surface` | `#1A1A1A` | Cards, nav |
| `--color-border` | `#2C2C2C` | Dividers |
| `--color-gold` | `#C9A84C` | Extracted from logo |
| `--color-gold-light` | `#D4B86A` | Hover states |
| `--color-gold-dim` | `#8A7235` | Muted accent on light |
| `--color-text` | `#F0EBE0` | Primary text |
| `--color-text-muted` | `#9A9585` | Secondary text |
| `--color-white` | `#FFFFFF` | Overlays |

*Skill reference palette (Luxury/Premium Brand):* `#1C1917` · `#44403C` · `#CA8A04` · `#FAFAF9` — consistent with our token set.

**Accessibility:** All text/background combinations must meet WCAG AA (4.5:1). Verify `--color-text-muted` against `--color-bg` before use.

---

### 5.3 Typography

**Pairing:** Luxury Serif  
*(Source: ui-ux-pro-max typography.csv #12 — explicitly listed for jewelry)*

| Role | Font | Weight |
|---|---|---|
| Display / Headlines | Cormorant Garamond | 300, 400, 600 |
| Body / UI | DM Sans | 300, 400, 500 |

```
Google Fonts import:
https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap
```

**Rules:**
- Body text minimum 16px (mobile)
- Line height 1.6–1.75 for body
- Max line length 65–75 characters
- Serif for page/section headings only; DM Sans for all UI text, nav, labels, buttons

---

### 5.4 Spacing Scale

4px base unit. See [design-tokens.md](design-tokens.md) for full table.

---

### 5.5 Motion

- Micro-interactions: 150–200ms, `ease-out`
- Scroll reveals: 300ms, `ease-out`, `translateY(20px) → 0`
- Page transitions: Astro ViewTransitions (fade, ~250ms)
- Respect `prefers-reduced-motion` — disable all non-essential animations

---

## 6. Component Inventory

| Component | Used On | Notes |
|---|---|---|
| `BaseLayout` | All pages | `<head>`, nav, footer, Google Fonts |
| `CollectionLayout` | Collection pages | Extends Base; adds breadcrumb |
| `Nav` | All pages | Logo + links + mobile hamburger |
| `Footer` | All pages | Address, socials, auto-year copyright |
| `Hero` | Home | Full-width image, overlay, headline, CTA |
| `SectionHeading` | All pages | Heading + optional subtitle, consistent sizing |
| `CollectionTile` | Collections hub, category indexes | Image + label + CTA link |
| `CategoryGrid` | Diamond/Gold index pages | Grid of `CollectionTile` |
| `ProductGallery` | Category leaf pages | Masonry/grid of photos |
| `ServiceCard` | Services page | Image + title + description |
| `TestimonialBlock` | Home | Quote + name + city |
| `PolicyAccordion` | Policies page | Expandable policy sections |
| `ContactForm` | Contact page | Name, Email, Phone, Subject, Message |
| `Button` | Site-wide | Primary (gold filled) + Ghost (gold outline) variants |

---

## 7. Technical Requirements

### 7.1 Astro-specific

| Requirement | Rule | Why |
|---|---|---|
| Zero client-side JS by default | No `client:*` directives unless needed | Performance; this is a static brochure |
| Image optimization | Use `<Image />` from `astro:assets` for all local images | WebP output, lazy loading |
| Content collections | Product categories defined as Astro collections with Zod schema | Type safety, easy to update |
| ViewTransitions | `<ViewTransitions />` in `BaseLayout` head | Smooth page-to-page navigation |
| Scoped styles | `<style>` in each `.astro` file | Prevents leakage |
| CSS tokens in `:root` | `tokens.css` imported globally via `BaseLayout` | Single source of truth |

### 7.2 GitHub Pages

- `site` and `base` set in `astro.config.mjs` before first deploy
- GitHub Actions workflow: `.github/workflows/deploy.yml` — build on push to `main`, deploy `dist/` to `gh-pages`
- Enable Pages in repo Settings → Pages → Source: `gh-pages` branch

### 7.3 Contact Form

GitHub Pages has no server. Options (decide before building):
- **Formspree** — free tier, no backend needed, redirects after submit
- **Netlify Forms** — if hosting moves to Netlify
- Static: `mailto:` link as fallback

---

## 8. Content Requirements

### Must-have before launch

- [ ] Logo with transparent background (PNG) — current logo has white bg, breaks on dark site
- [ ] Gold collection photography (any categories)
- [ ] 3–5 testimonials (currently only 1)
- [ ] Confirm WhatsApp number (same as `+962 795800651`?)

### Nice-to-have

- [ ] Store/exterior photo for About page
- [ ] Short video clip for Home hero (optional)

---

## 9. Quality Checklist (Pre-Launch)

### Visual
- [ ] No emojis used as icons — SVG only
- [ ] Hover states use `color`/`opacity` transitions only (no layout shift)
- [ ] Logo legible on dark background
- [ ] Gold used as accent — not dominant

### Accessibility
- [ ] WCAG AA contrast on all text/bg combinations
- [ ] All images have descriptive `alt` text
- [ ] Form inputs have `<label>` elements
- [ ] Keyboard-navigable (tab order matches visual order)
- [ ] `prefers-reduced-motion` disables scroll animations

### Performance
- [ ] Lighthouse mobile Performance ≥ 90
- [ ] All images use `<Image />` component (WebP + lazy)
- [ ] Google Fonts loaded with `display=swap`
- [ ] No unnecessary `client:` directives

### Responsive
- [ ] Tested at 375px, 768px, 1024px, 1440px
- [ ] No horizontal scroll on mobile
- [ ] Touch targets ≥ 44×44px
- [ ] Nav collapses to hamburger on mobile

### Functional
- [ ] All nav links resolve correctly
- [ ] Contact form submits (or has working fallback)
- [ ] WhatsApp link opens on mobile
- [ ] Copyright year is dynamic (not hardcoded 2022)
- [ ] `sitemap.xml` generated (Astro sitemap integration)

---

## 10. Out of Scope

- E-commerce / shopping cart
- Product pricing display
- CMS or admin interface
- Multiple languages (Arabic + English bilingual site)
- Individual product detail pages

---

## 11. Build Order

1. `BaseLayout` + `tokens.css` + `global.css` + `Nav` + `Footer`
2. Home page (hero, story, collections preview, testimonials, contact strip)
3. About + Services + Policies (simpler pages, reuse components)
4. Collections hub + Diamond category index + Diamond leaf pages
5. Contact page + form wiring
6. Gold collection (once photography available)
7. GitHub Actions deploy workflow
8. Pre-launch quality pass (Section 9)
