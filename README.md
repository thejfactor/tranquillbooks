# tranquillbooks

## About This Repo

This repo powers the QR codes printed in TranQuill Books' paperbacks (KDP). Each QR code encodes a short URL on `qr.tranquillbooks.com` (served via GitHub Pages, see `CNAME`). That URL loads a tiny redirect page, which looks up the book's Amazon ASIN in a central JSON list and forwards the reader to the book's Amazon page. Because the QR code only points at this site, the Amazon destination can be changed later by editing a JSON file, without reprinting the book.

**How it works:** QR code -> `qr.tranquillbooks.com/<Series>/<ProductID>/` -> `<Series>/<ProductID>/index.html` -> reads `lists/<List>.json` -> redirects to `https://www.amazon.com/dp/<ASIN>`.

### Repo Layout

| Path | Purpose |
|---|---|
| `<Series>/<ProductID>/index.html` | Redirect page for one book. Only `productID` and the list file path differ between pages. |
| `lists/*.json` | Lookup lists mapping product ID to ASIN, plus global settings and messages. `LPWSproducts.json` serves SharpAndCalm; `CWGeneric.json` serves CrossWord. |
| `index.html` | Site root page. |
| `CNAME` | Custom domain (`qr.tranquillbooks.com`). |

## Table of Contents

