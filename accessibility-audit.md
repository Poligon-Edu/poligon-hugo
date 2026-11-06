# Accessibility Audit — poligon-edu.ro

Scope: full Hugo build (`hugo --gc --minify`, v0.168.0, 84 pages), theme `hugo-book` +
custom `layouts/` and `assets/_custom.scss`, content in `content/ro` and `content/en`.
The reference page for educational materials is `content/ro/materiale/ecuatia_dreptei.md`.

WCAG references are given per item (2.2 = WCAG 2.2). "Urgent" = blocks access for a whole
group of users or creates legal exposure; "Recommendable" = WCAG AA failures and best
practices that clearly degrade the experience; "Nice to have" = polish.

## Urgent

### 1. Analytics loads before / without consent (legal risk, GDPR/ePrivacy)
- `layouts/partials/docs/inject/head.html` includes `{{ template "_internal/google_analytics.html" . }}`
  on **every page, unconditionally** (114 references to `googletagmanager.com` in the built site).
- The cookie banner in `layouts/partials/docs/inject/body.html` only stores a choice in
  `localStorage`; the code comment even says "Trigger any custom analytical scripts here if
  needed" — but GA is already loaded in `<head>`, so tracking happens regardless of the answer.
- `hugo.toml` has no `[privacy.googleAnalytics]` section, so `anonymizeIp` is off and Do Not
  Track is not respected.
- **Fix:** load GA only after an "accepted" choice (dynamic `gtag` injection in `body.html`),
  add `[privacy.googleAnalytics] anonymizeIP = true; respectDoNotTrack = true`, or replace GA
  with a consent-free/self-hosted analytics (Plausible, Umami) or drop it. Update
  `content/ro/privacy.md` and `cookies.md` to match reality.

### 2. Color contrast failures (WCAG 1.4.3, AA)
Measured ratios (assets/_custom.scss palette):

| Where | Foreground / background | Ratio | Required |
|---|---|---|---|
| Light theme links (teal `#008e80` on ivory `#fffdf0`) — all body + top-menu links | 3.97:1 | 4.5:1 (normal text) |
| Dark theme links (`#e56a77` on `#3b4758`) | 2.99:1 | 4.5:1 |
| Dark theme `.hl-block` / `.important-block` — `color: black !important` on pale tint over `#242b37` | 1.97:1 / 1.77:1 | 4.5:1 |
| `.review-date` (navy at 55% opacity) on card background | 2.74:1 | 4.5:1 |

Body text itself is fine (9.23:1 both themes). **Fix:** darken light-mode teal (e.g.
`#00756a` ≈ 5.3:1), lighten the dark-mode link color (e.g. `#ff8f9b`), replace
`color: black !important` in `.hl-block`/`.important-block` with `var(--navy)`, and raise
`.review-date` opacity.

### 3. No skip-to-content link (WCAG 2.4.1, A)
There is no "skip" element anywhere in the built pages. Keyboard users must tab through the
entire sidebar menu (dozens of links) before reaching the article on every page.
**Fix:** add a visually-hidden-but-focusable skip link as the first element in
`themes/hugo-book/layouts/baseof.html` (or an override in `layouts/_default/baseof.html`)
targeting the `<main>`/article, e.g. `<a href="#content" class="skip-link">Sari la conținut</a>`.

### 4. Images without alt text (WCAG 1.1.1, A)
Two images in the whole site have no `alt`:
- `content/ro/evenimente/_index.md` → `/images/datamathlab_2026.webp`
- `content/ro/materiale/ecuatia_dreptei.md` → `/images/figures/slope_diy.svg` (raw `<img>` HTML)

Raw `<img>` tags in Markdown bypass `layouts/_default/_markup/render-image.html`.
**Fix:** add meaningful `alt` in the content; make the render-image hook fail the build when
`alt` is empty (`.Attributes` / check `.Text`), and prefer Markdown image syntax over raw HTML.

### 5. Keyboard-inoperable interactive components (WCAG 2.1.1 A, 2.4.7 AA, 2.2.2 AA)
- **Review carousel** (`layouts/shortcodes/carousel.html`, used on the homepage): auto-advances
  every 5 s with **no pause/stop control** (2.2.2); the dot navigation items are `<span>`s with
  click handlers — not focusable, not keyboard-operable (2.1.1); no `prefers-reduced-motion`
  handling; all slides stay in the accessibility tree even when off-screen.
- **Lightbox** (`layouts/partials/docs/inject/footer.html`): images become clickable but are not
  focusable/Enter-operable; the overlay has no `role="dialog"`/`aria-modal`, focus is not moved
  into it nor trapped, and the enlarged `<img>` has a static `alt="Enlarged view"`.
- **Menu/ToC toggles** (`input.toggle` in `baseof.html`): 0×0, `opacity: 0` — focusable but with
  no visible focus indicator (the `input.toggle:focus-visible + label` rule in `_main.scss`
  never matches, since the next sibling is another input) — 2.4.7.

**Fix:** carousel — real `<button>`s for dots, a pause button, `aria-roledescription="carousel"`,
`aria-hidden` on inactive slides, stop on `prefers-reduced-motion`; lightbox — wrap images in
`<button>` or add `tabindex` + key handler, `role="dialog" aria-modal="true"`, focus trap + restore,
copy the source `alt`; toggles — give the visually-hidden inputs a visible focus ring via a
sibling/label selector that actually matches.

