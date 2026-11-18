# woodlani.com

Personal consulting site for Ed Tisdale — independent RevOps consulting across
Salesforce, HubSpot, and AI systems. Single-page static site: hand-written HTML/CSS/JS, no
framework, no build step.

**Live:** [woodlani.com](https://woodlani.com)

## Structure

```
index.html      the whole site (content + JSON-LD schema)
assets/         styles.css, main.js, images
robots.txt      + sitemap.xml for SEO
wrangler.jsonc  Cloudflare Workers deploy config (static assets)
```

## Deploy

Hosted on a Cloudflare Worker (`woodlani`) serving static assets, bound to
`woodlani.com` and `www.woodlani.com`.

- **Primary:** `git push` — the repo is Git-connected; Cloudflare auto-builds
  every push to `main`.
- **Manual:** `wrangler deploy` from the repo root (direct upload, no commit
  needed). Rollbacks: `wrangler versions list` / `wrangler rollback`.

## Preview locally

```bash
python3 -m http.server 8765
# then open http://localhost:8765 — /assets paths break under file://
```
