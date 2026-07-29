# Carlos Simón Amador Izaguirre — portfolio

Static bilingual website for `simonamador.com`. It uses plain HTML and one shared CSS file: no framework, package dependencies, build step or runtime service.

## Architecture and source of truth

- `index.html` — English profile homepage.
- `es/index.html` — Spanish profile homepage.
- `consulting/index.html` — English consulting landing.
- `es/consultoria/index.html` — Spanish consulting landing.
- `styles.css` — shared visual system and responsive behavior.
- `img/`, `cv/` — public static assets.
- `CNAME`, `robots.txt`, `sitemap.xml`, `site.webmanifest` — GitHub Pages and discovery metadata.

This repository (`simonamador/portfolio`, branch `main`) is the Git source of truth. The local configuration does not prove which Pages publishing source is selected in GitHub settings. The previous README incorrectly named `simonamador/simonamador.github.io`; confirm the Pages setting before the next production release.

## Deployment

There is no deploy script or GitHub Actions workflow in this repository. Expected flow:

1. Review and commit changes to `main`.
2. Push to `origin`.
3. GitHub Pages publishes the configured source for `simonamador.com`; `CNAME` preserves the custom domain.

Do not change Pages settings or `CNAME` without first confirming the repository settings.

For a local preview, run `node serve-local.mjs` from the repository root, then open `http://localhost:8000/`. Press `Ctrl+C` to stop the server. Opening HTML directly with `file://` does not accurately test root-relative paths.

## Validation checklist

- Check `/`, `/es/`, `/consulting/` and `/es/consultoria/` at desktop and mobile widths.
- Verify internal links, anchors, images, CVs, favicons and the web manifest.
- Parse all HTML and `sitemap.xml`; confirm one `h1` per page and reciprocal `hreflang`.
- Test keyboard navigation, skip links, mobile menu state, focus visibility and reduced motion.
- Run Lighthouse for accessibility, SEO and performance.
- Validate structured data with Schema.org or Google Rich Results tools.
- Confirm `robots.txt` and every sitemap URL after deployment.

## Pending placeholders and approvals

- `cv/bibtex-placeholder.txt` is still a placeholder used by publication links.
- Confirm public approval for any employer-linked project descriptions, event metrics, and event naming before publishing. Relevant locations contain `TODO: confirm public approval` comments.
- Confirm the GitHub Pages publishing source in repository settings.
- The consultation CTA uses email until a booking link is available.
