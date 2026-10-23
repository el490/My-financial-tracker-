# Finanças — personal finance tracker

A single-page budgeting app: salary + USD commission split into pots, bills, installment
purchases, a forecast of the coming months, and a commission simulator.
Your data stays on your device (browser localStorage). Nothing is sent anywhere.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app (also works on its own if you just double-click it) |
| `manifest.webmanifest`, `icons/` | Makes it installable on the home screen |
| `sw.js` | Offline support (keeps a copy of the app on the phone) |
| `vendor/chart.umd.js` | Chart.js, bundled so the History chart works offline |
| `test-split.js` | Tests for the commission split: `node test-split.js` |

## Install it on your phone (about 5 minutes, free)

A home-screen app must be opened from a web address (https), not as a file.
Publish this folder once, using either option below.

### Option A — GitHub Pages
1. Create a free account at github.com and click **New repository** (e.g. `financas`).
   On the free plan Pages needs a **public** repository. Only the app's code is public; your
   numbers never leave your phone.
2. Click **uploading an existing file** and drag in everything in this folder
   (including the `icons` and `vendor` folders). Click **Commit changes**.
3. Go to **Settings → Pages**, set **Source: Deploy from a branch**, **Branch: main / (root)**, then **Save**.
4. After about a minute your app is live at `https://YOUR-USERNAME.github.io/financas/`.

### Option B — Netlify
1. Create a free account at netlify.com.
2. Go to **Add new site → Deploy manually** and drag this whole folder in.
3. You get an address like `https://something.netlify.app` (you can rename it).

### Then, on the phone
- **iPhone:** open the address in **Safari** → Share button → **Add to Home Screen**.
- **Android:** open it in **Chrome** → menu **⋮** → **Install app** (or use the button in Ajustes).

Open it once while online. After that it works with no internet.

## Moving your data

Each address keeps its own data. Your data doesn't follow you from the file version
(or another phone) to the installed app automatically:

1. In the old copy: **Ajustes → Exportar backup** (downloads a `.json` file).
2. In the installed app: **Ajustes → Importar backup** and pick that file.

The app reminds you to export a backup every 30 days. Keep a copy somewhere safe
(Google Drive, iCloud, email to yourself). If the browser data is cleared, the backup is the
only copy.

## Updating the app later

Upload the changed files again. In `sw.js`, change `CACHE = 'financas-v1'` to `'financas-v2'`
(and so on each time) so phones download the new version. Your data is not affected.
