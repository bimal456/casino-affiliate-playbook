---
name: casino-affiliate-playbook
description: "Use when building or rewriting a casino affiliate site."
version: 0.1.0
license: MIT
author: kushalarora
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [affiliate, casino, seo, eeat, content, qa, cloudflare]
    related_skills: [astro-affiliate-cloudflare-build, casino-affiliate-content-generation, multi-geo-casino-affiliate-site]
---

# Casino Affiliate Playbook

Editorial, SEO, conversion and QA rules for independent casino/betting affiliate sites. Stack wiring lives in `astro-affiliate-cloudflare-build`. Bulk writer dispatch lives in `casino-affiliate-content-generation`. This skill is the brief those jobs must follow.

This is an **affiliate** skill. Do not use it for an owned-brand operator site (Spinwinera-style we/our, single `/play` funnel, no rival casinos). Those are a different product.

## When to Use

- New casino/betting affiliate, review, comparison or hub site.
- Rewrite, audit or score existing affiliate page copy ("run the checklist", fluff-free, answer-first).
- Planning URLs, brand clusters, fact boxes, tools, or a claims ledger.
- Pre-publish QA of static output against a site brief.

Don't use for: owned-brand casino sites, WordPress theme work, or Astro/Wrangler wiring (load the stack skill instead).

## Prerequisites

