# Dhaya Catering — Tirupur

Marketing site for **Dhaya Catering**, run by Dhayalarajan M. in Tirupur, Tamil Nadu.
Chettinad home-style cooking: weekly/monthly meal packs plus event catering.

- **Live:** https://dhaya-catering.vercel.app
- **Stack:** Single static `public/index.html` (no build step). Hosted on Vercel.
- **Contact:** dhayalr@gmail.com · +91 99523 05413 / +91 98940 12003
- **Kitchen:** 248/183-1, Jai Nagar 4th Street, Kangayam Road, Tirupur – 641606
- **FSSAI** 22425589000202 · **GSTIN** 33AKWPD9539K2ZG · [@dhayacloudkitchen](https://instagram.com/dhayacloudkitchen)

## Layout

```
public/          web root — everything here is deployed as-is
  index.html     the whole site: markup, CSS and JS in one file
  assets/        logos, founder photo, menu poster, visiting card
assets-src/      original client-supplied images (NOT deployed)
vercel.json      pins outputDirectory to public/ + cache headers
```

`vercel.json` sets `outputDirectory: "public"`, so root-absolute paths like
`/assets/logo.png` resolve both locally and in production. Keep new images in
`public/assets/` and drop untouched originals in `assets-src/`.

The logo and certification PNGs were derived from JPEGs that had black
backgrounds baked in. They were made transparent with a border-connected flood
fill — so blacks *inside* a mark, like the BNI lettering, survive. See the
commit that added them if they ever need regenerating.

## Local preview

```bash
cd public && python3 -m http.server 4173
# open http://localhost:4173
```

## Deploy

```bash
vercel --prod
```
