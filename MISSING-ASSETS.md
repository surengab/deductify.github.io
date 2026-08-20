# Missing assets

These files are referenced in the site HTML but do not yet exist in the repository.
Add them before publishing. Do not commit placeholder or blank files.

## Required before launch

| File path | Required dimensions | Notes |
|-----------|--------------------|----|
| `/favicon.png` | 32×32 or 180×180 | Linked from every page `<head>`. Also add `/favicon.ico` (32×32) for legacy browser fallback. |
| `/og-deductify.webp` | 1200×630 | Social share image. Appears in every page's `og:image` and `twitter:image` tags. |
| `/assets/images/deductify-logo.webp` | 512×512 minimum | Appears in every page's JSON-LD `Organization.logo` field. |
| `/assets/images/productify-icon.webp` | 72×72 (homepage card) · 110×110 (product page) | Primary format. Export from App Store Connect at 1024×1024 and resize. |
| `/assets/images/productify-icon.png` | same | PNG fallback inside `<picture>` element. |
| `/assets/images/plantive-icon.webp` | 72×72 (homepage card) · 110×110 (product page) | Primary format. |
| `/assets/images/plantive-icon.png` | same | PNG fallback. |
| `/assets/images/productify-screenshot-1.webp` | 9:19.5 portrait | iPhone screenshot, referenced in `/products/productify/`. |
| `/assets/images/productify-screenshot-1.png` | same | PNG fallback. |
| `/assets/images/productify-screenshot-2.webp` | 9:19.5 portrait | |
| `/assets/images/productify-screenshot-2.png` | same | |
| `/assets/images/productify-screenshot-3.webp` | 9:19.5 portrait | |
| `/assets/images/productify-screenshot-3.png` | same | |
| `/assets/images/plantive-screenshot-1.webp` | 9:19.5 portrait | iPhone screenshot, referenced in `/products/plantive/`. |
| `/assets/images/plantive-screenshot-1.png` | same | |
| `/assets/images/plantive-screenshot-2.webp` | 9:19.5 portrait | |
| `/assets/images/plantive-screenshot-2.png` | same | |
| `/assets/images/plantive-screenshot-3.webp` | 9:19.5 portrait | |
| `/assets/images/plantive-screenshot-3.png` | same | |

## Conversion

To convert PNG or JPG to WebP (requires libwebp):
```
cwebp -q 85 source.png -o output.webp
```

Or use macOS Preview → Export → WebP, or [Squoosh](https://squoosh.app/) in the browser.
