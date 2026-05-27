# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Running the project

This is a **static HTML site** with no build step. To preview locally:

```powershell
# Option 1 — Python (recommended, Python 3.13 is installed at C:\Python313\)
C:\Python313\python.exe -m http.server 8080
# Then open http://localhost:8080/01-home.html

# Option 2 — Node (npx)
npx --yes serve . -p 3000

# Option 3 — VS Code Live Server extension (port 5500)
```

Pages are served directly from the project root. There is no build, lint, or test pipeline.

## Architecture

**Delivery target: Webflow.** The CSS in `shared.css` is designed to be pasted into Webflow → Settings → Custom Code → Head. Each HTML file also embeds page-specific `<style>` blocks inline so every page is self-contained when exported.

### Pages

| File | Route intent | Size |
|---|---|---|
| `01-home.html` | Homepage | 78 KB |
| `02-scan-go.html` | Scan&Go product page | 89 KB |
| `03-queue-busting.html` | Queue Busting product page | 55 KB |
| `04-demo.html` | Demo booking form | 18 KB |
| `correct.html` | Alternate/corrected demo page | 20 KB |

### CSS architecture

`shared.css` (44 KB) holds all reusable components and CSS custom properties. Page-specific styles live in `<style>` blocks inside each HTML file.

**CSS custom properties (defined in `:root`):**
- `--bg: #F2F5EF` — page background
- `--dark: #09110D` — primary text
- `--mid: #68736D` — secondary text
- `--green-ok: #0B9A5B` — validation green
- `--y1: #E1FF26` / `--y2: #FFCF26` / `--yd: #D9CA0C` — yellow palette
- `--w: 1160px` — max container width

**Class naming by scope:**
- `pk-*` — global/shared components (header, buttons, cards, typography)
- `home-*` — homepage-only styles
- `sg-*` — Scan&Go page
- `qb-*` — Queue Busting page
- `demo-*` — demo form page

**Key shared components:** `.pk-btn-yellow` (3D yellow CTA), `.pk-btn-ghost` (glassmorphism), `.pk-tag` (animated pill badge), `.pk-header` (sticky blur header), `.pk-card` / `.pk-feat-card`, `.pk-stats` (4-col grid), `.pk-section-dark`, `.pk-cta-box`.

### Responsive breakpoints

- `≤ 1024px` — tablet adjustments
- `≤ 991px` — burger nav activated
- `≤ 767px` — mobile: stacked layouts, reduced font sizes via `clamp()`

### Assets

`/assets/` contains SVGs and PNGs (logos, icons, product images). Some images are served from the Webflow CDN (`cdn.prod.website-files.com`) and referenced by absolute URL in the HTML.

### JavaScript

Vanilla only. The only JS present is the mobile menu toggle (`toggleMenu()`) defined inline in each page's `<script>` block.
