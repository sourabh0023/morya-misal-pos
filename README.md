# Morya Misal POS

Mobile-first ordering and billing app for a small restaurant. Plain HTML, CSS and JavaScript, so there is no build step.

Features: menu search, category chips, favourites and best sellers, cart with quantity controls, table selection, bill preview (subtotal, discount, GST, round off, total), mark payment received (Cash / UPI / Card), order history, restaurant settings, and 80mm thermal receipts you can print or reprint from the browser. It installs to a phone home screen and works offline.

It runs in **demo mode**: sample menu and orders, no login, no payment service. Orders and settings are saved in the browser's local storage on each device.

## Deploy on Vercel

**Option 1: Vercel CLI**

```bash
cd morya-misal-pos
npx vercel          # first deploy (preview)
npx vercel --prod   # production
```

**Option 2: GitHub**

1. Push this folder to a new GitHub repository.
2. In Vercel choose Add New, then Project, and import the repository.
3. Framework Preset: **Other**. Leave Build Command and Output Directory empty. Deploy.

## Run locally

```bash
npx serve .
```

Then open the address it prints. Open it on your phone over the same Wi-Fi to try the touch layout.

## Printing receipts

1. Pair your 80mm thermal printer with the phone or computer (Wi-Fi or Bluetooth).
2. Open a bill and tap **Print bill** (or **Reprint bill** from Order history).
3. Choose the printer, set paper to 80mm and margins to None.

## Customise

- Restaurant name, address, phone, GST number, tax percentage and receipt footer: Settings tab in the app.
- Menu items and prices: the `MENU` array near the top of the script in `index.html`.
- After editing files, change `CACHE` in `sw.js` (for example to `v2`) so phones pick up the update.

## Limits

Data is stored per browser, so two phones will not see each other's orders. Sharing orders between devices needs a backend (for example Supabase or Vercel KV), which is not included.
