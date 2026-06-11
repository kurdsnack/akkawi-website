# src/layouts/

Page shell templates. Every page uses one of these to get the consistent `<head>`, header, nav, and footer.

## Planned layouts
- `BaseLayout.astro` — full page: doctype, meta tags, global styles, header, footer
- `CollectionLayout.astro` — extends Base; adds the collection breadcrumb and category sidebar

## Usage
```astro
---
import BaseLayout from '../layouts/BaseLayout.astro';
---
<BaseLayout title="About Us">
  <!-- page content -->
</BaseLayout>
```
