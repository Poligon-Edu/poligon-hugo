# COGA / Accessibility Audit — poligon-edu.ro (poligon-hugo)

**Scope:** Hugo site (`hugo.toml`, theme `hugo-book` + custom `layouts/`, `assets/_custom.scss`,
`data/reviews.json`), content in `content/ro` + `content/en`, teaching materials mirrored as web pages in
`content/ro/materiale/` plus downloadable PDFs in `static/documents/`.
**This file is the COGA-focused complement to the existing `accessibility-audit.md` and
`performance-audit.md` (WCAG/perf, 2026-11-06) — don't duplicate work: that audit's items U1–U7 and
"Recommendable" are still valid unless marked fixed below; this document adds the cognitive-accessibility
layer (COGA — [W3C coga-usable](https://www.w3.org/TR/coga-usable/) + WCAG 2.2 SC 2.4.11, 2.5.7, 2.5.8,
3.2.6, 3.3.7, 3.3.8) and a unified, prioritized TODO list with tools.
**Environment:** openSUSE Tumbleweed KDE (Linux); tool platform notes inline.

Verified in repo on the audit date: GA in `<head>` unconditional, KaTeX from jsdelivr CDN without SRI,
carousel autoplay with `<span>` dots, lightbox click-only, `content/ro/evenimente/_index.md` raw `<img>`
without `alt`, 5× `#` headings in `materiale/ecuatia_dreptei.md` (8 in `combinatorica.md`, 14 in
`floss/pandoc.md`), `static/documents/*.pdf` → `pdfinfo`: `Tagged: no`, YouTube iframe without
`loading="lazy"`, hotlinked Wikimedia image with `utm_*` params in `blog/1_etimologie.md`, English
paragraphs inside `ro/cookies.md`, no skip link in built pages, theme forced to `light` ignoring
`prefers-color-scheme`.

---

## 1. Urgent

### U1. Analytics without consent (legal, ePrivacy/GDPR) — see also old audit U1
- `layouts/partials/docs/inject/head.html` loads `{{ template "_internal/google_analytics.html" . }}` on
  every page; the cookie banner in `inject/body.html` only writes `localStorage` — GA has already fired.
  `hugo.toml` has no `[privacy.googleAnalytics]`.
- **Fix:** add
  ```toml
  [privacy.googleAnalytics]
  anonymizeIP = true
  respectDoNotTrack = true
  ```
  and load GA dynamically only on "Acceptă" (inject `gtag` in the accept handler), or replace with
  consent-free self-hosted Plausible/Umami. Then sync `content/ro/privacy.md` + `cookies.md` with reality
  (already on your `instructiuni.md` TODO).

### U2. Review carousel: autoplay, no pause, not keyboard-operable (WCAG 2.2.2, 2.1.1, 2.5.8) — old audit U5
- `layouts/shortcodes/carousel.html` (homepage): `setInterval(nextSlide, 5000)` with no pause/stop button;
  dots are `<span class="carousel-dot">` with click handlers (not focusable, < 24 px); no
  `prefers-reduced-motion` check; all slides stay in the accessibility tree.
- **Fix:** real `<button>` dots with `aria-label="Recenzie 3 din 8"` + `aria-current`; a pause/play toggle
  button with `aria-pressed`; `aria-roledescription="carousel"` on the region; `aria-hidden="true"` on
  off-screen slides; stop the timer when `matchMedia('(prefers-reduced-motion: reduce)')` matches and on
  focus-within.

### U3. Lightbox is mouse-only (WCAG 2.1.1, 4.1.2) — old audit U5
- `inject/footer.html`: images get click handlers only; overlay has no `role="dialog"`/`aria-modal`; focus
  is not moved in, trapped, or restored; Esc works but focus is lost.
- **Fix:** wrap each content image in a `<button>` (or add `tabindex="0"` + Enter/Space handler),
  `role="dialog" aria-modal="true" aria-label="Imagine mărită"` on the overlay, move focus to it on open,
  simple focus trap, restore focus on close, copy the source `alt` (you do) — and remove the static
  `alt="Enlarged view"` fallback.

### U4. No skip-to-content link; toggle checkboxes have no visible focus (WCAG 2.4.1, 2.4.7/2.4.11) — old audit U3
- Theme `baseof.html` has no skip link. **Fix:** copy `themes/hugo-book/layouts/baseof.html` →
  `layouts/baseof.html`, add `<a href="#book-page-content" class="skip-link">…</a>` first in `<body>` +
  `id`/`tabindex="-1"` on `.book-page`, skip-link CSS in `_custom.scss`; fix the
  `input.toggle:focus-visible` selector in `_custom.scss` (the theme's `+ label` never matches).

### U5. Images without alt / raw HTML bypassing the render hook (WCAG 1.1.1)
- `content/ro/evenimente/_index.md:38` `<img src="/images/datamathlab_2026.webp" />` — no alt. Raw `<img>`
  in Markdown bypasses `layouts/_default/_markup/render-image.html`.
- **Fix:** add alt in content; harden the hook to **fail the build** on empty alt:
  `layouts/_default/_markup/render-image.html` → `{{ if not .Text }}{{ errorf "image without alt: %s" .Destination }}{{ end }}`.
  Prefer Markdown `![alt](…)` everywhere so the hook applies.

### U6. Multiple `<h1>` per learning-material page (WCAG 1.3.1) — old audit U6
- `materiale/ecuatia_dreptei.md` has 5 `#` headings, `combinatorica.md` 8, `floss/pandoc.md` 14.
  Screen-reader users navigate by headings; the outline is meaningless.
- **Fix:** one `#` per page; demote the rest to `##`/`###`. Belt-and-braces: add a render-heading hook
  (`layouts/_default/_markup/render-heading.html`) that demotes level-1 headings after the first, and a CI
  grep that fails on `^# ` appearing twice in a file.

### U7. Math: client-side KaTeX from a CDN, no fallback, no reflow handling — old audit U7
- `inject/head.html` pulls `katex@0.16.11` from jsdelivr **without SRI**, `auto-render` runs on
  `DOMContentLoaded`. If the CDN is blocked/JS off → raw `$…$` TeX. KaTeX's default `htmlAndMathml` output
  is good for screen readers — keep it; add `output: 'htmlAndMathml'` explicitly. Display math has no
  `overflow-x:auto` → page-level horizontal scroll on mobile (1.4.10).
- **Fix:** self-host KaTeX into `assets/` (like adrianmanea.xyz already does — copy that pattern) or render
  server-side with a `render-passthrough.html` hook using Hugo's `transform.ToMath`; add SRI if you keep
  the CDN; CSS `.katex-display { overflow-x:auto; overflow-y:hidden; }`.

### U8. Downloaded PDFs are untagged (WCAG in documents)
- `static/documents/*.pdf`: `pdfinfo` → `Tagged: no`, no `/Lang`, no title.
- **Fix:** regenerate from `materiale_edu` with the tagging recipe in `materiale_coga.md` (U1 there),
  copy over, and make the **HTML page the canonical accessible version** — label the PDF link
  "PDF (pentru tipar)" and keep "citește online" as the primary action. Verify with veraPDF.

---

## 2. Medium priority

### M1. Contrast — re-measure after the palette update (WCAG 1.4.3)
- Old audit measured light links `#008e80` on ivory = 3.97:1 and dark links `#e56a77` on `#3b4758` =
  2.99:1, `.hl-block`/`black !important` ≈ 1.8–2.0:1, `.review-date` 2.74:1. `assets/_custom.scss` now
  declares `--teal:#005f53` (7.44:1) etc. in `:root`, but there are `!important` `html[data-theme]`
  blocks and legacy `--color-link` assignments — **re-run axe/WAVE on the current build** and fix whatever
  still fails (aim ≥ 4.5:1 text, ≥ 3:1 large text/UI).

### M2. Theme forced to light; toggles lack accessible state (COGA + 4.1.2)
- Same pattern as the personal site: `inject/head.html` defaults `localStorage || 'light'`; `!important`
  theme blocks in `_custom.scss` override `prefers-color-scheme: dark`; `#theme-toggle` has no
  `aria-pressed`; language switcher uses flag emoji (`🇬🇧`/`🇷🇴`) announced as "regional indicator…" and
  rendered as letters on Windows.
- **Fix:** `matchMedia` default, `aria-pressed`, `aria-hidden` on emoji, text labels, `hreflang`.

### M3. Cookie banner not announced, no way to reopen (3.2.6 Consistent Help, COGA)
- `inject/body.html` banner has no `role="region" aria-label="Cookie-uri"`; after choosing, preferences
  can't be changed. **Fix:** add the region role + `aria-live="polite"` announcement, and a
  "Setări cookie-uri" link in the footer (`inject/footer.html`) that clears `localStorage` and re-shows
  the banner.

### M4. Search results not announced (4.1.2/3.2.6)
- `BookSearch = true`; theme's `search.html` has `<ul id="book-search-results">` with no live region.
  **Fix:** override `layouts/partials/docs/search.html`, add `role="status" aria-live="polite"` to the
  results, and document the `/` / `Ctrl+K` shortcut on the search page.

### M5. Third-party embeds and hotlinks leak visitor data (privacy → COGA trust)
- YouTube iframe on `content/ro/_index.md:90` (has good `title`, but no `loading="lazy"`; ~1 MB of
  third-party JS on first paint) — add `loading="lazy"`, or use a click-to-play facade
  (`lite-youtube-embed`, works on Linux in any browser).
- `content/ro/blog/1_etimologie.md:93` hotlinks a Wikimedia image **with `utm_*` tracking params** —
  downloads leak visitor IPs to a third party. **Fix:** self-host in `static/images/`.
- KaTeX CDN (U7) — same category.

### M6. Language of parts (WCAG 3.1.2)
- `content/ro/cookies.md` contains whole English paragraphs on a `lang="ro"` page. **Fix:** wrap them in
  `<span lang="en">` or translate.

### M7. Meta descriptions missing on material pages → garbage `og:description`
- Add `description = "…"` front matter to every page under `materiale/` and `cursuri/`.

### M8. `facts-engine` shortcode: hidden heading + hash navigation without focus management
- `layouts/shortcodes/facts-engine.html` sets `h2#cuprins { display:none }` (removes it from the a11y tree
  — acceptable since it's replaced, but ensure the replacement ToC links are real anchors), and
  `#pt-N` hash routing swaps views **without moving focus** — keyboard/SR users are left behind.
  **Fix:** after showing a single fact, `targetCard.setAttribute('tabindex','-1'); targetCard.focus()`.
  Buttons contain emoji + text — fine, but keep the text meaningful without the emoji.

### M9. facts/material pages: COGA structure for long learning pages
- Material pages run 300–1300 lines. COGA asks for: a summary at top, consistent section pattern,
  defined terms, no time pressure, predictable navigation. You already have good prose and a consistent
  sidebar (keep it — that *is* 3.2.6/COGA "consistent layout"). **Add:** a "Recapitulare / Ce reții" box at
  the top of each material (use the existing `box`/`important` shortcodes), a small glossary of recurring
  terms per page, and one `#` heading per page (U6).

### M10. Target sizes (WCAG 2.5.8, 24×24 px): carousel dots/arrows, menu toggle labels
- Check in DevTools; bump padding in `_custom.scss`.

---

## 3. Low priority

- **L1.** `aria-current="page"` on the active sidebar link; `aria-label` on the three nav landmarks.
- **L2.** Decorative emoji in UI (`🌙/☀️/🎲/📌`) → `aria-hidden="true"` spans or `::before` with
  `speak: none`-equivalent (CSS `content` is already skipped by most SRs; keep it out of accessible names).
- **L3.** `theme-color` dark value doesn't match the real dark background — fix in `_custom.scss`/head.
- **L4.** `figcaption` `font-weight: 200` — raise to 400 for readability.
- **L5.** Print stylesheet check for material pages (students print them).
- **L6.** `data/reviews.json` publishes named testimonials — confirm you have consent for each (GDPR),
  and keep avatar `alt` = author name (you do) — good.
- **L7.** Raw HTML + inline styles in Markdown (`ecuatia_dreptei.md` has dozens of `<span style=…>`)
  forces `unsafe = true`; migrate repeated patterns to the `box`/`highlight`/`important` shortcodes over time.

---

## 4. Step-by-step TODO (priority order, then complexity) with tools

Tools on **openSUSE Tumbleweed (Linux)**:

| Tool | Purpose | Linux? |
|---|---|---|
| `hugo`, `dart-sass` (standalone binary — npm `sass` does NOT work with Hugo's `css.Sass`) | build/serve | yes (`zypper install hugo`) |
| axe DevTools / WAVE extensions, Lighthouse, Firefox Accessibility Inspector | find issues in the live DOM | yes (browser extensions work on Linux) |
| `pa11y-ci` + axe-core (`npm i -g pa11y-ci`), `html-validate`, `vnu.jar`, `markdownlint-cli`, `lychee` | automated checks of built site | yes (Node/Java) |
| **Orca** (`zypper install orca speech-dispatcher-espeak`) + Firefox/Chromium; **Evince/Okular** for PDFs | manual SR pass — the core COGA test | Linux-native (NVDA/JAWS = Windows-only; VoiceOver = macOS-only) |
| veraPDF (Java, verapdf.org) for `static/documents/*.pdf`; `poppler-utils`, `qpdf` | PDF/UA + structure checks | yes. **PAC 2024 = Windows-only; Acrobat Pro = Win/mac; PDFix Lite = macOS** |
| KDE Contrast / WebAIM contrast checker (web) | contrast | yes (CCA app = Win/mac only) |
| LanguageTool (CLI/desktop) for RO prose, `vale`/`proselint` for EN | plain-language pass (COGA) | yes |
| `lite-youtube-embed` | privacy/perf facade for YouTube | yes (any browser) |
| self-hosted Plausible/Umami (optional GA replacement) | consent-free analytics | yes (self-host via Docker/zypper package) |

### TODO list

1. **Baseline scan.** `hugo server` → axe + WAVE + Lighthouse on home (ro/en), one material page,
   courses, contact; `npx pa11y-ci http://localhost:1313/`; `hugo --minify` then `java -jar vnu.jar public/`.
   Triage into this file's U/M/L.
2. **Consent + analytics (U1, M3).** Add `[privacy.googleAnalytics]` to `hugo.toml`; move GA out of
   `inject/head.html` into the banner's accept handler in `inject/body.html`; add `role="region"
   aria-label` + `aria-live` to the banner; add a footer "cookie settings" link that reopens it; update
   `privacy.md`/`cookies.md` (also fixes M6 by translating or `lang="en"`-wrapping the English parts).
3. **Base layout overrides (U4).** Copy theme `baseof.html` → `layouts/baseof.html`; add skip link, nav
   `aria-label`s, `aria-current`; fix toggle focus ring in `_custom.scss`; add global
   `@media (prefers-reduced-motion: reduce)` block.
4. **Carousel (U2).** Rewrite `layouts/shortcodes/carousel.html`: button dots with `aria-label`/`aria-current`,
   pause button, `aria-roledescription="carousel"`, `aria-hidden` on inactive slides, reduced-motion + focus stop.
5. **Lightbox (U3).** `inject/footer.html`: focusable image buttons, `role="dialog" aria-modal`, focus trap
   + restore, real alt.
6. **Alt text enforcement (U5).** Fix `evenimente/_index.md` img; make `render-image.html` `errorf` on empty
   alt; grep-audit all content for raw `<img` without `alt`; add markdownlint MD045 to CI.
7. **Headings (U6).** Demote extra `#` to `##` in the 6 files listed; add render-heading hook + CI grep.
8. **Math (U7).** Self-host KaTeX into `assets/` (copy the pattern from adrianmanea.xyz) or SSR via
   `render-passthrough.html` + `transform.ToMath`; explicit `output:'htmlAndMathml'`; `.katex-display`
   overflow CSS; verify MathML announcement in Orca.
9. **PDFs (U8).** Regenerate tagged PDF/UA-1 from `materiale_edu` (see `materiale_coga.md` steps 1–7),
   copy into `static/documents/`, verify (`pdfinfo` → `Tagged: yes`; veraPDF), relabel links so HTML is
   primary.
10. **Toggles (M2).** `inject/head.html` + `menu-after.html`: `matchMedia` dark default, `aria-pressed`,
    `aria-hidden` emoji, text labels, `hreflang`; remove `!important` theme blocks.
11. **Search (M4).** Override `layouts/partials/docs/search.html` with `role="status" aria-live="polite"`.
12. **Third-party hygiene (M5).** `loading="lazy"` on the YouTube iframe or lite-youtube facade;
    self-host the Wikimedia image (drop `utm_*`).
13. **Meta descriptions (M7)** on all `materiale/` + `cursuri/` pages.
14. **facts-engine focus management (M8).** Focus the revealed card on hash navigation.
15. **COGA content pass (M9).** "Recapitulare" box at top of each material page; glossary of terms; one
    idea per paragraph; LanguageTool RO pass; keep the consistent sidebar + contact placement.
16. **Contrast + target size re-measure (M1, M10)** on the current build with axe; fix remaining pairs;
    ensure all interactive targets ≥ 24×24 CSS px.
17. **CI.** `.github/workflows/`: `hugo --minify` → vnu.jar → pa11y-ci → lychee → markdownlint →
    veraPDF on `static/documents/*.pdf` → fail on errors.
18. **Re-audit with Orca** after deploy: headings outline per material page, links list descriptive,
    carousel operable by keyboard, lightbox dialog announced, banner announced, math spoken via MathML,
    PDFs tagged. Record results here and in `accessibility-audit.md`.

### Acceptance checks ("done" means)
- axe/WAVE/pa11y: **0** A/AA violations on ro+en across home, a material, a course, contact, cookies.
- Keyboard-only pass: skip link first, every control operable with visible focus, carousel pausable,
  lightbox dialog focus-managed, no keyboard traps.
- Orca: one h1 per page, sensible heading tree, descriptive link list, carousel announced as carousel,
  search results announced, MathML math read, tagged PDFs read in order.
- Network: with cookies declined, **no** requests to google-analytics/googletagmanager/jsdelivr(if
  self-hosted)/upload.wikimedia.org.
- `pdfinfo static/documents/*.pdf` → `Tagged: yes`, `Lang: ro`, title set; veraPDF PDF/UA-1 clean.
- `prefers-reduced-motion: reduce` stops the carousel; OS dark mode respected with no stored choice;
  contrast ≥ 4.5:1 (text) / 3:1 (UI) everywhere; targets ≥ 24 px.

---

## Final Automated and Manual Checks

Yes. There's a well-established stack for this, and on openSUSE Tumbleweed almost all of it runs natively. Here's the standard toolchain, what "all green" means, and exact commands.

### The standards you're checking against

| Target | What it is | Tool that checks it |
|---|---|---|
| **WCAG 2.2 AA** (web) | The W3C standard; includes the COGA-relevant SCs 2.4.11, 2.5.7, 2.5.8, 3.2.6, 3.3.7, 3.3.8 | axe-core, HTML_CodeSniffer, IBM Equal Access, WAVE, Lighthouse |
| Valid HTML5 | prerequisite for everything else | W3C Nu validator (`vnu.jar`) |
| **PDF/UA-1** (ISO 14289) for your PDFs | Tagged PDF standard | **veraPDF** (the reference validator) |
| EN 301 549 / EAA | The EU procurement standard (in force since June 2025) — relevant if you sell courses to schools/NGOs; it references WCAG. You can produce a **VPAT/ACR** from your test reports | VPAT template (ITI) + your axe/veraPDF reports |

### Install on openSUSE Tumbleweed

```bash
sudo zypper install hugo nodejs20 npm java-21-openjdk poppler-utils qpdf mupdf-tools \
  orca speech-dispatcher-espeak lychee          # lychee falls back to: cargo install lychee
npm install -g pa11y-ci axe-core html-validate markdownlint-cli2 lighthouse @lhci/cli
# veraPDF (Java, runs fine on Linux): download GUI+CLI from https://verapdf.org/downloads
# axe DevTools / WAVE / IBM Equal Access extensions: install in Firefox or Chrome on Linux
```

**Not available on Linux** (flagging per your request): NVDA & JAWS (Windows-only screen readers → use **Orca**), PAC 2024 and Adobe Acrobat Pro's accessibility checker (Windows / Win+mac), Colour Contrast Analyser (Win/mac → use KDE's Contrast widget or WebAIM's web checker), Accessibility Insights desktop app (Windows; its *web extension* works in Linux browsers).

### The "all green" automated pipeline (per Hugo site)

1. **Build:** `hugo --minify --gc` → `public/`
2. **HTML validation — must be 0 errors:** `java -jar vnu.jar public/` (download `vnu.jar` from github.com/validator/validator releases)
3. **Automated accessibility — must be 0 issues at WCAG2AA:** `pa11y-ci` with a `.pa11yci.json` at the repo root:
   ```json
   { "defaults": { "standard": "WCAG2AA", "runners": ["axe", "htmlcs"], "threshold": 0,
                   "chromeLaunchConfig": { "args": ["--no-sandbox"] } },
     "urls": ["http://localhost:1313/", "http://localhost:1313/en/",
              "http://localhost:1313/materiale/ecuatia-dreptei/", "http://localhost:1313/contact/"] }
   ```
   Run `hugo server` in one terminal, `pa11y-ci` in another. `threshold: 0` = any violation fails.
4. **Lighthouse CI** (`lhci autorun` with `lighthouserc.js`, budget: accessibility category = 100 on key pages) — catches things axe misses (target size, color contrast, tap targets).
5. **Extra rule coverage:** IBM Equal Access Accessibility Checker — browser extension for manual passes, or Node CLI `@ibm/iba-ace-cli` in CI (`iba-ace-cli --ruleset latest ...`). Use it alongside axe, not instead.
6. **Links:** `lychee public/` (plus `hugo --printPathWarnings` for broken `ref`/`relref`).
7. **Content lint:** `markdownlint-cli2 "content/**/*.md"` with MD045 (image alt) enabled + a custom grep for bare `[aici]`/`[here]` link text and double `^# ` headings.
8. **PDFs:** `verapdf --flavour ua1 static/documents/*.pdf` → 0 failed rules; plus `pdfinfo f.pdf | grep -E 'Tagged|Lang|Title'` → `Tagged: yes`. Same for `materiale_edu/*/tex/build/*.pdf`.
9. **CI:** one GitHub Actions workflow (`.github/workflows/a11y.yml`) running steps 1–8 on every push; green = build passes. Ubuntu runners have Java and Node, so vnu/veraPDF/pa11y-ci all work there.

### What automation can't cover (the COGA part — do these manually, they're the point of your specialization)

Automated tools catch only ~30–40% of WCAG issues, and almost none of the COGA ones. The manual gates that "all green" must also include:

- **Keyboard-only pass**: Tab from page load — skip link appears first, every control reachable with a *visible* focus ring (2.4.7/2.4.11), carousel pausable, lightbox focus-trapped, no traps.
- **Screen-reader pass with Orca** (Firefox; Evince/Okular for PDFs): one h1 per page, sensible headings/links/landmarks lists, math announced via MathML, PDFs read in order with bookmarks.
- **axe DevTools / WAVE** spot-checks in the browser on the live site (they see the real DOM, unlike static scans).
- **Contrast**: axe/Lighthouse + KDE Contrast on your palette tokens (≥ 4.5:1 text, ≥ 3:1 UI).
- **Media/user-preference emulation** in DevTools: `prefers-reduced-motion: reduce` (carousel stops), `prefers-color-scheme: dark` (respected), forced-colors mode, and the **WCAG 1.4.12 text-spacing bookmarklet** (from webstandards.org) — all must keep the site usable.
- **Plain-language/readability** (COGA core): LanguageTool CLI for Romanian prose, `vale`/`proselint` for English, plus a reading-level check (e.g. `textstat`).
- **Cognitive walkthrough**: can a first-time visitor find contact/prices in ≤ 3 clicks from any page (3.2.6 consistent help), is help in the same place on every page, no time limits, no CAPTCHA-style auth (3.3.8), no re-asking for info (3.3.7)?
- Optionally, real **user testing** with people with cognitive disabilities — COGA's own guidance says this is the only way to validate the cognitive aspects.

So: automated tools give you the green CI badge for WCAG 2.2 AA + PDF/UA-1; the manual Orca/keyboard/readability gates are what make it genuinely COGA-compliant — and they're also your portfolio evidence.
