# .github/workflows/

GitHub Actions CI/CD.

## Planned workflow: `deploy.yml`
Triggers on push to `main`. Steps:
1. Checkout repo
2. Install Node + Astro dependencies
3. Run `astro build`
4. Push `dist/` output to the `gh-pages` branch

This file doesn't exist yet — create it when the site is ready for its first deploy.

## Before first deploy
- Set `site` in `astro.config.mjs` (e.g. `https://yourusername.github.io`)
- Set `base` if deploying to a sub-path (e.g. `/akkawi-website`)
- Enable GitHub Pages in repo Settings → Pages → Source: `gh-pages` branch
