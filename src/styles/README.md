# src/styles/

Global CSS. All design token values (colors, fonts, spacing) are defined here as CSS custom properties and referenced everywhere else — never hardcoded in components.

## Planned files
- `global.css` — CSS resets, base element styles, font imports
- `tokens.css` — `--color-*`, `--font-*`, `--spacing-*` custom properties

## Token reference
See [docs/design-tokens.md](../../docs/design-tokens.md) for the values and decisions behind each token.

## Import order
`tokens.css` must be imported before `global.css`. Both are imported once in `BaseLayout.astro`.
