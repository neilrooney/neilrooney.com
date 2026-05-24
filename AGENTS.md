# AGENTS.md

## Repo Shape
- This is a hand-written static site for `https://neilrooney.com`; there is no package manager, build step, lint, formatter, or automated test config in the repo.
- Main entrypoints: `index.html` for the home page, `404.html` for the Cloudflare Pages custom 404, `css/main.css` for shared styles, `_headers` for Cloudflare Pages response headers/cache/preload rules, and `robots.txt`/`sitemap.xml` for indexing.
- Asset paths assume the site is served from the repository root. Do not validate by opening `index.html` with `file://`; use a static server.

## Commands
- Preview locally from the repo root: `python3 -m http.server 8000`, then open `http://localhost:8000/`.
- There is no install, test, build, lint, or typecheck command unless you add that tooling as part of the change.
- For focused manual checks, visit `/`, `/404.html`, `/robots.txt`, and `/sitemap.xml` in the local server. Local previews do not apply Cloudflare Pages `_headers`.

## Change Notes
- Deployment is via Cloudflare Pages, but no GitHub Actions or release workflow is defined here; confirm the production branch and deploy trigger in Cloudflare Pages before release-sensitive changes.
- `_headers` sets a restrictive CSP (`default-src 'none'`) and immutable caching for `/css/*`, `/images/*`, and `/fonts/*`. Update it when adding external scripts/styles/images/fonts or changing cache-sensitive asset paths.
- When changing identity, profile image, title, description, or URL data, keep visible copy, canonical URL, Open Graph/Twitter tags, JSON-LD `Person`, `robots.txt`, and `sitemap.xml` aligned.
- Keep public-facing copy in British English to match existing content (`Specialising`, `Acknowledgements`).
