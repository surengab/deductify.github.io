# Deductify — deductify.org

Independent iOS studio website. Static HTML/CSS hosted on GitHub Pages with custom domain `deductify.org`.

---

## TODO: Items to resolve before publishing

### High priority — required for launch

| # | File(s) | What to do |
|---|---------|------------|
| 1 | Every page — JSON-LD `<script>` | Replace `"TODO: Add founder name"` with the real founder name |
| 2 | Every page — JSON-LD `<script>` | Replace `"TODO: Add founding year"` with the 4-digit founding year (e.g. `"2018"`) |
| 3 | `about/index.html` | Fill in the `<!-- TODO: Add founder bio -->` comments with 2–3 sentences of real bio text |
| 4 | `about/index.html` | Add the studio location (city/country) in the `<dd>` under "Location" |
| 5 | Contact form in `contact/index.html` | Set the `action=""` attribute on `<form>` to a real endpoint. Options: [Formspree](https://formspree.io/), [Netlify Forms](https://www.netlify.com/products/forms/), or a custom backend. Mark the `TODO` comment done once wired. |
| 6 | `products/plantive/index.html` | Confirm the Plantive marketing site domain. Currently set to `https://plantiveapp.com/`. Update all three occurrences if different. |

### Assets — all images are placeholders until added

Place final images at these exact paths (WebP primary, PNG fallback):

| Asset | Path | Dimensions | Notes |
|-------|------|------------|-------|
| OG / social share image | `/og-deductify.webp` | 1200×630px | Used on every page for social sharing |
| Favicon (PNG) | `/favicon.png` | 32×32px or 180×180px | Browser tab icon |
| Favicon (ICO) | `/favicon.ico` | 32×32px | Legacy browser fallback |
| Deductify logo | `/assets/images/deductify-logo.webp` | Flexible | Used in JSON-LD `logo` field |
| Founder photo (hero) | `/assets/images/founder-photo.webp` | 88×88px | Circular crop, replaces the "D" placeholder in `index.html` hero |
| Founder photo (about) | `/assets/images/founder-photo.webp` | 140×140px | Same file, circular crop, replaces placeholder in `about/index.html` |
| Productify app icon | `/assets/images/productify-icon.webp` + `.png` | 72×72px (cards), 110×110px (product page) | Export from App Store Connect |
| Plantive app icon | `/assets/images/plantive-icon.webp` + `.png` | 72×72px (cards), 110×110px (product page) | Export from App Store Connect |
| Productify screenshot 1 | `/assets/images/productify-screenshot-1.webp` + `.png` | 9:19.5 ratio | iPhone screenshot, portrait |
| Productify screenshot 2 | `/assets/images/productify-screenshot-2.webp` + `.png` | 9:19.5 ratio | iPhone screenshot, portrait |
| Productify screenshot 3 | `/assets/images/productify-screenshot-3.webp` + `.png` | 9:19.5 ratio | iPhone screenshot, portrait |
| Plantive screenshot 1 | `/assets/images/plantive-screenshot-1.webp` + `.png` | 9:19.5 ratio | iPhone screenshot, portrait |
| Plantive screenshot 2 | `/assets/images/plantive-screenshot-2.webp` + `.png` | 9:19.5 ratio | iPhone screenshot, portrait |
| Plantive screenshot 3 | `/assets/images/plantive-screenshot-3.webp` + `.png` | 9:19.5 ratio | iPhone screenshot, portrait |

To convert existing JPG/PNG to WebP: `cwebp -q 85 input.png -o output.webp`

Once founder photo is ready, replace the CSS placeholder `<div class="hero-mark">` in `index.html` with:
```html
<div class="hero-mark">
  <picture>
    <source srcset="/assets/images/founder-photo.webp" type="image/webp">
    <img src="/assets/images/founder-photo.png" alt="[Founder name]" width="88" height="88">
  </picture>
</div>
```
And replace the `<div class="founder-photo-placeholder">` in `about/index.html` with a `<picture>` element similarly.

### Post-launch checklist

- [ ] Submit `https://deductify.org/sitemap.xml` to [Google Search Console](https://search.google.com/search-console)
- [ ] Submit sitemap to [Bing Webmaster Tools](https://www.bing.com/webmasters)
- [ ] Monitor Search Console for crawl errors for 2 weeks after launch
- [ ] Update **App Store Connect** for both apps:
  - Developer Website → `https://deductify.org/`
  - Privacy Policy URL → `https://deductify.org/privacy.html`
- [ ] Verify the CNAME file (`deductify.org`) is committed and GitHub Pages custom domain is configured in repo Settings → Pages

---

## Redirect note (GitHub Pages)

GitHub Pages does not support server-side 301 redirects. The old blog posts at:

- `/blog/water-drinking` → `https://productifyapp.org/blog/what-habits-to-track/`
- `/blog/walking.html` → `https://productifyapp.org/blog/what-habits-to-track/`
- `/blog/morning-routine` → `https://productifyapp.org/solutions/morning-routine/`

…are handled by client-side meta-refresh pages already in place in `/blog/`. They use `<meta http-equiv="refresh">` plus a JavaScript `location.replace()` fallback.

If you migrate to a host that supports Apache or Nginx, use the rules in `.htaccess` (Apache) or adapt them for your Nginx config.

---

## File structure

```
/
├── index.html                    Homepage
├── about/index.html              Founder + studio story
├── products/
│   ├── productify/index.html     Productify portfolio entry
│   └── plantive/index.html       Plantive portfolio entry
├── contact/index.html            Contact form
├── privacy.html                  Privacy policy
├── terms.html                    Terms of use
├── styles.css                    Single stylesheet (all pages)
├── robots.txt
├── sitemap.xml
├── CNAME                         GitHub Pages custom domain
├── .htaccess                     Apache redirect reference (see note above)
├── blog/
│   ├── water-drinking.html       Redirect → productifyapp.org
│   ├── walking.html              Redirect → productifyapp.org
│   └── morning-routine.html      Redirect → productifyapp.org
└── assets/images/                Drop all image assets here
```
