# toyopita.com

Artist site for Toyopita — Sound Engineer / Producer / Remixer based in Osaka, Japan.

Live: <https://toyopita.com/>

## Stack
- Static HTML, no build step
- Hosted on Cloudflare Pages (project: `toyopita`)
- Custom domain `toyopita.com` + `www.toyopita.com`
- Design: BLUEPRINT (engineering-drawing aesthetic)

## Files
- `index.html` — single-page site (Hero / About / Works / Music / Contact)
- `favicon.svg` — TOY-001 themed inline SVG favicon
- `og-image.png` (1200×630) — Open Graph share image
- `og-image.svg` — source for the OG image
- `_headers` — Cloudflare Pages cache + security headers

## Development

```bash
# preview locally
cd ~/toyopita-site
python3 -m http.server 8811
# → http://localhost:8811/
```

## Deploy

```bash
cd ~/toyopita-site
npx wrangler pages deploy . --project-name=toyopita
```

Custom domains and DNS are managed by Cloudflare Pages.

## Regenerating OG image

If `og-image.svg` is edited, regenerate the PNG:

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless --no-sandbox --disable-gpu \
  --window-size=1200,630 \
  --screenshot=$PWD/og-image.png \
  "file://$PWD/og-image.svg"
```

## Mockup archive

Other design directions explored before BLUEPRINT was chosen are kept at
`~/toyopita-mockups/` (P1 SWISS / P2 DUB PRESS / P3 DAW / P4 TECHNO POSTER /
P6 KINETIC). Don't delete that directory — the alternates may be reused for
other projects.
