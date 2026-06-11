# src/content/

Astro content collections. Structured data (Markdown or JSON) that pages pull from — keeps copy and data out of `.astro` files.

## Planned collections

### `collections/` — product category data
Each category (rings, necklaces, etc.) gets a Markdown file with frontmatter:
```md
---
title: Diamond Rings
collection: diamond
description: "..."
coverImage: /assets/images/products/diamond-rings-cover.jpg
order: 1
---
Optional extended description here.
```

## When to use content collections vs. hardcoding
- Use collections for anything the client might want to update: product categories, testimonials, services
- Hardcode structural copy (nav labels, footer address) in components directly
