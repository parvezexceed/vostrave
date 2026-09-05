# VOSTRAVE — website

Single-page static site (`index.html`) — no build step. Deploys on Vercel straight from GitHub.

## How to update the live site

**Everything is flat** — `index.html`, the brand files and all product photos / size charts sit side by side in the **root of the GitHub repo** (no images sub-folder). Product paths therefore look like `waffle-t-shirt-black-1.jpg`.

1. Upload / replace `index.html` (and any new or changed `.jpg` photos) in the repo root — *Add file → Upload files* on GitHub.
2. Commit → Vercel redeploys in ~30 seconds.

If you add a photo, make sure the file name in `PRODUCTS` matches the uploaded file exactly (case-sensitive).

Old files that are no longer used and can be deleted: `hero.jpg`, `velvet-bg.jpg`, `logo-primary.png`, `monogram.png`, `wordmark.png`.

## Categories

The category strip above the grid is built automatically from the `CATEGORIES` list (search `const CATEGORIES`) — each box shows the first 3 product photos of that category and the item count. To add a category, add its name to `CATEGORIES` and give products that `category`; empty categories are hidden automatically. The list order = box order.

## Editing products

Everything lives in the `PRODUCTS` array inside `index.html` (search for `const PRODUCTS`). New products are first, so they appear at the top of **All Products**.

```js
{ id: "unique-slug", name: "Product name", category: "Waffle T-Shirt",
  price: 450, sourcePrice: 350, stock: "in",            // "in" | "low" | "out"
  sizes: ["M","L","XL"],
  img: "main.jpg",                                // card photo
  gallery: ["angle-2.jpg", "angle-3.jpg"], // extra angles on the detail view
  sizeChart: "sizechart-tee-waffle.jpg",
  desc: "One-paragraph description.",
  bullets: ["Fabric", "Fit", "Care"] }
```

- Category chips are generated from `CATEGORIES` (only categories that have products are shown).
- Delivery charges, phone, WhatsApp and the order e-mail address are in `CONFIG`.
- Orders are still sent through **FormSubmit** to the e-mail in `CONFIG.email` — the mechanism is unchanged.

## Size charts

Branded size-chart images are the `sizechart-*.jpg` files:

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