- [TranQuill Books](#tranquill-books) - registry of all live QR paths
  - [SharpAndCalm](#sharpandcalm) - 15 books + 1 collection, plus 2 XL books + 1 XL collection (19 pages), list: `lists/LPWSproducts.json`
  - [CrossWord](#crossword) - Divya Darshan, list: `lists/CWGeneric.json`
- [Adding a New Book](#adding-a-new-book) - step-by-step procedure (QR path + Amazon URL as inputs; ask whether to use a new or existing list)

---

## TranQuill Books

### SharpAndCalm

Each URL below is the QR code target. When scanned, it looks up the book's entry in [`lists/LPWSproducts.json`](lists/LPWSproducts.json) and forwards the reader to the Amazon product review page for that book.

| # | Book Title | QR URL | Points To |
|---|---|---|---|
| 1 | The Animal Kingdom | `qr.tranquillbooks.com/SharpAndCalm/the_Animal_Kingdom/` | amazon.com/dp/B0H9MRN56L |
| 2 | Earth & Sky | `qr.tranquillbooks.com/SharpAndCalm/Earth_and_Sky/` | amazon.com/dp/B0H9T1PNPL |
| 3 | The Turning Year | `qr.tranquillbooks.com/SharpAndCalm/the_Turning_Year/` | amazon.com/dp/B0HBF8HJDD |
| 4 | The Heart of the Home | `qr.tranquillbooks.com/SharpAndCalm/the_Heart_of_the_Home/` | amazon.com/dp/B0HB7CMGBT |
| 5 | Celebrations & Traditions | `qr.tranquillbooks.com/SharpAndCalm/Celebrations_and_Traditions/` | amazon.com/dp/B0CP9J1CX9 (placeholder, not yet updated) |
| 6 | Oceans & Shores | `qr.tranquillbooks.com/SharpAndCalm/Oceans_and_Shores/` | amazon.com/dp/B0H9ZB7CK7 |
| 7 | Faithful Companions | `qr.tranquillbooks.com/SharpAndCalm/Faithful_Companions/` | amazon.com/dp/B0HB97XY1V |
| 8 | The Sporting Life | `qr.tranquillbooks.com/SharpAndCalm/the_Sporting_Life/` | amazon.com/dp/B0CP9J1CX9 (placeholder, not yet updated) |
| 9 | Country Life | `qr.tranquillbooks.com/SharpAndCalm/Country_Life/` | amazon.com/dp/B0CP9J1CX9 (placeholder, not yet updated) |
| 10 | Moments in History | `qr.tranquillbooks.com/SharpAndCalm/Moments_in_History/` | amazon.com/dp/B0CP9J1CX9 (placeholder, not yet updated) |
| 11 | Tales, Myths & Legends | `qr.tranquillbooks.com/SharpAndCalm/Tales_Myths_and_Legends/` | amazon.com/dp/B0CP9J1CX9 (placeholder, not yet updated) |
| 12 | The Working World | `qr.tranquillbooks.com/SharpAndCalm/the_Working_World/` | amazon.com/dp/B0CP9J1CX9 (placeholder, not yet updated) |
| 13 | Stage, Screen & Song | `qr.tranquillbooks.com/SharpAndCalm/Stage_Screen_and_Song/` | amazon.com/dp/B0CP9J1CX9 (placeholder, not yet updated) |
| 14 | The Age of Travel | `qr.tranquillbooks.com/SharpAndCalm/the_Age_of_Travel/` | amazon.com/dp/B0CP9J1CX9 (placeholder, not yet updated) |
| 15 | Home & Garden | `qr.tranquillbooks.com/SharpAndCalm/Home_and_Garden/` | amazon.com/dp/B0HBLDPN57 |
| C1 | The Living World (collection) | `qr.tranquillbooks.com/SharpAndCalm/Collection_TheLivingWorld/` | amazon.com/dp/B0H61ZT269 |

**XL (extra large print) collection:** the first two XL books and the XL collection page.

| # | Book Title | QR URL | Points To |
|---|---|---|---|
| XL1 | Earth & Sky XL | `qr.tranquillbooks.com/SharpAndCalm/Earth_and_SkyXL/` | amazon.com/dp/B0HR2K6B74 |
| XL2 | The Heart of the Home XL | `qr.tranquillbooks.com/SharpAndCalm/the_Heart_of_the_HomeXL/` | amazon.com/dp/B0HQYCR6WW |
| CXL | The Living World XL (collection) | `qr.tranquillbooks.com/SharpAndCalm/Collection_TheLivingWorldXL/` | amazon.com/dp/B0HQXTF4F8 |

**List-only entries without a redirect page:** `lists/LPWSproducts.json` also holds `tractor-edition` (`B09YYYYYYY`, amazon.in) and `find-me-2yr` (`B07ZZZZZZZ`). Both are dummy placeholder ASINs and have no `index.html`, so they are not live QR targets.

Note: the page folders `Collection_TheLivingWorld/` and `Collection_TheLivingWorldXL/` use the product IDs `collection_The_Living_World` and `collection_The_Living_WorldXL` (the list keys); the folder name and the key differ, and the page's `productID` is what must match the list.

### CrossWord

Each URL below is the QR code target. When scanned, it looks up the book's entry in [`lists/CWGeneric.json`](lists/CWGeneric.json) and forwards the reader to the Amazon product page for that book.

| # | Book Title | QR URL | Points To |
|---|---|---|---|
| 1 | Divya Darshan | `qr.tranquillbooks.com/CrossWord/DivyaDarshan/` | amazon.com/dp/B0HPNPMGVH |

## Adding a New Book

Inputs needed: the **QR code path** (e.g. `https://qr.tranquillbooks.com/CrossWord/DivyaDarshan`) and the **Amazon URL** (e.g. `https://www.amazon.com/dp/B0HPNPMGVH`).

1. **Parse the inputs.**
   - QR path `https://qr.tranquillbooks.com/<Series>/<ProductID>` gives the folder `<Series>/<ProductID>/` and the product ID `<ProductID>`.
   - Amazon URL `https://www.amazon.com/dp/<ASIN>` gives the ASIN. If the domain is not `amazon.com` (e.g. `amazon.in`), add a `baseURL` override to the entry (e.g. `"baseURL": "https://www.amazon.in/dp/"`).
2. **Ask which list to use:** create a new list, or use an existing one? Existing lists live in [`lists/`](lists/) (currently `LPWSproducts.json` and `CWGeneric.json`).
   - **Existing list:** add a new entry to its `products` object.
   - **New list:** ask for the list file name (e.g. `NewSeries.json`). Copy the `globalSettings` block from an existing list, start `products` empty, then add the new entry.
3. **Add the product entry** to the chosen list's `products` object. The key must exactly match the product ID (case-sensitive):
   ```json
   "<ProductID>": {
     "asin": "<ASIN>",
     "loadingMessage": "Loading the <Book Title> review page..."
   }
   ```
   Optional per-entry overrides: `baseURL`, `errorMessage`.
4. **Create the redirect page** at `<Series>/<ProductID>/index.html` by copying an existing page (e.g. `CrossWord/DivyaDarshan/index.html`) and changing only two lines:
   - `const productID = "<ProductID>";`
   - `fetch('/lists/<ListFile>.json')`
5. **Update this README** by adding a row to the series table (or a new series section for a new series or list).
6. **Do not modify existing entries or pages** unless explicitly asked.
7. **Validate** that the list file is valid JSON and that the product ID in the page matches the key in the list.
8. **Commit and push** to `main`. The site is served from the repo root (see `CNAME`), so the new path goes live after the push.
