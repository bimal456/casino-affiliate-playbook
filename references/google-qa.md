# Google and manual QA

Reviewed: 2026-10-15. Recheck official guidance before future builds. Rankings cannot be certified from a successful build.

## Sources

- Noindex and crawl: https://developers.google.com/search/docs/crawling-indexing/block-indexing
- JavaScript / crawlable links: https://developers.google.com/search/docs/crawling-indexing/javascript/javascript-seo-basics
- Spam policies: https://developers.google.com/search/docs/essentials/spam-policies
- Back-button hijacking: https://developers.google.com/search/blog/2026/04/back-button-hijacking
- Helpful content: https://developers.google.com/search/docs/fundamentals/creating-helpful-content
- Documentation changes: https://developers.google.com/search/updates
- AI content: https://developers.google.com/search/docs/fundamentals/using-gen-ai-content

## Required review

1. Inspect current official updates and spam policies. Record only applicable changes and dated primary sources. Do not invent special AI-class-name penalties or ranking guarantees.
2. Original value and page intent. Preserve useful depth; remove repetition. Volume, keyword density, E-E-A-T labels and AI-detector scores are not ranking guarantees.
3. Check ownership, contact, licence scope, bonus wagering/expiry/eligibility and RG copy against primary sources. Block unsupported material claims. Never create fake first-hand testing.
4. Initial HTML and rendered content, crawlable hrefs, successful canonical pages, real 404 status, robots/noindex interactions, sitemap coverage, hreflang only for real translations.
5. Navigation and back behavior. No deceptive redirects, cloaking, doorway variants, scaled low-value pages, fabricated schema or stuffing. Flag suspicious history/pushState; normal client routing is not automatically abuse.
6. Test 360px, 768px and desktop: overflow, accessible dropdowns, focus, buttons, image loading, console. Do not assert these passed from static source alone.
7. After authorised deploy: production headers and redirect destination with an HTTP client. Search Console URL Inspection when access is provided.
8. Keep every requirement pass / fail / not-tested with evidence. Automated success covers only the checks the script runs.

## Hosting notes (this account)

- Cloudflare Pages Functions return 1019. Use a standalone Worker + `[assets]`.
- `/go/{brand}` 302 lives in the Worker. Verify `Location` and `X-Robots-Tag` on that redirect response. Static `_headers` do not apply to Worker-generated responses.
- Do not Disallow `/go/` in robots.txt when noindex must be read.
- A custom 404.html is not proof of a 404 status.
