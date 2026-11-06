# Performance Audit — poligon-edu.ro

Measured on a production build: `hugo --gc --minify` (Hugo v0.168.0 extended), 84 pages,
428 static files, **build time 0.52 s**, total output **43 MB** (of which `static/images`
= 31 MB, `static/fonts` = 4.3 MB). Page weights below are computed from the built HTML +
all local assets it references, raw and gzipped (GitHub Pages serves gzip/brotli). Third-party
requests counted separately. Baseline context: the site is fully static on the GitHub Pages
CDN with `--minify` in CI — the framework is not the bottleneck; assets are.

## Severe

### 1. Unoptimized, eager-loaded images with no dimensions or responsive variants
- **0 occurrences of `loading="lazy"`** in the whole site; no `width`/`height` on content
  images (→ CLS), no `srcset`, no modern formats for most images.
- Homepage `/`: **4.5 MB raw of images** (`bac_non_ro.png` 1.5 MB, `joshua_stiinte.png`
  1.3 MB, `teatru_s9.png` 468 K, …) all loaded eagerly on first paint.
- `/cursuri/arhiva/istorie_mate/`: **7.1 MB raw** (`real_set.jpg` 3.6 MB + `limit.jpg`
  3.2 MB; JPGs barely compress — gzip ≈ raw) for two illustrations.
- `/materiale/ecuatia-dreptei/`: 233 K HTML (32 K gz) + `descartes_viete.png` 969 K among
  30 images (figures are SVG and light — good).
- **Fix:** move content images from `static/images` to `assets/` (or page bundles) and process
  them with Hugo's image pipeline (`.Resize` / `.WebP` / `.AVIF`, `srcset` + `sizes`), generate
  `width`/`height`, `loading="lazy"` + `decoding="async"` in the `render-image.html` hook,
  `fetchpriority="high"` on the LCP image. This alone should cut typical page weight by 70–90%.

### 2. Redundant third-party KaTeX from jsdelivr on all 84 pages
- `layouts/partials/docs/inject/head.html` loads `katex.min.css` (render-blocking) +
  `katex.min.js` (264 K) + `auto-render.min.js` from `cdn.jsdelivr.net` on **every page**
  (171 jsdelivr references in the build) — even though math is now rendered server-side to
  MathML (`render-passthrough.html`), so the client-side renderer has nothing left to do.
- Cost per page: ~300 KB+ of JS/CSS/fonts from a third party, a render-blocking external
  stylesheet, a single point of failure, and a GDPR third-party request. There is also an
  unreferenced local copy in `static/katex/` (1.5 MB).
- **Fix:** delete the three KaTeX `<script>`/`<link>` tags and the auto-render inline script
  from `inject/head.html`; keep the local `static/katex` only if some page still needs it
  (none do), otherwise remove. If you ever need client math again, self-host it.

### 3. Google Analytics on every page, unconditionally
- `gtag/js` (async) + config on all 84 pages (114 references to `googletagmanager.com`) —
  adds a DNS/TLS/HTTP round-trip to a third party and processes personal data before consent
  (see accessibility audit). **Fix:** consent-gate it or replace with a lightweight,
  cookieless, self-hosted counter.

### 4. YouTube embed on the homepage without `loading="lazy"`
- `/` iframes `youtube-nocookie.com/embed/…` immediately (no `loading` attribute), pulling
  ~1 MB of third-party JS on landing. **Fix:** add `loading="lazy"` (and optionally a
  facade: show the thumbnail, load the iframe on click).

## Moderate

### 5. Font loading strategy
- `STIX Two Math` ships only as `.woff` (756 K, no woff2) and is used on every math page;
  with `font-display: swap` the formulas reflow late (CLS). Convert to woff2 + preload it on
  math pages.
- Switzer declares 15 weights × woff2 **and** woff (~600 K deployed; modern browsers only
  fetch the woff2). Drop the `.woff` fallbacks or subset them.
- Unreferenced font files are deployed in `static/fonts` (Crimson Pro per-weight statics
  ~1.5 MB, Martian Mono cyrillic-ext statics, etc.) — only the variable files listed in
  `assets/_fonts.scss` (41 `url()` refs) are actually used. Delete the rest; total
  `static/fonts` is 4.3 MB.
- **Fix:** preload the 2–3 critical faces (Crimson Pro latin normal/italic, Switzer
  Regular/Bold), `font-display: swap` is fine then; subset to latin + latin-ext.

