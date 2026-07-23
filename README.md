# Gear Train — Kenya landing page

A simple static landing page for Gear Train Kenya, ready to deploy on Cloudflare.

> AI-powered automation, transaction monitoring and cloud computing.

## Structure

```
public/
  index.html        # the landing page
  styles.css        # styles
  images/           # logos (orange for light bg, white for dark bg)
wrangler.jsonc      # Cloudflare Workers static-assets config
package.json
```

## Local preview

Any static server works. The simplest:

```bash
npx wrangler dev        # serves at http://localhost:8787
# or, without wrangler:
python3 -m http.server 8000 --directory public
```

## Deploy to Cloudflare

This site deploys via **Cloudflare Workers static assets** (no build step).

```bash
npm install
npx wrangler login      # one-time browser auth
npm run deploy          # publishes to <name>.workers.dev
```

To use a custom domain (e.g. `geartrain.co.ke`), add the domain to your
Cloudflare account, then in the dashboard: **Workers & Pages → geartrain-ke-site
→ Settings → Domains & Routes → Add custom domain**.

### Alternative: Cloudflare Pages (Git-connected)

Push this repo to GitHub, then in the Cloudflare dashboard:
**Workers & Pages → Create → Pages → Connect to Git**, and set:

- **Build command:** _(leave empty)_
- **Build output directory:** `public`

## Things to update before going live

- **Contact links** in `index.html` — currently `mailto:hello@geartrain.co.ke`.
- **Kintro website URL** — currently `https://kintro.money`.
- **AI offer** links — currently point to the contact section.
