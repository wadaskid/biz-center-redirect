# biz-center-redirect

A lightweight, zero-cost static redirect site for forwarding `biz-center.io` (and all sub-paths) to `https://businessbosses.co.uk`.

Designed specifically for **DigitalOcean App Platform Free Static Site Tier** (free for up to 3 static sites).

## How it works
1. **HTTP / Ingress Redirect (`_redirects`)**: Provides a server-level `301!` permanent redirect pattern: `/* -> https://businessbosses.co.uk/:splat`.
2. **Instant Browser Navigation (`index.html` & `404.html`)**: Instant zero-delay JavaScript `window.location.replace()` preserving request path, query parameters, and hash fragments.
3. **Instant Meta Refresh Fallback**: `<meta http-equiv="refresh" content="0; url=https://businessbosses.co.uk/">`.
4. **Accessible Fallback UI**: Clean animated card with a direct link for browsers with script execution disabled.

---

## Deploying to DigitalOcean App Platform (100% Free)

1. Go to the [DigitalOcean App Platform](https://cloud.digitalocean.com/apps).
2. Click **Create App** and choose **GitHub**.
3. Select this repository: `wadaskid/biz-center-redirect`, branch `main`.
4. DigitalOcean will auto-detect it as a **Static Site** ($0/month).
   - **Build Command**: Leave empty.
   - **Output Directory**: Leave empty (root `/`).
   - **Catchall Document**: `404.html` (or `index.html`).
5. Click **Next** until the app is created.
6. Once deployed:
   - Go to **Settings** -> **Domains**.
   - Add `biz-center.io` and `www.biz-center.io`.
   - Follow DigitalOcean's instructions to point your DNS (or DigitalOcean will configure it automatically since your DNS is managed on DigitalOcean).
   - DigitalOcean will automatically issue free SSL certificates for HTTPS.