### 6. Search index weight
- Every page loads `ro.search.min.*.js` (module, deferred) which fetches the full
  `ro.search-data.min.*.json` (~208 K per language) plus `fuse.min.mjs` on first focus.
  Acceptable, but a static index like **Pagefind** would be smaller, need no runtime
  library, and ship prebuilt UI — worth it if search stays.

### 7. Math-heavy pages have a large DOM
- `/materiale/ecuatia-dreptei/`: 233 K raw / 32 K gz HTML, 503 `<math>` elements. Gzip makes
  transfer fine; the cost is DOM/parse on low-end phones. Acceptable for now — just avoid
  adding client-side re-rendering (see severe #2).

### 8. Caching on GitHub Pages
- GitHub Pages caps `Cache-Control: max-age=600` for everything and doesn't support custom
  headers, so even fingerprinted assets revalidate every 10 min. Mitigation: keep
  `resources.Fingerprint` (already used for CSS/JS) — done — and keep HTML small. If you ever
  move to Cloudflare/Netlify, add long-lived cache headers for fingerprinted files.

## Light

- **Dead deployed assets**: `static/mermaid.min.js` (3.1 MB), `static/katex/` (1.5 MB),
  `static/asciinema/` (200 K) are not referenced by any built page. Remove them — they cost
  nothing at runtime but bloat the repo/deploy and widen the attack surface.
- **Source images are heavy**: `static/images` = 31 MB (top: `real_set.jpg` 3.6 MB,
  `limit.jpg` 3.2 MB, `music.jpg` 2.1 MB, `bac_non_ro.png` 1.5 MB). Even after the pipeline
  in severe #1, recompress the masters. (`symmetry.avif` next to `symmetry.jpeg` shows you
  already have AVIF in the toolchain.)
- **No `robots.txt`** (sitemap.xml is generated — good; canonical links present — good).
  Add a minimal `static/robots.txt` pointing to the sitemap.
- `theme-color` meta mismatch is cosmetic (see a11y audit).
- Dev-only `livereload.js` appears in local builds but not in the CI build — correct as is.
- Build performance itself is excellent (0.52 s / 84 pages; `css.Sass` libsass deprecation
  warning is worth switching to `dartsass` eventually, but it's a CI-time concern only).

## Should we migrate to Astro? (performance + accessibility verdict)

**Short answer: no — not now.** The evidence above shows the bottlenecks are assets and
third-party scripts, not the framework: Hugo already emits fully static, minified HTML in
half a second and serves it from the GitHub Pages CDN. Astro's output would be the same kind
of static HTML, so there is no measurable performance headroom to gain. On accessibility,
every urgent item in the companion audit lives in your templates/SCSS/shortcodes, not in
Hugo — migrating would mean re-implementing (and risking regressions on) the same
skip-link/contrast/heading/keyboard issues in a new codebase.

Where Astro would genuinely help this site:
- `astro:assets` / `<Image>` automate responsive images + modern formats — but Hugo
  Extended does the same via render hooks + the resources pipeline (severe #1).
- Content Collections validate front matter at build time (would catch missing
  `description`, missing alt, etc.).
- `remark-math` + `rehype-katex` (MathML output) mirrors your current server-side MathML
  setup, so your `$…$` workflow survives.
- Pagefind would replace the fuse.js search index (moderate #6).
- Islands/partial hydration suit the lightbox/carousel/facts-engine — but your current
  inline scripts are a few KB total and already fine.

What migration would cost: re-building the hugo-book layout (filetree sidebar, ToC, search,
theme + language toggles), the 7 shortcodes, both render hooks, ~950 lines of `_custom.scss`,
the cookie banner, lightbox and facts-engine, plus i18n routing and the GitHub Actions
deploy — weeks of work with real regression risk, for zero measurable gain on a site whose
main evolution is *more accessible educational Markdown*.

**Recommendation:** stay on Hugo and fix the audits in place (image pipeline, remove CDN
KaTeX, consent-gate analytics, skip link, contrast, headings, keyboard support, content
guidelines for `materiale/*.md`: alt text, one `h1`, MathML kept server-side, tagged PDFs).
Re-evaluate Astro only if you later add app-like interactivity (accounts, live exercises);
even then, Astro islands or a small JS layer inside Hugo is the cheaper first step.
