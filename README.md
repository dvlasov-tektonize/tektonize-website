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
- `og-image.png` — social share image (1200×630)
- `robots.txt` / `sitemap.xml` — SEO crawl directives
- `CNAME` — custom domain (`tektonize.com`)
- `.github/workflows/pages.yml` — auto-publish to GitHub Pages on every push to `main`

## SEO (already wired in)
Each page carries a static `<head>` (visible to non-JS crawlers and social scrapers) with:
- unique `<title>` + meta description
- canonical URL
- Open Graph + Twitter Card tags (share preview uses `og-image.png`)
- JSON-LD structured data (Organization on home, FAQPage on faq)
- `robots.txt` + `sitemap.xml` point crawlers at all three pages

## One-time setup
1. Upload all files to the repo root (drag-and-drop in GitHub, or `git add . && git commit && git push`).
   Replace the old files — remove the previous `tektonize-cci.html` / `tektonize-faq.html`.
2. Repo → **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. Custom domain: the `CNAME` file points the site at `tektonize.com`. In DNS, point
   `tektonize.com` (and `www`) to GitHub Pages, then confirm under Settings → Pages.
4. Done. Every future push to `main` republishes automatically.

## After deploy — submit to search engines
- Google Search Console → add `tektonize.com` → submit `https://tektonize.com/sitemap.xml`.
- Validate share previews: Facebook Sharing Debugger, LinkedIn Post Inspector, X Card Validator.

## Notes
- Keep all files in the same folder — the pages fetch `support.js`, the shared
  header/footer, and the assets by relative path.
- To update the site, edit in the design project and re-export this folder.
