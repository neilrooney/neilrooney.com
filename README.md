# neilrooney.com

## Description

This repository contains the source for Neil Rooney's personal website at [neilrooney.com](https://neilrooney.com).

The site presents a concise professional profile, profile image, and links to external profiles. It is intentionally small, has no build step, and can be previewed directly from the repository root.

## Setup Instructions

No dependency installation is required.

To preview the site locally, run a local static file server from the repository root:

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000` in a browser.

## Deployment

The site is deployed through Cloudflare Pages. This repository does not define a GitHub Actions release workflow, package publishing workflow, or tagged release process.

Before releasing production changes, confirm the active production branch and deployment trigger in the Cloudflare Pages project settings.

## Troubleshooting / Known Issues

If fonts, images, or absolute paths do not load locally, make sure the site is being served from the repository root rather than opened directly from the filesystem.

Production security headers and cache rules are applied by Cloudflare Pages during deployment, so local previews will not exactly match production response headers.

## Acknowledgements

The original version of this site was based on work by [Leah Culver](https://github.com/leah/leah.github.io).
