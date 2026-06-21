# Tektonize Website — deploy package

Static site. Upload the **contents of this folder** to the root of
`dvlasov-tektonize/tektonize-website` (branch `main`).

## Files
- `index.html` — landing (home)
- `faq.html` — FAQ
- `cci.html` — Clarity & Control Index diagnostic
- `Site Header.dc.html` / `Site Footer.dc.html` — shared header/footer (loaded by the pages at runtime)
- `support.js` — runtime that renders the pages (required, keep alongside the HTML)
- `favicon.ico` / `favicon-32.png` / `apple-touch-icon.png` — site icons
- `CNAME` — custom domain (`tektonize.com`)
- `.github/workflows/pages.yml` — auto-publish to GitHub Pages on every push to `main`

## One-time setup
1. Upload all files to the repo root (drag-and-drop in GitHub, or `git add . && git commit && git push`).
2. Repo → **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. Custom domain: the `CNAME` file points the site at `tektonize.com`. In your DNS,
   point `tektonize.com` (and `www`) to GitHub Pages, then confirm the domain under
   Settings → Pages.
4. Done. Every future push to `main` republishes automatically.

## Notes
- Keep all files in the same folder — the pages fetch `support.js`, the shared
  header/footer, and the icons by relative path.
- To update the site, edit in the design project and re-export this folder.
