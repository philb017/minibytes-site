# minibytes (Jekyll)

A Jekyll rebuild of minibytes.com.au — same nav structure (Hardware / Software /
Notes with their real subcategories), same kind of terse command-reference
posts, seeded with 16 real posts pulled from the live site as a working
sample.

## What's here

- `_config.yml` — site settings + the `nav` structure driving the header dropdowns
- `_layouts/` — default shell, home (post list), post, page, category archive
- `_includes/` — header (nav) and footer
- `_posts/` — 16 sample posts, real content pulled from the live site
- `category/*.md` — one archive page per subcategory (Hardware: Avaya Switch,
  Cisco Switch, Fortigate, Mikrotik, Ubiquiti · Software: AntiMalware, Centos,
  Office 365, Other, Powershell, VMware, Windows). Empty ones just show
  "No posts in this category yet" until you add matching posts.
- `gallery.md`, `kitesurfing.md` — placeholder pages for the two "Notes" nav items
- `assets/css/style.css` — plain CSS, light/dark via `prefers-color-scheme`, no build step

## Run it locally

```
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000. I couldn't test-build this myself — this
sandbox's outbound access to rubygems.org is blocked — so run it locally
before you trust it; the front matter and Liquid tags have been
syntax-checked, but that's not the same as a real build.

## Adding a post

Drop a file in `_posts/` named `YYYY-MM-DD-title.md`:

```markdown
---
title: "Your Title"
date: 2026-08-25
category: Windows
---

Body content here.
```

`category` must exactly match one of the strings used in `category/*.md`
(case-sensitive) or it won't show up on that archive page.

## Bringing in the rest of your posts

This only has 16 sample posts, not your full archive. The reliable way to
pull everything over is a proper WordPress export, not more scraping:

1. In WordPress: **Tools → Export → All content** → download the `.xml` file.
2. Use [`jekyll-import`](https://import.jekyllrb.com/docs/wordpress/) (the
   `jekyll-import wordpress-dot-com` or `wordpress` importer) to convert it
   straight into `_posts/`. It preserves dates, categories, and handles the
   HTML-to-Markdown conversion properly — much better fidelity than scraping
   the live pages.
3. Re-run `bundle exec jekyll serve` and check categories/dates landed where
   expected — you'll likely need to reconcile some category names against
   the `category/*.md` files here.

## Deploying

- **GitHub Pages**: push as-is — `jekyll-feed` and `jekyll-sitemap` are both
  on GitHub's supported-plugins list, so it builds natively, no Actions needed.
- **Cloudflare Pages / Netlify**: build command `bundle exec jekyll build`,
  output directory `_site`. Either can also run custom plugins if you add any
  later, which GitHub Pages' native build can't.
