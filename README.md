# 🐟 Sockeye Tracker — open fish-data explorer

A friendly, no-login website for **viewing and exploring fish tagging data**. Built for community members, the public, and field crews — anyone who needs to see the data without an account on another system.

It shows your records as:
- an **Overview** dashboard with plain-language highlights and key numbers,
- an **Explore** table you can search, filter and sort,
- simple **Charts** (activity over time, who tagged what, fish size),
- a **Map** of where fish were caught and released,
- and a tap-to-open **detail card** for every single fish.

Everything runs in the browser. There is no server, no database, and nothing to log into.

---

## 📂 What's in this folder

| File | What it is |
|------|------------|
| `Sockeye Tracker.dc.html` | The website itself — this is what visitors open. |
| `fish-data.js` | Your data, as a file the website reads. **Replace this to update what everyone sees.** |
| `Update Data Tool.dc.html` | A helper page that combines one or many CSV exports into a new `fish-data.js`. |
| `README.md` | This file. |

---

## ▶️ Looking at it right now

Just open **`Sockeye Tracker.dc.html`** in any web browser. That's it.

---

## ✏️ Updating & accumulating data

**The whole database is the single file `fish-data.js`.** You never edit it by hand — you rebuild it whenever you have new data. Records *accumulate*: every CSV you add stacks on top of the rest, so 2025 and 2026, every site, all live together.

### Quick peek (only on your own computer)
Open the tracker and click **“Update data”** in the top-right. You get two choices:
- **➕ Add records to current** — appends a CSV to what's already showing (duplicates are skipped).
- **↺ Replace all data** — swaps in a fresh CSV instead.

This is perfect for checking new exports, but it only changes what *you* see in *your* browser. It does **not** change the live website for other people.

### Make it permanent for everyone (the real accumulation step)
To change what every visitor sees, rebuild `fish-data.js` with the builder:

1. Open **`Update Data Tool.dc.html`**.
2. **Add every CSV you want in the database** — all years, all sites — in one go (you can select several files at once, or drop them in one at a time). The running total climbs as you add them.
3. Leave **“Skip exact duplicate rows”** ticked so nothing gets counted twice.
4. Click **“Download fish-data.js”**.
5. Upload that file to GitHub, replacing the old one (see below). Done — the site now shows everything combined.

**Adding only new data later?** Instead of re-adding every old CSV, tick **“Include the data already in the site”** — it starts the total from the records already in `fish-data.js`, and you just add the new CSVs on top.

Your CSVs can have the same columns as the sample (Session, PIT Tag, SRR Code, Event Type, Length, Event Date, Event Site, Tagger, Latitude, Longitude, …). Extra or missing columns are fine — the site adapts, and the charts, filters, and map automatically pick up new sites, species, and years.

---

## 🌐 Putting it online for free (GitHub Pages)

You said you have a GitHub account — here's the whole thing, no coding required.

1. **Make a repository.** On [github.com](https://github.com), click **New repository**. Name it something like `fish-tracker`. Set it to **Public**. Click **Create**.
2. **Upload the files.** On the new repo page, click **Add file → Upload files**, then drag in:
   - `Sockeye Tracker.dc.html`
   - `fish-data.js`
   - `Update Data Tool.dc.html`
   - `README.md`
   - `support.js` *(this sits next to the `.dc.html` files — upload it too if present)*

   Click **Commit changes**.
3. **Turn on Pages.** Go to **Settings → Pages**. Under *Branch*, pick `main` and `/ (root)`, then **Save**.
4. Wait ~1 minute. GitHub shows you a public link like
   `https://YOUR-NAME.github.io/fish-tracker/Sockeye%20Tracker.dc.html`
5. Share that link. Anyone can open it — no account needed.

### Updating the live site later
1. Make a fresh `fish-data.js` with the **Update Data Tool** (above).
2. In your GitHub repo, open `fish-data.js`, click the **pencil ✏️**, then **Add file → Upload files** to replace it (or paste the new contents).
3. **Commit changes.** The website refreshes within a minute.

> Tip: for a cleaner web address, rename `Sockeye Tracker.dc.html` to `index.html` before uploading. Then your link is simply `https://YOUR-NAME.github.io/fish-tracker/`.

---

## 📜 License

This project is open source. A permissive **MIT License** is recommended — it lets anyone use, share, and build on it while keeping your credit. To apply it, add a file named `LICENSE` with the MIT license text (GitHub offers this automatically: **Add file → Create new file → name it `LICENSE` → “Choose a license template”**).

---

## 🙏 Credits & data

- Map tiles © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors, styled by [CARTO](https://carto.com/).
- Map rendering by [Leaflet](https://leafletjs.com/).
- Fish data is yours — please credit the collecting organization when you share.
