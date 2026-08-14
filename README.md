# Silvertree Capital — Website

1:1 static clone of the Webflow site for [silvertree-capital.de](https://www.silvertree-capital.de),
fully self-hosted: every asset (CSS, JS, images, fonts) is served from this repo — no Webflow,
no Google Fonts, no external CDNs at runtime.

## Stack
- Code: this GitHub repository
- Hosting: Cloudflare Pages (free plan — static requests are free and unlimited, no suspension mechanism)
- Deploys: automatic on every push to `main`
- Running cost: $0/month + domain

## Cloudflare Pages settings
- Build command: (none)
- Build output directory: `public`
- Custom domains: www.silvertree-capital.de (canonical) + silvertree-capital.de (redirects to www)

## Notes
- `public/` mirrors the live Webflow site as published 2026-07-25 (pages: home, our-focus, about,
  contact, impressum, datenschutz), with all URLs rewritten to local `/assets/...` paths.
- Fonts (DM Sans, Manrope) are self-hosted in `assets/fonts/` — the Google Fonts runtime request
  was replaced with a local stylesheet (also better for GDPR).
- Team photos are currently the 800px variants; replace files in `assets/images/` when
  high-resolution versions are provided.
- The contact form still posts to Webflow's form API and will stop working when the Webflow
  subscription is cancelled — swap it for an email link or a form service before/at cutover.
- The Datenschutz page's "Hosting" section still describes Webflow; it must be updated to
  Cloudflare (and reviewed) at cutover.
