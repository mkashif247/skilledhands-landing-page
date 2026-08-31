# Skilled Hands — Landing Page

Marketing landing page for **Skilled Hands**, a mobile app for finding trusted local tradespeople (plumbers, electricians, painters, and more).

## Stack

Static site — plain HTML, CSS, and JavaScript, no build step or framework. Deployed to [Cloudflare Workers](https://developers.cloudflare.com/workers/) via [Wrangler](https://developers.cloudflare.com/workers/wrangler/), served as static assets.

## Project structure

```
index.html       Page markup and content (new landing page design)
styles.css       All styling
translations.js  5-language i18n support (EN, ES, IT, DE, FR)
assets/          Images (logos, backgrounds, icons)
fonts/           Self-hosted Ubuntu font files
wrangler.jsonc   Cloudflare Workers deployment config
```

## Local development

This is a static site — no build tooling is required. Serve the directory with any static file server and open it in a browser, e.g.:

```sh
npx serve .
```

or simply open `index.html` directly in a browser.

## Deployment

Deployed to Cloudflare Workers using Wrangler:

```sh
npx wrangler deploy
```

`wrangler.jsonc` configures the deployment:
- `assets.directory` — serves the project root as static assets
- `workers_dev` — disabled (no `*.workers.dev` URL; the site is served from its configured route/domain only)

## Notes

- No `workers.dev` preview URL is exposed — see `wrangler.jsonc`.
- `.assetsignore` excludes non-deployable files (`.git`, `.wrangler`, config, local artifacts) from the asset upload.
