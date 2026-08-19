# ACX Consulting — one-pager

Single static file, no build step. Everything (HTML, CSS, JS) lives in `index.html`.

## Host it on GitHub Pages (free)

1. Create a new **public** repo on GitHub, e.g. `acx-consulting`.
2. Upload `index.html` to the root of that repo (drag and drop works, or `git push`).
3. Go to **Settings → Pages**.
4. Under "Build and deployment", choose **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
5. Wait ~1 minute. Your site is live at `https://<your-username>.github.io/acx-consulting/`.

## Connect acxconsulting.eu / .nl (optional, recommended)

Pick **one** domain as primary (e.g. `.eu`) — you can forward the other to it later at your registrar.

1. In the repo root, add a file named exactly `CNAME` (no extension) containing one line:
   ```
   acxconsulting.eu
   ```
2. At your domain registrar, add these DNS records for `acxconsulting.eu`:
   - Four **A** records for the root domain, pointing to:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One **CNAME** record for `www` pointing to `<your-username>.github.io`
3. Back in **Settings → Pages**, enter `acxconsulting.eu` under "Custom domain" and save. Tick **Enforce HTTPS** once it's available (can take up to 24h for the certificate).
4. For `acxconsulting.nl`: simplest option is a domain forward/redirect to `acxconsulting.eu` set up at your registrar, rather than hosting the same site twice.

## Editing later

Everything is in one file. Open `index.html` in any text editor:
- Copy lives in the `<body>`, grouped by section (`<!-- HERO -->`, `<!-- SERVICES -->`, etc.)
- Colors and fonts are CSS variables at the top of the `<style>` block, under `:root`
- No dependencies to install, no `npm`, nothing to build — save the file, push to GitHub, it's live.
