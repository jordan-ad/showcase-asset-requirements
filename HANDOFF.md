# Showcase Asset Requirements — Handoff

A single-page, client-facing checklist of every asset we need to build a client's
Showcase. Static HTML, no build step, hosted on GitHub Pages.

- **Repo:** https://github.com/jordan-ad/showcase-asset-requirements
- **Live page:** https://jordan-ad.github.io/showcase-asset-requirements/

## Clone & edit

```bash
git clone https://github.com/jordan-ad/showcase-asset-requirements.git
cd showcase-asset-requirements
```

Everything is one file plus assets — no install, no build, no server. To preview,
just open `index.html` in a browser (double-click it).

## What's in here

| Path | What it is |
|---|---|
| `index.html` | The whole page — markup + styles + scripts all inline |
| `Showcase Logos/` | Header logo + favicon |
| `examples/` | The example thumbnail images shown beside each asset |
| `fonts/` | TT Commons (heading fallback) |
| `Showcase Stock List.csv` | The downloadable stock-list template clients fill in |

## How the page is built

- **Design system:** AD Group's **Blueprint** — brand blue `rgb(1,112,203)`,
  Aeonik Pro headings (Atkinson Hyperlegible / Google Fonts for body), 16px card
  radius, pill buttons, alpha borders over shadows. Tokens are defined as CSS
  variables in the `:root` block at the top of `index.html`.
- **Structure:** a sticky header, a quick-jump legend, then sections
  (Home, Building, Interactive map, Videos, Gallery, Brochure, Team, Shortlist,
  External links). Each requirement is an `.asset` card with a badge
  (Required / Recommended / Optional).
- **Adding a requirement:** copy an existing `.asset` card block, change the
  heading/description/formats, and drop it under the right section. If you add a
  new section, add a matching `<a>` to the `.legend` nav and an `id` on the
  `.section-label`.

## Download PDF button

The button runs `window.print()` and relies on the `@media print` stylesheet at the
bottom of `index.html` (hides the nav/button, expands cards, etc.). It always
reflects the current page. A static pre-rendered PDF was deliberately *not* used —
it would need re-exporting on every edit.

## Deploying changes

GitHub Pages auto-publishes on push to `main`:

```bash
git add -A
git commit -m "your change"
git push
```

Wait ~1 minute, then refresh the live URL. Pages config lives in
**Settings → Pages** (Deploy from branch → `main` / root).

## Notes

- This repo is a standalone copy. The page originally lived in the `requirements/`
  folder of the `showcase-drop` repo; it was split out here so GitHub Pages could
  serve it (the original is a private fork and can't run Pages).
- All asset paths are relative, so the page works both locally and under the
  Pages subpath with no changes.