### 6. Broken heading structure — multiple `<h1>` per page (WCAG 1.3.1, A)
`content/ro/materiale/ecuatia_dreptei.md` has **5 `#` headings** (lines 7, 200, 309, 329, 389) →
5 `<h1>` in the built page; `floss/pandoc.md` has 14. Screen-reader users navigate by headings,
so the outline is meaningless. The sidebar brand is also an `<h2>` that precedes the page `<h1>`.
**Fix:** one `#` per page (the title), `##` for sections — either edit the Markdown or demote
headings in a render-heading hook. Add a lint ( CI check) that fails on multiple `^# ` per file.

### 7. Math accessibility — the core of your educational materials
Good news first: math is rendered **server-side to MathML** with a TeX `<annotation>`
(`layouts/_markup/render-passthrough.html`, `transform.ToMath`), which is the most accessible
option — no client JS needed, and 503 `<math>` elements on the reference page.
Remaining urgent-ish gaps:
- **No overflow handling for long block equations**: `math[display="block"]` gets only a margin
  in `_custom.scss`; wide `align*` environments (e.g. the exercițiul 9 resolutions) cause
  page-level horizontal scrolling on mobile. Add `overflow-x: auto` on a wrapper.
- The STIX Two Math font (see performance audit) swaps in late, reflowing the formulas.
- Screen-reader support for MathML is uneven (VoiceOver+MathML ok, NVDA needs MathPlayer, JAWS
  ok). Consider adding `role="math"` and, for complex display formulas, a visually hidden
  textual description via the `<annotation>` element (already present — keep it).

## Recommendable

- **OS dark mode is ignored**: the inline script in `inject/head.html` does
  `localStorage.getItem('theme') || 'light'` and the `html[data-theme="light"]` rules in
  `_custom.scss` use `!important`, so a user with `prefers-color-scheme: dark` gets the light
  theme unless they manually toggle. Respect the media query when no choice is stored
  (this is also what the `@media (prefers-color-scheme: dark)` block in `_custom.scss`
  intends but loses to).
- **No `prefers-reduced-motion` handling anywhere** (carousel auto-advance, lightbox/card
  transitions, hover transforms). Add a global `@media (prefers-reduced-motion: reduce)` block
  and stop the carousel timer.
- **Cookie banner is not announced** (no `role="region"` + `aria-label`), and there is no way
  to re-open preferences after choosing. Make it a labelled region and add a "Cookie settings"
  link in the footer that clears `localStorage`.
- **Theme toggle button** (`inject/menu-after.html`) has no `aria-pressed`; its state is only
  conveyed by an emoji + text swap.
- **Language switcher uses flag emoji** (`🇬🇧`/`🇷🇴`): screen readers announce "regional
  indicator G B…", and Windows renders them as plain letters. Use a text label + `aria-label`.
- **Brand link's accessible name is "Logo"**: `_custom.scss` hides the title `<span>` with
  `display: none` and `font-size: 0`, so the link in the sidebar announces only the img alt.
  Use a proper visually-hidden class instead.
- **Language of parts (WCAG 3.1.2)**: `content/ro/cookies.md` contains whole English paragraphs
  (lines ~28–36) on a `lang="ro"` page with no `lang="en"` wrapper.
- **Meta description is garbage on material pages**: `ecuatia_dreptei` gets a description
  containing the raw author block and "Descarcă versiunea PDF…" because front matter has no
  `description` and Hugo falls back to `.Summary`. Add `description` to front matter of every
  page (also fixes `og:description`).
- **Hotlinked external image** in `content/ro/blog/1_etimologie.md` (Wikimedia, with `utm_*`
  tracking params): leaks visitor IPs to a third party and can break. Self-host it in
  `static/images/`.
- **YouTube iframe on the homepage** has a good `title` but no `loading="lazy"` — it pulls
  ~1 MB of third-party JS on first paint. Add `loading="lazy"`.
- **Search results are not announced**: `#book-search-results` has no `aria-live`/`role="status"`;
  the `Ctrl+K` / `/` shortcuts are undocumented.
- **PDF downloads are untagged**: `static/documents/ecuatia_dreptei.pdf` (1.3 MB) has no
  `/MarkInfo` and no `/Lang` — screen readers cannot navigate it. The HTML page is the accessible
  version (good), but if PDFs are meant to be read standalone, generate tagged PDFs
  (LaTeX `hyperref` + tagging) with document language set.
- **Raw HTML + inline styles in Markdown**: `ecuatia_dreptei.md` alone has 45 `<span style=…>`;
  the built page has 296 `style=` attributes. This forces `unsafe = true` in goldmark and makes
  content hard to maintain. Move repeated patterns to shortcodes/classes (`box`, `highlight`,
  `important` already exist).
- **Menu collapse anchors**: `menu-filetree.html` emits `<a role="button">` without `href` for
  content-less sections — not focusable (2.1.1) if it ever triggers; give it `tabindex="0"` +
  key handler or use a `<button>`.

## Nice to have

- Decorative emoji in UI controls (🌙/☀️, 🎲, 📌 injected via `::before` in `_custom.scss`):
  add `aria-hidden` / avoid in accessible names.
- `theme-color` dark value `#2e3440` doesn't match the real dark background `#3b4758`.
- `figcaption` uses `font-weight: 200` — thin at 1rem; consider 400 for readability.
- The three `<nav>` landmarks (menu, ToC, languages) have no `aria-label` to distinguish them.
- Add `aria-current="page"` to the active sidebar link (the `.active` class already exists).
- The language toggle falls back to linking `/en/` (homepage) when a page has no translation —
  fine, but a title attribute would clarify.
- Consider a print stylesheet check (`_print.scss` exists in the theme) for the educational
  pages — printing math materials is a common use case.
