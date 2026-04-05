# Outreach for the Unreached Soul Winning Ministry

Public website for **Outreach for the Unreached Soul Winning Ministry**—a static, content-driven ministry site built with [Astro](https://astro.build). Pages are generated at build time for speed and SEO; sermons, events, staff, and blog posts live in Markdown via Astro Content Collections.

**Repository:** [github.com/randy-tarasevich/Outreach-for-the-Unreached-Soul-Winning-Ministry](https://github.com/randy-tarasevich/Outreach-for-the-Unreached-Soul-Winning-Ministry)

[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](CODE_OF_CONDUCT.md)

## Tech stack

- **Astro 5** — static site generation
- **Tailwind CSS v4** — styling via [`@tailwindcss/vite`](https://tailwindcss.com/docs/installation/framework-guides/astro) and `src/assets/styles/global.css` (no legacy `tailwind.config.cjs`)
- **Markdown content** — `src/content/` with schemas in `src/content/config.ts`
- **Sitemap** — `@astrojs/sitemap` (set your real URL in `astro.config.mjs` → `site`)

## Features

- Static generation, fast loads, and SEO-friendly defaults (meta tags, JSON-LD, sitemap)
- Mobile-first layouts and reusable UI components
- Staff, events, sermons, ministries, blog, and site info as structured content
- Accessible patterns (ARIA, keyboard navigation) where implemented in components

## Project structure

```
Outreach-for-the-Unreached-Soul-Winning-Ministry/   # repository root
├── public/
│   ├── uploads/          # Images: staff, events, sermons, ministries, blog
│   ├── favicon.svg
│   ├── robots.txt
│   └── site.webmanifest
├── src/
│   ├── assets/styles/    # Global CSS (Tailwind v4 entry + tokens)
│   ├── components/       # Global, Sections, UI
│   ├── content/          # Markdown + config.ts schemas
│   ├── layouts/          # BaseLayout, PostLayout
│   ├── pages/            # Routes
│   └── utils/
├── astro.config.mjs
└── tsconfig.json
```

## Getting started

**Prerequisites:** Node.js 18+ and npm.

```bash
git clone https://github.com/randy-tarasevich/Outreach-for-the-Unreached-Soul-Winning-Ministry.git
cd Outreach-for-the-Unreached-Soul-Winning-Ministry
npm install
npm run dev
```

Open [http://localhost:4321](http://localhost:4321).

**Production build:** `npm run build` — output in `dist/`. Preview locally with `npm run preview`.

## Content

All editable copy and media paths are in `src/content/**/*.md`. Schemas and required frontmatter fields are defined in `src/content/config.ts`.

### Staff (`src/content/staff/`)

```markdown
---
name: "John Smith"
title: "Youth Pastor"
image: "/uploads/staff/john-smith.webp"
email: "john@example.com"
phone: "+1-555-1234"
bio: "John has been serving in youth ministry for 10 years."
order: 3
draft: false
---

Longer biography here…
```

### Events (`src/content/events/`)

```markdown
---
title: "Youth Summer Camp"
date: 2025-07-15
endDate: 2025-07-20
time: "9:00 AM - 5:00 PM"
location: "Camp Wilderness"
image: "/uploads/events/summer-camp.webp"
summary: "A week-long adventure for teens to grow in faith and have fun!"
tags: ["youth", "summer", "camp"]
registrationRequired: true
registrationLink: "https://example.com/register"
draft: false
---

## About Summer Camp

Event details…
```

### Sermons (`src/content/sermons/`)

```markdown
---
title: "Walking in Faith"
date: 2025-02-02
speaker: "Rev. Dr. John Smith"
series: "Faith Foundations"
scripture: "Proverbs 3:5-6"
audioUrl: "https://example.com/sermons/walking-in-faith.mp3"
videoUrl: "https://www.youtube.com/embed/example789"
image: "/uploads/sermons/walking-in-faith.webp"
summary: "Learn how to trust God completely and walk confidently in His plan."
tags: ["faith", "trust", "guidance"]
draft: false
---

## Sermon Overview

Notes and outline…
```

## Main routes

| Path | Purpose |
|------|---------|
| `/` | Home |
| `/about-us` | Mission, values, history |
| `/staff` | Staff directory |
| `/ministries` | Ministries |
| `/sermons` | Sermon archive (filters) |
| `/events` | Events |
| `/blog` | Blog |
| `/im-new` | New visitors |
| `/contact` | Contact |
| `/giving` | Giving |

## Customization checklist

1. **`astro.config.mjs`** — set `site` to your production URL (required for correct canonical URLs and sitemap).
2. **`src/layouts/BaseLayout.astro`** — default SEO/meta if needed.
3. **`src/components/Global/`** — header, footer, navigation, branding.
4. **`public/site.webmanifest`** and **`public/favicon.svg`** — name, icons, theme.
5. **`src/assets/styles/global.css`** — Tailwind v4 theme extensions and global rules.
6. **`src/content/siteInfo/`** and other collections — ministry name, service times, copy.

Place images under `public/uploads/` using the same paths referenced in frontmatter.

## Deployment

Any static host works (Netlify, Vercel, Cloudflare Pages, GitHub Pages, etc.):

- **Build command:** `npm run build`
- **Publish directory:** `dist`

Connect the repo after pushing to GitHub; most platforms auto-detect Astro.

## License

See the [LICENSE](LICENSE) file in this repository.

## Acknowledgments

- [Astro](https://astro.build), [Tailwind CSS](https://tailwindcss.com), and the broader open-source ecosystem
- This codebase started from an open-source church website starter and has been adapted for Outreach for the Unreached Soul Winning Ministry
