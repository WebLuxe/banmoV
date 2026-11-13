# V8 Motors website

Plain HTML/CSS/JS, hosted free on GitHub Pages. No server and no database: the stock list is one file, `data/cars.json`, which lives in this repository.

## Pages
- `index.html`, `cars.html`, `car.html?id=…`, `sell.html`, `about.html`, `contact.html`
- `js/data.js` loads `data/cars.json` and turns it into the cards and car pages. `js/snapshot.js` is a built-in copy used only if that file can't be loaded (for example when a page is opened straight from disk).

## Admin (`/admin/`)
`admin/index.html` is the stock admin. Sign in with a GitHub **fine-grained token** that has **Contents: Read and write** on this repository only (the sign-in page explains how to make one).

Every time you save, the admin makes one commit to this repository: the updated `data/cars.json`, plus any new photos in `images/cars/` (resized to 1600px WebP in the browser first). GitHub Pages republishes the site, which takes about a minute.

- **Add a car / Edit**: details, price, photos (drag to reorder; the first is the cover).
- **Mark sold**: hides the car from the website but keeps it in the list.
- **Delete**: removes it from the list and deletes its uploaded photos.

Older photos still load from `https://v8.farhaan.info/uploads/…`; new uploads are stored in this repository.

## Styles
Edit `scss/`, then `npm install` once and `npm run build:css` to rebuild `css/style.css`.
