# public/

Static files served exactly as-is. Nothing in here goes through Astro's build — reference them with absolute paths from `/`.

## Folder structure

```
public/
└── assets/
    ├── images/
    │   ├── brand/       ← Logo, hero images, store photos
    │   └── products/    ← Product photography, organized by collection
    │       ├── diamond/
    │       └── gold/
    └── fonts/           ← Self-hosted fonts (if not using Google Fonts CDN)
```

## Image naming convention
- Lowercase, hyphenated: `diamond-rings-hero.jpg`
- Include category prefix where useful: `diamond-ring-01.jpg`, `gold-bracelet-03.jpg`
- Use `.jpg` for photos, `.svg` for logo and icons, `.webp` for optimized web delivery

## Assets status
- Brand: TBD (logo file needed from client)
- Diamond collection: partial (sourced from old Wix site)
- Gold collection: missing — needs photography from client
