# Deductify — Pre-launch change log

## Files modified

| File | Change |
|------|--------|
| `index.html` | Replaced Organization JSON-LD: removed `founder` and `foundingDate`, added `description`, added TODO comment for Apple Developer `sameAs` URL. Added WebSite JSON-LD block. Added four SEO meta tags (`og:locale`, `og:image:alt`, `twitter:site`, `twitter:image:alt`). Removed TODO founder-photo comment from hero (D mark is intentional). Removed TODO comments from app icon `<picture>` elements. Changed Plantive card link from `https://plantiveapp.com/` to internal `/products/plantive/`. |
| `about/index.html` | Fixed JSON-LD (same pattern as above). Updated `<title>` to `About — Deductify`. Updated `<meta name="description">`, `og:title`, `og:description`, `twitter:title`, `twitter:description` to studio-philosophy copy. Replaced entire `<main>` — removed all founder content, photo placeholders, and personal narrative. New main has four `content-block` sections: What we make, What we believe, Our apps, Get in touch. |
| `privacy.html` | Fixed JSON-LD. Expanded privacy policy body: added Productify-specific data description (habit logs stored locally / iCloud), Plantive-specific data description (image processed transiently for identification, not stored). Expanded Third-Party Services section. Updated Your Rights section to list both contact emails — `contact@deductify.org` for general requests, `gabrielyansuren@gmail.com` for formal GDPR/CCPA data subject requests. Updated Contact section similarly. |
| `terms.html` | Fixed JSON-LD (removed `founder` and `foundingDate`, added `description`). Content unchanged — was already correct. |
| `contact/index.html` | Fixed JSON-LD only. Content unchanged. |
| `products/productify/index.html` | Fixed JSON-LD (Organization block only; MobileApplication block unchanged). |
| `products/plantive/index.html` | Fixed JSON-LD (Organization block only; MobileApplication block unchanged). |
| `styles.css` | Added CSS for new about-page classes: `.page-lede`, `.content-block`, `.belief-list`, `.apps-mini-grid`. |

---

## Missing assets — add before publishing

These files are referenced in the HTML but do not exist yet. Add them manually:

| Path | Dimensions | Notes |
|------|------------|-------|
| `/favicon.png` | 32×32 or 180×180 | Browser tab icon; also add `/favicon.ico` for legacy browsers |
| `/og-deductify.webp` | 1200×630 | Social share card image, referenced in every page's OG/Twitter tags |
| `/assets/images/deductify-logo.webp` | 512×512 min | Used in JSON-LD `logo` field on every page |
| `/assets/images/productify-icon.webp` | 72×72 (card), 110×110 (product page) | Export from App Store Connect; WebP primary |
| `/assets/images/productify-icon.png` | same | PNG fallback for `<picture>` element |
| `/assets/images/plantive-icon.webp` | 72×72 (card), 110×110 (product page) | Export from App Store Connect; WebP primary |
| `/assets/images/plantive-icon.png` | same | PNG fallback |
| `/assets/images/productify-screenshot-1..3.webp` + `.png` | 9:19.5 ratio | iPhone screenshots (portrait), referenced in `/products/productify/` |
| `/assets/images/plantive-screenshot-1..3.webp` + `.png` | 9:19.5 ratio | iPhone screenshots (portrait), referenced in `/products/plantive/` |

To convert existing PNG/JPG to WebP: `cwebp -q 85 input.png -o output.webp`

---

## TODOs remaining for you to handle

1. **Apple Developer URL in `sameAs`** — Every page's Organization JSON-LD has a comment marking where to add your Apple Developer profile URL once located. Search for `// TODO: Add Apple Developer URL` to find all occurrences (7 files). Add the URL as a third item in the `sameAs` array, then remove the comment line.

2. **Contact form backend** — `contact/index.html` form `action=""` is a placeholder. Wire it up to a handler such as [Formspree](https://formspree.io/), [Netlify Forms](https://www.netlify.com/products/forms/), or a custom endpoint before launch.

3. **Push to GitHub** — The last commit was amended; a force-push is required: `git push origin master --force-with-lease`.

4. **Post-launch**:
   - Submit `https://deductify.org/sitemap.xml` to Google Search Console and Bing Webmaster Tools.
   - Update both App Store Connect entries: Developer Website → `https://deductify.org/` and Privacy Policy URL → `https://deductify.org/privacy.html`.
   - Monitor Search Console for crawl errors for 2 weeks after go-live.
