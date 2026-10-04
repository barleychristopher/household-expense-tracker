# Household Expense Tracker — version 1.2

A free, Android-friendly household budgeting PWA. It keeps personal spending separate from shared spending, tracks recurring bills, offsets those bills with net rental income, and calculates a monthly settlement between two partners.

## What is new in v1.2
- Monthly take-home salary figures for both partners.
- Net rental income (rent less entered property costs) offsets recurring household bills first because rent is received into the account that pays those bills.
- The remaining recurring bills are split in proportion to the two salaries only.
- Shared grocery budget defaults to £500 per month and tracks expenses in the Groceries category marked Shared.
- Transactions can be marked Personal or Shared. Personal grocery transactions are excluded from the shared grocery budget and settlement.
- Separate monthly personal spending budgets for each partner.
- Monthly settlement shows the partner's share of remaining recurring bills and shared groceries, credits groceries paid by the partner, and subtracts transfers already received.
- JSON backup/restore and CSV transaction export.

## Important calculation rules
1. Net rent is `max(0, rent received - property costs)`.
2. Net rent offsets recurring bills up to the value of those bills. Any excess rental income is not carried forward or applied to groceries in this version.
3. The remaining recurring bills are split using salary percentages. If both salaries are zero, the app uses a 50/50 split.
4. Shared grocery spending is based on expense transactions in the Groceries category marked Shared. The £500 limit is a budget, not an automatic bill.
5. The monthly settlement is an estimate: partner share of remaining bills + partner share of shared groceries - groceries paid by partner - transfers already received. A negative result means the app calculates that you owe your partner.
6. Property costs are whatever costs you choose to enter; this is not a tax or accounting calculation.

## Updating an existing GitHub Pages app
1. Download and extract the ZIP.
2. In your existing GitHub repository, upload the files from the extracted folder to the repository root and choose to replace/overwrite existing files when prompted. Include `index.html`, `manifest.json`, `sw.js`, `icon.svg`, `icon-192.png`, `icon-512.png`, and `README.md`.
3. Wait for GitHub Pages deployment to finish. Open the same published URL in Chrome on Android and refresh it; if needed, close the app completely and reopen it, then refresh again. The service worker cache name has changed so the new app shell can be downloaded.
4. The app uses the same browser storage key and upgrades saved data in place, so replacing the code should not delete existing transactions. Nevertheless, before updating, open the old app and use Settings → Export backup. Never use Clear site data to force an update unless you have a verified backup, because that can erase local records.
5. Test a small sample transaction, the £500 grocery budget, income figures, recurring bills, settlement, and JSON export/restore before relying on the new version.

## Local data and privacy
- Records stay in the browser profile on the device; this version does not sync between phones.
- Do not commit transaction exports or JSON backups to GitHub. Keep your repository free of real household financial records.
- Export backups regularly. Clearing browser/site storage can erase records.
- The app does not connect to bank accounts.

## PWA files
- `index.html` — app interface and logic
- `manifest.json` — installable app metadata
- `sw.js` — offline app-shell cache
- `icon-192.png`, `icon-512.png`, `icon.svg` — app icons
