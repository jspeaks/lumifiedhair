# Lumified Hair — Website Project

## What this is
A personal website for Lumi (Instagram: @lumifiedhair), a cosmetology student and hair stylist. The site is intentionally minimal and portrait-forward — more of a beauty brand calling card than a full site.

## Stack
- **Astro** (static site generator) — builds to `dist/`
- Single page: `src/pages/index.astro`
- All assets in `public/` (served as-is, no processing)

## Deployment
**Push to `main` → Cloudflare Pages auto-deploys.** No manual build step needed.

- Cloudflare Pages project: `lumifiedhair` → `lumifiedhair.pages.dev`
- Primary domain: `lumifiedhair.com` (DNS managed by Cloudflare)
- Secondary domain: `lumified.hair` (registered at Porkbun, forwarded 301 → lumifiedhair.com via Porkbun URL forwarding — no Cloudflare zone for this one)

## Design intent
- Dark background (`#0f0f0f`), warm cream/gold tones
- Font: **Cormorant Garamond** (Google Fonts) — luxury serif, elegant for a beauty brand
- Layout: "i am" (italic, muted gold) above a circular caricature portrait, "LUMI" in large caps below
- Portrait fills most of the viewport height; text rows anchor top and bottom
- Fully responsive: portrait/tablet = flex column; landscape short screens = grid side-by-side
- Color palette: text `#f0e6dc`, accent `#a08b78`, background `#0f0f0f`

## Key assets
- `public/lumi-caricature.png` — painterly caricature portrait (source of truth for the circular image and favicon)
- `public/favicon.png` — 64×64 crop of the caricature (regenerate with `sips -z 64 64 lumi-caricature.png --out favicon.png` if updated)

## DNS / infrastructure notes
- Cloudflare nameservers are authoritative for `lumifiedhair.com` (delegated from Porkbun)
- The `lumifiedhair.com` CNAME `@ → lumifiedhair.pages.dev` is managed by Cloudflare Pages custom domain flow — don't edit it manually
- `lumified.hair` is handled entirely at Porkbun; no Cloudflare zone exists for it
