# src/components/

Reusable UI pieces. Composed inside layouts and pages.

## Planned components

### Layout components (used in every page)
- `Nav.astro` — top navigation bar with logo and links
- `Footer.astro` — sitewide footer (address, socials, copyright)

### Home page
- `Hero.astro` — full-width image + headline + CTA
- `CollectionPreview.astro` — two-tile Diamond/Gold teaser
- `Testimonials.astro` — customer quote(s)
- `ContactForm.astro` — Name, Email, Phone, Subject, Message

### Collection pages
- `CategoryGrid.astro` — image tile grid linking to sub-categories
- `CategoryCard.astro` — single tile (image + label + link)

### Shared
- `Button.astro` — styled CTA button (primary / ghost variants)
- `SectionHeading.astro` — consistent heading block with optional subtitle

## Naming convention
PascalCase for component files. One component per file.
