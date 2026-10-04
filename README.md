# Household Expense Tracker (MVP)

A free, mobile-friendly Progressive Web App for manually tracking shared household expenses and income. It uses browser localStorage; no account, server, bank connection, or subscription is required for the first version.

## Features
- Add, edit and delete expense/income transactions
- Category, date, amount, payment method, notes, and household member
- Monthly totals and category budget limits
- Transaction search and filters
- Six-month report chart and category breakdown
- Add/edit categories and household member names
- Export full JSON backup, export transactions to CSV, restore JSON backup
- PWA manifest and service worker for installation/offline app shell

## Important limitations
- Data stays in the current browser profile on the current device. Installing the app on another phone does not share or sync data.
- Export JSON backups regularly. Clearing browser/site data can erase records.
- The local browser storage is not an encrypted financial database; protect your device and browser profile.
- No bank integration, account login, or cloud sync is included.

## Quick test on a computer
1. Unzip the project folder.
2. In the folder, run a local web server (Python installed): `python -m http.server 8000`
3. Open `http://localhost:8000` in Chrome.
4. Add sample transactions, adjust budgets, export JSON/CSV, then test restoring a JSON backup.

## Publish for Android installation
A PWA must be served over HTTPS (or localhost for development) to be installable in supporting browsers.

Free static hosting option: GitHub Pages.
1. Create/sign into a GitHub account.
2. Create a new repository. Do not put real household financial data in the repository.
3. Upload the files in this folder to the repository root (index.html, manifest.json, sw.js, icons and README).
4. In repository Settings → Pages, enable deployment from the `main` branch and root folder.
5. Wait for the published HTTPS site URL, then open it in Chrome on Android.
6. Use Chrome menu → **Install app** or **Add to Home screen** (wording varies).
7. Test add/edit/delete, export a backup, close/reopen, and offline behavior before relying on it.

## Household sharing
This first version tracks who paid, but the data itself is local. For both partners to see the same live records, a next version needs authentication and a shared cloud database (for example Supabase or Firebase), plus security rules and privacy testing. Don't use the local-only version as the sole record of important financial data.


## Proportional recurring-bill splitting (v1.1)

Open **Split bills** to enter each person's monthly take-home income, monthly rental income received, and monthly property costs. Net rental income is calculated as rent minus those costs and treated as shared income, allocated equally to both partners when calculating contribution percentages. Add recurring household bills and choose weekly, monthly, quarterly, or annual frequency; each is converted to a monthly equivalent. Only active bills in this list are included in the contribution calculation; one-off spending and variable everyday purchases are excluded.

The app stores the income settings and recurring bills locally in this browser, alongside transactions. Export a JSON backup regularly. This version does not synchronise data between phones.
