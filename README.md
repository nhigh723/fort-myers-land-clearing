# Fort Myers Land Clearing Guide — Rank-and-Rent Site #2

Static HTML/CSS site. No build step, no frameworks, no backend.
Cloned structurally from the Lehigh Acres template
(`../lehigh-acres-land-clearing/`) with all content rewritten and
localized to Fort Myers. Brand: **Fort Myers Land Clearing Guide** —
an honest local-resource guide, NOT a fake contractor. See the honesty
rules in the task brief: no fake reviews, address, phone, license
claims, or company names; no HLW affiliation; all content original;
prices are typical SWFL ranges with "varies by site conditions"
caveats.

## Fort Myers localization (what makes this site different)

- **City vs. county permits** — inside the City of Fort Myers limits,
  permits come from the city; in unincorporated Lee County (many
  "Fort Myers" addresses), from the county.
- **Riverfront and canal lots** — Caloosahatchee River and canal
  frontage: mangroves protected statewide, wetland setbacks, high
  water table, drainage and flood-elevation rules.
- **Storm debris** — hurricane-damaged lots are a recurring local job:
  downed trees and scattered debris need separating and hauling.
- **Electric utility** — FPL serves most of Fort Myers (verified Nov
  15, 2026 via web search: FPL serves Fort Myers; LCEC serves Cape
  Coral, North Fort Myers, and parts of Lehigh Acres). Some
  unincorporated pockets use a different provider — the site says to
  confirm by address.
- Same county facts as Lehigh: Lee County, Brazilian pepper,
  melaleuca, saw palmetto, sandy soil, wet season May–October, Lee
  County permitting, Florida 811 locates.

## Files

| File | Purpose |
|---|---|
| `index.html` | Home — hero, services, Fort Myers specifics, cost snapshot, FAQ teaser, quote CTA |
| `forestry-mulching.html` | Service page + Service schema |
| `lot-clearing.html` | Service page + Service schema |
| `brush-clearing.html` | Service page + Service schema |
| `stump-grinding.html` | Service page + Service schema |
| `site-prep-grading.html` | Service page + Service schema |
| `cost-guide.html` | Detailed pricing + FAQPage schema (3 pricing Q&As) |
| `faq.html` | 14 Q&As + FAQPage schema |
| `get-a-quote.html` | Quote form (name, phone, email, area, service, acreage, description) |
| `css/style.css` | Single stylesheet, mobile-first (copied from template) |
| `js/main.js` | Mobile nav, dropdown, form logic (copied from template, relabeled) |
| `sitemap.xml` | All 9 pages |
| `robots.txt` | Allow all + sitemap reference |

## Before publishing

1. **Replace the placeholder domain.** `nhigh723.github.io/fort-myers-land-clearing`
   appears in canonical tags, schema URLs, `sitemap.xml`, and
   `robots.txt`. It is NOT a registered domain — it is a placeholder.
   Find-and-replace it with the live domain (or the GitHub Pages URL)
   on publish. Every occurrence is marked with a
   `PLACEHOLDER DOMAIN` comment.
2. **Quote form endpoint.** `js/main.js` has two config consts at the
   top of the form section: `FORM_ENDPOINT` (a form-service URL that
   accepts a JSON POST, e.g. Formspree) and `FORM_MAILTO` (fallback
   inbox). Both are empty today. Until they are set, submitting the
   form opens the visitor's email app with the request pre-filled and
   shows the details on the page with a copy button — honest, and
   nothing is silently lost. No email address or phone number is
   hardcoded anywhere on the site.

## SEO / GEO notes

- Unique title + meta description per page; one H1 per page; clean
  H2/H3 structure; direct-answer intros (first 50–70 words answer the
  page's question).
- FAQPage schema on homepage (4 Q&As), FAQ page (14 Q&As), and
  cost guide (3 pricing Q&As). Service schema on all 5 service pages.
  WebSite schema on the homepage.
- Internal linking between all pages (nav, service cards, in-content
  links, footer).
- Fast: system fonts, no frameworks, one CSS file, one small JS file,
  no images.

## Local verification

Run `python3 -m http.server 8000` from this directory and open
http://localhost:8000/ — or run the link/content checks documented in
the build report. Verified Nov 15, 2026: all 14 URLs return 200,
`node --check js/main.js` passes, CSS braces balanced (156/156), all
JSON-LD blocks parse, one H1 per page, 9/9 unique titles, FAQPage
counts 4 (home) / 3 (cost guide) / 14 (FAQ), all internal links
resolve, no lorem ipsum / placeholder text / TODOs, no hardcoded
email or phone, no named real companies (FPL is named only as the
electric provider in the context of coordinating near power lines,
verified via web search), zero "Lehigh" references, no fake
reviews/testimonials/ratings/license claims.

**Originality audit (Nov 15, 2026):** sentence-level comparison
against the Lehigh template (town names normalized out, declarative
prose >= 60 chars, FAQ questions and form labels excluded as shared
by design) found 20/304 identical sentences (6.6%). The remainder
are price facts, template CTA formulas, and the intentional
disclaimer wording — all body prose was written fresh for Fort Myers.
