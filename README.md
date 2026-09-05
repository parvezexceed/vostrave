# VOSTRAVE — website

Single-page static site (`index.html`) — no build step. Deploys on Vercel straight from GitHub.

## How to update the live site

1. Unzip `vostrave-code.zip` and `vostrave-images.zip` into the **root of your GitHub repo** (same folder as the old `index.html`).
   - `index.html`, `README.md`, brand files (`monogram-gold.png`, `wordmark-gold.png`, `logo-gold.png`, `hero-portrait.jpg`, `og-image.jpg`, `fallback.png`, favicons) → repo root
   - the `images/` folder (all product angles + size charts) → repo root, so paths look like `images/waffle-t-shirt-black-1.jpg`
   - keep your existing `*.webp` / `*katua.jpg` files where they are (the 18 original products still use them)
2. Commit → Vercel redeploys in ~30 seconds.

Old files that are no longer used and can be deleted: `hero.jpg`, `velvet-bg.jpg`, `logo-primary.png`, `monogram.png`, `wordmark.png`.

## Editing products

Everything lives in the `PRODUCTS` array inside `index.html` (search for `const PRODUCTS`). New products are first, so they appear at the top of **All Products**.

```js
{ id: "unique-slug", name: "Product name", category: "Waffle T-Shirt",
  price: 450, sourcePrice: 350, stock: "in",            // "in" | "low" | "out"
  sizes: ["M","L","XL"],
  img: "images/main.jpg",                                // card photo
  gallery: ["images/angle-2.jpg", "images/angle-3.jpg"], // extra angles on the detail view
  sizeChart: "images/sizechart-tee-waffle.jpg",
  desc: "One-paragraph description.",
  bullets: ["Fabric", "Fit", "Care"] }
```

- Category chips are generated from `CATEGORIES` (only categories that have products are shown).
- Delivery charges, phone, WhatsApp and the order e-mail address are in `CONFIG`.
- Orders are still sent through **FormSubmit** to the e-mail in `CONFIG.email` — the mechanism is unchanged.

## Size charts

Branded size-chart images are in `images/sizechart-*.jpg`:

| file | used for |
|---|---|
| `sizechart-tee-drop.jpg` | acid-wash drop-shoulder tees |
| `sizechart-shirt-zaven.jpg` | dobby / ramie premium shirts |
| `sizechart-shirt-jackword.jpg` | Jackword embossed shirts |
| `sizechart-shirt-casual.jpg` | Exclusive Offer casual shirts |
| `sizechart-jeans-baggy.jpg` | semi baggy jeans |
| `sizechart-pant-remi.jpg` | Remi cotton pants |
| `sizechart-tee-waffle.jpg` / `-tee-mock.jpg` / `-polo-cuban-waffle.jpg` | DeshWear tees & polos |
| `sizechart-polo-ribbed.jpg` / `-pant-ribbed.jpg` | zipper polos, Cuban shirts, Cuban pants |
| `sizechart-polo-gentle.jpg` / `-jacket-700.jpg` | classic polos, North Face 700 |
| `sizechart-shirt-vostrave.jpg` / `-polo-vostrave.jpg` / `-katua-vostrave.jpg` | original 18 products |
