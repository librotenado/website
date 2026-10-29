# librotenado – website

One static page for **librotenado**, the open accounting protocol: no build step, no framework, no external
resources, no cookies, no tracking. Light and dark mode follow the system or the visitor's choice (the switch in the
header, stored in the browser only). A [falkOSS](https://falkoss.org) project.

| Path | What |
|---|---|
| `index.html`, `style.css`, `404.html` | the page (English) |
| `librotenado-whitepaper.pdf` | the whitepaper, copied from the whitepaper repository |
| `favicon.*`, `apple-touch-icon.png`, `icon-*.png`, `site.webmanifest`, `social.png` | head icons – **generated** by `brand/generate.py` in `librotenado/librotenado` (`brand/web/`), copied here |
| `assets/` | adaptive mark and lockup (from `brand/svg/`), Atkinson Hyperlegible Next and Mono as WOFF2 (`assets/fonts/`, SIL OFL 1.1) |

The header lockup and the marks are inlined into the HTML from `brand/svg/librotenado-*-adaptive.svg`, so they follow
the colour switch (`--logo-ink`, `--logo-accent`, `--logo-sub` in `style.css`). Copy them again when the brand kit
changes.

Imprint and privacy policy are falkoss.org's – same operator, one place to keep them current.

Preview locally:

```sh
python3 -m http.server 8030
```

## Publishing

GitHub Pages via `.github/workflows/pages.yml` on every push to `main`. One-time setup: Repo → Settings → Pages →
Source: **GitHub Actions**. Pages needs a public repository (or a paid plan).

The domain is **librotenado.org**: Repo → Settings → Pages → Custom domain: `librotenado.org`; then **Enforce HTTPS**.
DNS: `A` and `AAAA @` to the GitHub Pages addresses, `CNAME www` → `librotenado.github.io`; the Pages domain
verification TXT is in place. `librotenado.com` and `.eu` redirect with **301** to `https://librotenado.org`;
`librotenado.dev` is kept for the documentation. `404.html` uses root paths, which resolve under the custom domain.

## Licence

Code (HTML, CSS): [AGPL-3.0-or-later](LICENSE). Text, and the whitepaper: CC BY 4.0. Fonts: SIL Open Font License
1.1. The brand's artwork (icons, lockup, mark): CC BY-ND 4.0, copied from
[librotenado/brand](https://github.com/librotenado/brand). Name and brand of librotenado belong to falkOSS – see the
brand kit's README. Every file's licence is in `REUSE.toml` or its SPDX header ([REUSE](https://reuse.software),
checked in CI).
