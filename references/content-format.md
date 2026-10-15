# Content file format (Markdown + YAML)

Every page is one `.md` file. YAML frontmatter on top, Markdown body below. On Astro builds, the URL comes from the **file path**, not a `slug` field. Keep `slug` only as a human label; do not expect it to drive the route.

## Common fields

```yaml
---
type: page              # page | post | brand | brandPage | author
title: "H1 title"       # starts with the focus keyword
metaTitle: "Title tag, max ~65 chars, starts with the focus keyword"
metaDescription: "Max ~165 chars; no em dash; no competitor-site names"
focusKeyword: "unique across the whole site"
secondaryKeywords: []
author: real-author-slug
reviewer: real-author-slug
excerpt: "Card / internal-link blurb"
summary:
  - "Key fact 1"
  - "Key fact 2"
  - "Key fact 3"
faq:
  - q: "Question?"
    a: "Self-contained answer in 1 to 3 sentences."
sources:
  - title: "Official register or T&Cs title"
    url: "https://..."
heroImage: kebab-case-name
heroAlt: "Descriptive alt that naturally includes the focus keyword"
publishedAt: 2026-10-15
lastChecked: 2026-10-15
status: published       # published | draft
---
```

## Body rules

- No H1 in the body. Start at `##`.
- Internal links: absolute paths that exist in `docs/url-plan.json`.
- External links: full https URLs to official sources only.
- Tables for comparable data. FAQ 4-7 on money pages. Summary 3-5 bullets.
- Tip/warning boxes as blockquotes if the theme supports them. Do not invent shortcodes the stack does not render.

## Brand review (`content/brands/{brand}/index.md`)

Required when published: `name`, `company` (licence holder as on the register, no `[VERIFY]` text), `website`, `licenses[]` (slug + number if seen + holder + register URL + `verified|reported`), `ratings` with keys `safety`, `terms`, `payments`, `rg`, `support`, `games`, `reviewType: desk | hands-on`, `pros`, `cons`.

`affiliateUrl` / `/go/{brand}` mapping lives in the brief, not as a secret in git.

Hands-on only if a real test happened. Otherwise `reviewType: desk` and the body says so.

## Cluster page (`content/brands/{brand}/{type}.md`)

```yaml
type: brandPage
brand: bet365
pageType: payments   # registration | login | welcome-bonus | promotions | app | casino | live-casino | sportsbook | payments | verification | customer-support | account-closure
focusKeyword: "bet365 payment methods"
```

Write it only when it carries real, verified, brand-specific facts. Skip types that do not apply. If two types would repeat the same facts, merge them.

## Author

`name`, `jobTitle`, `expertise`, true bio only. Never invent people or photos.