- Market, language, domain, author (real person or pen name of a real person), and first brand list. If 1-5 in [Ask first](#ask-first) are missing, ask them in one numbered message and wait.
- This Cloudflare account: Pages Functions return error 1019. Host with a **standalone Worker + `[assets]`**. Deploy only when the user asks.
- Keyword/SERP data: SerpApi (`~/casino-trends-watch/.env`, ~10/hr on Starter) or DataForSEO. No Ahrefs MCP. Never treat a cap-empty SerpApi response as a real "no results".
- Secrets stay out of Git. Affiliate destinations live in the brief / Worker KV, not in page copy.

Load references only when needed:

| Need | File |
|---|---|
| Page rewrite / audit | [references/answer-first.md](references/answer-first.md) |
| Markdown + YAML shape | [references/content-format.md](references/content-format.md) |
| Google / browser QA | [references/google-qa.md](references/google-qa.md) |
| Job brief JSON | [references/brief.example.json](references/brief.example.json) |

## Ask first

Ask in one short numbered message. Do not write pages until 1-5 are answered. Default the rest and say what you chose.

1. Market (country/region) and language.
2. Focus: casino, sports, both; any niche.
3. Domain and brand name/tagline (or propose).
4. Author: real name or pen name, plus 3-5 true bio facts. Never invent people.
5. First operators, in order.
6. Approved affiliate programs / tracking URLs yet?
7. Company name, country, contact email for About/legal.
8. Hands-on tests possible (deposit/withdraw screenshots)? Default: desk reviews, stated as desk.
9. May "reported, not yet confirmed" facts from other review sites be used? Default: primary sources only.
10. Pace / page budget this batch.

Default hosting: Cloudflare Worker + `[assets]`, not Pages Functions, not WordPress.

## Never-break rules

**Writing**
- No en dash or em dash anywhere (copy, titles, commits). Use `-`.
- Fully original. Never copy or closely paraphrase other gambling sites.
- Never name competitor affiliate or review sites.
- No filler intros ("In this article we will"). First sentence under every heading answers it.
- Yes/no question headings start with "Yes," or "No,".
- Never promise winnings. Never target minors or self-excluded players.

**Facts**
- Never invent bonuses, wagering, dates, license numbers, ratings, tests or quotes.
- Primary sources only: operator site/T&Cs, official registers, payment/game providers, help orgs.
- Unconfirmed value: rewrite so it is not needed, or `[VERIFY: what]`. Pages with open `[VERIFY]` are not published. Strip VERIFY text from any field that renders (fact boxes leak).
- Never claim a first-hand test that did not happen. Desk reviews say they are desk reviews.
- Offshore licence is not local authorisation. Record URL + date in a claims ledger.

**SEO**
- One focus keyword per page, first in H1 and title tag. No cannibalization. One brand = one review; each cluster page owns a distinct keyword.
- Intent match: "best X" = toplist, "how to" = steps, "{brand} review" = review. Never mix two intents on one URL.
- Internal links only to URLs in `docs/url-plan.json` (or the brief's page list).
- External links: official sources only. Affiliate CTAs: `rel="sponsored nofollow"` (+ `noopener` if `target=_blank`).
- No thin clones. No city/brand-name template swaps. If a topic is too thin, fold it into the parent and leave the URL unwritten.
- Small checked batches. No burst publish on a new domain.
- Depth follows the SERP (match or slightly beat top 3-5). No padding to hit a word count. Honor an explicit brief `min_words` if the user set one; do not invent 8,000/4,000 defaults.

**People / trust**
- Real author only. Editorial policy discloses AI drafting if used; a named person approves.
- Trust pages ship with the first money pages: About, Author, How we rate, Editorial policy, Affiliate disclosure, Responsible gambling, Contact, Privacy, Terms, Corrections.

**Conversion (affiliate, not brand)**
- Distinct `/go/{brand-slug}/` per brand. Never funnel all brands through `/play`.
- 302/307 only. Same destination for users and crawlers. No cloaking, no UA/geo/referrer splits, no history traps, no password fields, no fake official login.
- `/go/` stays crawlable when relying on noindex. Do not Disallow `/go/` in robots.txt. Exclude `/go/` from the sitemap. Verify `X-Robots-Tag: noindex` on the **redirect response**.
- Review content before the CTA. Disclosure near commercial comparisons, in the site language. Rankings never follow commission.

**Player safety**
- Age badge (checked 18+/19+) and RG link on every page. Promote only operators allowed to take that market. Never geo-block pages; only operator buttons change.
- Check local advertising rules before bonus copy.

## Procedure

1. **Positioning note** (one page, owner approve): primary player, what ranking pages miss (notes only, never copy, never name them), 2-3 signature assets from the list below, name/tagline/voice. Complete when the owner has signed off or told you to proceed.
2. **URL plan** as `docs/url-plan.json`: every URL, focus keyword, page type, status. Check it before any new page. Complete when zero keyword collisions remain.
3. **SERP-first** per page: live query, date, engine, location method, observed URLs. Match content type, H2s, depth and tone. Disclose generic-search limits. Complete when each planned page has a noted SERP reference.
4. **Claims ledger** for bonuses, licences, eligibility, payments, withdrawals: source URL + date + claim. Complete when every published number has a row.
5. **Write** from [references/content-format.md](references/content-format.md). Apply [references/answer-first.md](references/answer-first.md) (rewrite vs audit vs single component). Information gain: at least 2-3 things generic pages lack. Summary 3-5 bullets, FAQ 4-7 self-contained answers, tables for comparable data. No H1 in the body.
6. **Build** real pages: one H1, semantic landmarks, unique titles/descriptions, production canonicals, crawlable nav. Affiliate disclosure + RG. Images: dimensions, descriptive alt (informative) or empty alt (decorative); do not lazy-load the LCP image.
7. **Check** `python3 scripts/qa_static.py --root DIST --brief BRIEF_JSON` from this skill directory (or copy the scripts into the repo). Last status must not be FAIL. Then [references/google-qa.md](references/google-qa.md). Fix failures; do not weaken checks.
8. **Ship** only the batch that passed. Deploy only on request, via Worker + `[assets]`. Report sources, open `[VERIFY]`, failed/not-tested checks, and the delivery path. Never claim indexing.

## Signature assets (pick 2-3 that fit)

1. Brand fact boxes (owner, named licence + register link, payments/limits/times, min deposit, support, RG tools, app) with source + last-checked.
2. Bonus value calculator (wagering, weighting, time limit, max cashout -> real cost).
3. Terms change log (dated snapshots).
4. First-hand test logs with screenshots - never fake.
5. Local payment-method guides from checked data.
6. Calculators (odds, wagering, RTP, bankroll).
7. Comparison tables sorted from fact boxes, not opinion.
8. Owner / sister-site map from confirmed companies only.
9. Honest score with published method; scores independent of commission.
10. AI-search block: summary, tables, FAQ, schema matching visible facts, `llms.txt`.

## Starting IA

```
/                                  Home
/{hub}/                            Intent toplists (casinos, bonuses, live, apps, payments, fast-withdrawal)
/reviews/                          Index
/reviews/{brand}/                  One review per brand
/reviews/{brand}/{topic}/          Cluster only with real brand-specific facts
/payment-methods/{method}/
/guides/{topic}/
/tools/{tool}/
/about/ /authors/{name}/ /how-we-rate/ /editorial-policy/
/affiliate-disclosure/ /responsible-gambling/ /contact/
/privacy/ /terms/
```

Brand cluster pages (skip if facts would duplicate): review, bonus, app, withdrawal, payments, verification, login, support, account closure, sister sites. Each links back to the review and the matching hub.

Country/city pages only when rules, operators or payments actually differ. Never clone per city.

Launch order: positioning -> URL plan -> trust pages + check script green -> home + 3-5 hubs + 10-20 priority reviews + core tools -> small cluster/payment/guide batches. Before each batch: would a player bookmark this page?

## Writing modes

From the request:

- **Rewrite:** return the copy, then the answer-first report.
- **Audit:** report only; quote each violation and the fix.
- **Single component:** return that block only, paste-ready.

Unclear: rewrite for short inputs, audit for full pages. Full rule set: [references/answer-first.md](references/answer-first.md).

Priority if rules collide: answer-first sentence, then certainty on verified facts, then the IF second sentence. Do not make a sentence "certain" by making it false; state the condition instead.

## Hosting (this account)

- Worker + `[assets]` to `./dist`. Not Pages Functions (1019).
- `/go/{brand}` 302 in the Worker, with `X-Robots-Tag: noindex` on that response. Verify with a real HTTP client; `file://` cannot prove headers.
- `robots.txt` + `sitemap.xml` at root. Sitemap = canonical indexable 200s only.
- True 404 status on missing paths (a custom 404.html is not proof).
- Do not deploy unless asked.

## Pitfalls

- `[VERIFY]` in YAML that renders (company, licence holder) ships on the live page. Strip before deploy.
- SerpApi Starter over cap returns fake empty results.
- 8k/4k word floors from the old Codex brand brief are not defaults here. SERP sets depth; padding is a spam-update liability.
- `/play` is the owned-brand funnel. Affiliate output using `/play` is a FAIL.
- Disallow `/go/` plus noindex is a contradiction; keep `/go/` crawlable.
- Static QA PASS is not legal, ranking, or browser proof. Label untested checks.
- Do not speak as the operator. Neutral third person for brands; we/our only for the publisher's research and method.

## Verification

A batch is done when:

- [ ] url-plan has unique focus keywords; every internal link is in the plan
- [ ] every published fact has a claims-ledger row, or the page is held
- [ ] no `[VERIFY]` in any rendered field
- [ ] no em/en dashes; no competitor-site names; no invented tests
- [ ] each money page has disclosure, RG, age, `/go/{brand}` with sponsored nofollow
- [ ] `qa_static.py` is not FAIL
- [ ] google-qa items are pass, fail, or not-tested with evidence
- [ ] Worker deploy claimed only if `wrangler deploy` was actually run and the URL fetched
