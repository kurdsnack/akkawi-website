# Akkawi Jewelry — Project Map

## Project overview
Static brochure site for Samir Akkawi Jewelry (Amman, Jordan). Built with **Astro**, deployed to **GitHub Pages**. No e-commerce — customers browse, then contact the store directly.

Source analysis: [akkawi-jewelry-site-analysis.md](akkawi-jewelry-site-analysis.md)

---

## Folder map

| Path | Purpose |
|---|---|
| `src/pages/` | All routes. One `.astro` file = one URL. Mirrors the site nav. |
| `src/layouts/` | Page shell templates (header, footer, `<head>`). |
| `src/components/` | Reusable UI pieces — nav, cards, contact form, etc. |
| `src/styles/` | Global CSS, design tokens (colors, fonts, spacing). |
| `src/content/` | Astro content collections — product/category data as Markdown or JSON. |
| `public/` | Static assets served as-is (images, fonts, favicons). |
| `docs/` | Non-code project docs: brand voice, design decisions, content strategy. |
| `.github/workflows/` | GitHub Actions CI/CD — build and deploy to Pages on push to `main`. |

---

## Page routing

```
src/pages/
├── index.astro              →  /
├── about.astro              →  /about
├── services.astro           →  /services
├── policies.astro           →  /policies
├── contact.astro            →  /contact
└── collections/
    ├── index.astro          →  /collections
    ├── diamond/
    │   ├── index.astro      →  /collections/diamond
    │   ├── rings.astro      →  /collections/diamond/rings
    │   ├── necklaces.astro  →  /collections/diamond/necklaces
    │   ├── bracelets.astro  →  /collections/diamond/bracelets
    │   ├── solitaire.astro  →  /collections/diamond/solitaire
    │   ├── earrings.astro   →  /collections/diamond/earrings
    │   └── pendants.astro   →  /collections/diamond/pendants
    └── gold/
        ├── index.astro      →  /collections/gold
        ├── rings.astro      →  /collections/gold/rings
        ├── earrings.astro   →  /collections/gold/earrings
        ├── bracelets.astro  →  /collections/gold/bracelets
        └── necklaces.astro  →  /collections/gold/necklaces
```

---

## Key docs (read these when making brand/content decisions)

- [docs/PRD.md](docs/PRD.md) — full product requirements, page specs, build order, launch checklist
- [design-system/MASTER.md](design-system/MASTER.md) — design system source of truth (colors, type, spacing, component patterns)
- [docs/brand-voice.md](docs/brand-voice.md) — tone, language rules, what the brand sounds like
- [docs/design-tokens.md](docs/design-tokens.md) — color/font token values
- [docs/content-strategy.md](docs/content-strategy.md) — what copy/content goes on each page

---

## Astro conventions

- Any `.md` or `.astro` file in `src/pages/` becomes a URL route — keep only actual pages there
- Prefix non-route files in `src/pages/` with `_` (e.g. `_README.md`) — Astro skips them
- READMEs in other `src/` subfolders (components, layouts, etc.) are fine — Astro only auto-routes from `src/pages/`

---

## Deployment

- Target: GitHub Pages via GitHub Actions
- Workflow: `.github/workflows/deploy.yml`
- Build output: `dist/` (Astro default) → pushed to `gh-pages` branch
- Config: `astro.config.mjs` — set `site` and `base` before first deploy
