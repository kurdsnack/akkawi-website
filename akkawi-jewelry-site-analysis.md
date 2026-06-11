# Samir Akkawi Jewelry — Current Website Analysis

> **Purpose:** This document describes the structure, content, and build of the existing website at [akkawijewelry.com](https://www.akkawijewelry.com) to inform the design and development of a new site.

---

## 1. Business Overview

| Field | Details |
|---|---|
| **Business Name** | Samir Akkawi Jewelry |
| **Type** | Boutique fine jewelry store |
| **Location** | 9 Shatt Al-Arab Street, Um Uthaina, Amman, Jordan |
| **Founded** | Early 1990s (30+ years in business) |
| **Phone** | +962 795800651 |
| **Email** | samir@akkawijewelry.com |
| **Social** | Facebook, Instagram (`@akkawi_jewelry`) |
| **Website Builder** | Wix.com |
| **Copyright Year** | 2022 |

### Brand Positioning
- "Unique yet classic fine gold & diamond jewelry to last a lifetime"
- Emphasizes credibility, after-sales service, and personal trust
- Targets jewelry buyers in Amman for life milestones: engagements, weddings, birthdays

---

## 2. Site Architecture

The site is a **brochure/catalog website** — no e-commerce or shopping cart. Customers browse and then contact the store directly.

```
akkawijewelry.com/
├── Home                          (/)
├── About                         (/About)
├── Services                      (/services-4)
├── Store Policies                (/policies)
├── Contact                       (/blank-4)
└── Collections                   (/collections)
    ├── Diamond Collection        (/diamond-collection)
    │   ├── Rings                 (/copy-of-gold-bracelets)
    │   ├── Necklaces             (/dimaond-necklaces)
    │   ├── Bracelets             (/copy-of-diamond-rings-1)
    │   ├── Solitaire Rings       (/dimaond-wedding-rings)
    │   ├── Earrings              (/gold-earrings)
    │   └── Pendants              (/copy-of-diamond-rings)
    └── Gold Collection           (/gold-collection)  ⚠️ BUG: redirects to Diamond Collection
```

**Total top-level pages:** 6  
**Total sub-pages (product categories):** 6 (diamond only)  
**Known bugs:** The Gold Collection nav link (`/gold-collection`) redirects to the Diamond Collection page — the gold sub-pages either don't exist or are misconfigured.

---

## 3. Page-by-Page Breakdown

### 3.1 Home (`/`)

**Purpose:** Brand introduction and first impression.

**Sections:**
- **Header/Nav** — Logo (image) + "Samir Akkawi Jewelry" text, full nav menu
- **Hero** — Full-width image with headline: *"Jewelry You'll Always Want to Wear"* + short brand description + CTA to browse the site
- **Story Section** — Heading: *"The Way It All Began"* — 30-year history narrative, focus on quality and craftsmanship
- **Testimonial** — Single pull quote from a customer (initials S.N., Amman)
- **Dot/Slide Navigation** — 5 anchored sections within the homepage (carousel-style)
- **Contact Section** — Address, email, phone + a contact form (Name, Address, Email, Phone, Subject, Message, Submit)
- **Newsletter Signup** — Email input + Join button
- **Footer** — Logo, contact info, social icons, copyright

**Key content:**
> *"Samir Akkawi Jewelry is one of the best jewelry shops in Amman offering unique yet classic pieces to last a lifetime."*

---

### 3.2 About (`/About`)

**Purpose:** Brand story, mission, and values.

**Sections:**
- **Hero/Banner** — Gold rings collection image
- **Main Content Block** — Heading: *"All About Us — When Creativity and Quality Meet"*
  - Brand history (since early 90s, boutique store, reputation for credibility)
  - Mission statement: *"Fulfill jewelry lovers' desires with our unique high-quality collection, superior services and credibility."*
  - Values list:
    - We sell high quality jewelry
    - We believe in after sales service
    - We value our customers
    - We are a family
    - We are credible
    - We live by our principles
- **Footer** — Same sitewide footer

---

### 3.3 Services (`/services-4`)

**Purpose:** Describe what the store offers beyond just selling jewelry.

**Layout:** 4 image tiles in a grid, each with a title and short description.

| Service | Description |
|---|---|
| **Diamond Jewelry** | Wide range of certified and guaranteed fine Belgian diamond jewelry |
| **Repair & Maintenance** | High standard, prompt repair service |
| **Gold Jewelry** | 18 Karat white and yellow gold — Rings, Earrings, Bracelets, Necklaces |
| **Appraisals & Consultancy** | Free jewelry consultancy and impartial valuation of diamonds, gold, and watches |

**Intro text:** *"Our clients are always our first priority... helping them buy, sell, repair and appraise their jewelry."*

---

### 3.4 Store Policies (`/policies`)

**Purpose:** Build trust through transparent return, exchange, and warranty policies.

**Sections:**

**Exchange & Returns — Diamond Jewelry**
- Free return/exchange within 30 days of purchase
- After 30 days: 30% fee for returns, 15% fee for exchanges

**Exchange & Returns — Gold Jewelry**
- Gold returned at prevailing market price on date of exchange
- Manufacturing costs, stone weights, and non-gold components are deducted

**Warranty**
- Pricing guaranteed at international market value at time of purchase
- Complimentary polishing, servicing, and technical inspection for any purchased item, at any time

---

### 3.5 Contact (`/blank-4`)

**Purpose:** Dedicated contact page.  
*(Note: Page slug `/blank-4` suggests this was a blank template page renamed — content not fully crawled but a contact form is embedded on the Home page as well.)*

---

### 3.6 Collections (`/collections`)

**Purpose:** Hub/landing page for the two product collections.

**Layout:** Two large image tiles side by side, each with a description and "Explore our collection" CTA link.

| Collection | Description |
|---|---|
| **Diamond Collection** | Impressive variety of diamond and gemstone pieces — rings, earrings, necklaces, and rare finds |
| **Gold Collection** | One of the biggest ranges in Amman at competitive prices *(currently broken — links to Diamond Collection)* |

---

### 3.7 Diamond Collection (`/diamond-collection`)

**Purpose:** Category index for diamond jewelry.

**Layout:** 6 image tiles in a grid, each linking to a sub-page.

| Category | URL Slug |
|---|---|
| Rings | `/copy-of-gold-bracelets` |
| Necklaces | `/dimaond-necklaces` *(typo in slug)* |
| Bracelets | `/copy-of-diamond-rings-1` |
| Solitaire Rings | `/dimaond-wedding-rings` *(typo in slug)* |
| Earrings | `/gold-earrings` |
| Pendants | `/copy-of-diamond-rings` |

**Note:** Several URL slugs are clearly carry-overs from duplicated Wix pages (e.g. `copy-of-gold-bracelets`, `copy-of-diamond-rings-1`) and contain typos (`dimaond` instead of `diamond`). This indicates the site was built by duplicating pages rather than creating them cleanly.

---

## 4. Global Components

### Navigation
- **Logo:** Image + text combination (top-left)
- **Nav links:** Home, About, Services, Store Policies, Contact, Collections (dropdown with Diamond + Gold)
- **Style:** Horizontal top nav, accessible (tab-navigable)

### Footer (sitewide)
- Business name
- Email: samir@akkawijewelry.com
- Phone: +962 795800651
- Facebook link
- Instagram link
- Copyright: © 2022 by Samir Akkawi Jewelry

### Contact Form (on Home page)
Fields: Name, Address, Email, Phone, Subject, Message  
Action: Submit (Wix native form handler)

### Newsletter Signup (on Home page)
Fields: Email  
Action: Join (Wix native subscriber list)

---

## 5. Technical Notes

| Property | Detail |
|---|---|
| **Platform** | Wix.com (Website Builder) |
| **Hosting** | Wix-managed |
| **Image CDN** | `static.wixstatic.com` |
| **Analytics/SEO** | Google Site Verification tag present |
| **Social Meta** | Full Open Graph + Twitter Card tags on all pages |
| **Facebook Admin** | `akkawijewelry` |
| **E-commerce** | None — no cart, no product pricing displayed |
| **CMS/Database** | None apparent — static content only |

---

## 6. Content & UX Issues to Address in New Build

| Issue | Location | Notes |
|---|---|---|
| Gold Collection link broken | Nav + `/collections` page | `/gold-collection` redirects to Diamond Collection |
| Messy URL slugs | Diamond sub-pages | Slugs like `copy-of-gold-bracelets`, `copy-of-diamond-rings-1` — clearly duplicated pages |
| Typos in slugs | Diamond sub-pages | `dimaond-necklaces`, `dimaond-wedding-rings` |
| Contact page slug | `/blank-4` | Non-descriptive slug, suggests unfinished setup |
| No product detail pages | All collections | Categories link to galleries, no individual product pages with details |
| No pricing | Entire site | Expected for a luxury boutique, but worth deciding on for new build |
| Single testimonial | Home page | Only one customer quote across the entire site |
| Copyright year | Footer | Shows 2022 — outdated |
| Gold Collection content | Missing | No sub-pages exist for gold jewelry categories |

---

## 7. Summary for New Build

The current site is a **simple informational brochure site** built on Wix with a relatively flat structure. It covers the essentials — brand story, services, product categories, and policies — but lacks depth in product presentation, has several structural bugs from the Wix page-duplication workflow, and has no Gold Collection sub-pages despite it being a core offering.

The new build should:
- Maintain the same top-level page structure (Home, About, Services, Policies, Contact, Collections)
- Properly separate and build out both Diamond and Gold collection hierarchies
- Use clean, semantic URLs
- Consider adding individual product or look-book style pages
- Modernize the visual design while preserving the boutique, trustworthy brand feel
