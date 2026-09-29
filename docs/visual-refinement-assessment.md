# Visual Refinement Assessment

**Site:** https://www.theprinceecho.com  
**Repo:** `theprinceecho/theprinceecho`  
**Date:** 2026-09-29 (Europe/Berlin)  
**Agent:** Hermes Ops  
**Mandate:** Assessment + polish proposal — not a blind redesign. Draft ≠ live.

---

## Inventory

| Page / surface | Path | Notes |
|----------------|------|-------|
| Home (hero) | `index.html` `#home` | Full-viewport hero + logo |
| About / Threshold | `index.html` `#about` | Section, not a separate HTML file |
| Where to Find | `index.html` (no id) | Applied (X) + Bridge (Substack) cards |
| Transmissions | `index.html` `#recent-transmissions` | Essays I–VIII |
| Contact | `contact.html` | Tally iframe |
| Legal | `legal.html` | EN copy; cites German DDG |
| Shared CSS | Inline `<style>` × 3 | Duplicated tokens/chrome; drift risk |
| i18n | None | No DE pages, no switcher |
| Logo | `assets/img/webp/TPE_Logo.webp` | Untouched (lock) |

Public layer labels already correct: **X = Applied**, **Substack = Bridge**. No temple/outer/inner/transcendental on landing.

---

## Findings (by impact)

### P0 — Polish now (implemented on this branch)

1. **Cross-page CSS drift**  
   Tokens and chrome are copy-pasted across `index.html`, `contact.html`, `legal.html`. Concrete drift today:
   - `--font-size-xl`: index uses `clamp(1.5rem, 1.35rem + 0.6vw, 1.25rem)` (max &lt; preferred — broken clamp); contact/legal correctly max at `1.75rem`.
   - Index has TPE watermark body background + `.nav__link.active` + focus-visible; contact/legal lack these.
   - Contact/legal omit favicon `<link>`.
   - **Fix:** extract shared tokens + nav + footer + base to `assets/css/site.css`; link from all pages.

2. **Invalid font stack** — `body`  
   `font-family: Inter, system_ui, sans-serif` — `system_ui` is not a valid CSS family (underscore). Inter is never loaded. Result: generic `sans-serif`.  
   **Fix:** `system-ui, -apple-system, "Segoe UI", Roboto, sans-serif`. Inter load / self-host deferred (open question).

3. **Fixed-nav overlap risk** — `contact.html` `.contact`, `legal.html` `.legal`  
   Nav is `position: fixed`. Subpages rely on `--space-4xl` top padding alone; tight on short viewports.  
   **Fix:** shared `--nav-offset` + consistent `padding-top` on subpage mains.

4. **Mobile transmissions** — `.transmission` @ ≤560px  
   Side-by-side 160px image + text stays horizontal; cramped on phones.  
   **Fix:** stack column below 560px; full-width image.

5. **Accent RGBA mismatch**  
   Borders/glow use `rgba(197, 164, 110, …)` (amber) while `--color-accent` is `#d0c4a8` (cream-gold).  
   **Fix:** align border/glow to `rgba(208, 196, 168, …)`.

6. **Text hierarchy flat**  
   `--color-text` and `--color-text-secondary` are identical (`#c5b8a0`).  
   **Fix:** secondary → `#a89a82` (still charcoal+gold family).

7. **EN/DE language switcher absent**  
   No i18n structure.  
   **Fix:** smallest viable `nav__lang` (EN|DE) on all pages + `de/*.html` chrome stubs with “Inhalt folgt.” — **no invented German marketing copy**.

8. **`_headers` caches all non-index assets as immutable 1y**  
   Would pin extracted CSS forever; also pins `contact.html` / `legal.html`.  
   **Fix:** short/must-revalidate for `*.html` and `/assets/css/*`.

### P1 — Discuss later (not implemented)

| Item | Selector / locus | Note |
|------|------------------|------|
| Load or self-host Inter | `body` font stack | Sovereignty vs Google Fonts |
| Meta description / OG tags | `<head>` all pages | SEO; Lighthouse meta-description currently off |
| Wrap index sections in `<main>` | `index.html` | Landmark; CI assertion currently off |
| Skip link | after `<body>` | a11y nicety |
| Transmission link hygiene | Essay V–VII `href`s | Mix of `open.substack.com`+UTM vs clean `/p/` URLs |
| Sitemap `lastmod` | `sitemap.xml` | Still 2026-05-17 |
| Contact unused form CSS | `.form-group` etc. | Dead styles; Tally iframe is live UI |
| Separate About HTML | — | Brief named “About”; today it is `#about` on index — keep unless product wants a route |
| Reduced-motion | transitions | Prefer calm; optional `prefers-reduced-motion` |
| Card hover `translateY` on touch | `.card:hover` | Fine; sticky hover on some mobiles |

### Content gaps (flag only — no silent rewrite)

1. **No German marketing/legal copy** for landing, contact note, or legal sections. Legal cites § 5 DDG but body is English only — DE legal text needs Mike/counsel, not Ops invention.
2. **Where-to-find subtitle** (`index.html` `.where-to-find .section-subtitle`): `Applied short signals<br>Bridge essays.` — line break / punctuation feels unfinished; messaging decision for Mike.
3. **Hero vs About framing**: hero “A threshold for those who sense the urge.” vs About “sovereign threshold… architecture that is forming” — intentional layering or slight redundancy? Discuss, don’t rewrite.
4. **No meta description** — product/messaging call.
5. **Essay V alt text** still says “Track 2 - The Institutional Response” while title block says Track 2 / Institutional Response — OK; Essay IV alt uses “Track #1” vs UI “Track 1” — cosmetic alt inconsistency.
6. **Contact nav** has no “Contact” item / active state on subpages — optional IA tweak.
7. **`config/project.json`** still says `"theme": "navy-gold"` while live identity is charcoal + cream-gold — docs drift.

---

## Implemented on this branch (summary)

- Assessment doc (this file).
- Shared `assets/css/site.css` + page links; remove duplicated chrome/tokens from HTML where moved.
- Token / type / contrast / mobile transmission / nav-offset / accent RGBA polish within charcoal+gold.
- Header/footer consistency + favicon on all pages + watermark on all pages.
- EN|DE switcher UI; `de/` stubs (chrome + “Inhalt folgt.” only).
- `_headers` adjustment for HTML + CSS revalidation.

**Not done:** copy rewrites, logo changes, merge to `main`, Cloudflare deploy, inventing DE marketing copy, Grok Build.

---

## Open questions for Metatron / user

1. Approve DE stub approach, or wait until Mike supplies DE copy before shipping switcher live?
2. Should legal get a proper German Impressum/Datenschutz draft (Mike + counsel)?
3. Self-host Inter, Google Fonts, or keep system-ui stack?
4. Any messaging tweak to Where-to-find subtitle / hero-about overlap (Mike)?
5. Aristotle brand pass: any token/spacing constraints beyond charcoal+gold + logo lock?

## Blocking Aristotle brand pass?

**Nothing hard-blocking.** Logo kept; palette preserved (cream-gold on charcoal). Secondary text and border RGBA were nudged for hierarchy/alignment — Aristotle should confirm those two token tweaks. DE stubs are structural placeholders only.

---

*Draft for PR review. Publish gate: Metatron / user.*
