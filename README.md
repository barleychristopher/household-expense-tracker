# Household Expense Tracker 1.4

A mobile-friendly, installable web app for tracking personal and shared household finances in GBP. It stores records locally in the browser; it does not sync data between devices.

## Features
- Manual transaction entry with personal/shared classification.
- Household monthly summary: both salaries, net rental income, recurring shared bills, shared grocery spend and budget, estimated disposable income for each person, and settlement balance.
- Proportional split of recurring shared bills based on the two salaries after net rental income is applied against the bills.
- Shared grocery budget (default £500/month) and settlement tracking for transfers already received.
- Separate personal budgets and personal recurring bills (e.g. car finance, personal insurance, phone contracts), assigned to either household member.
- Monthly, weekly, quarterly and annual recurring-bill frequencies converted to monthly equivalents.
- JSON backup/restore and CSV transaction export.
- Installable PWA shell and basic offline app caching.

## Publish with GitHub Pages
1. Export a JSON backup from the existing app before updating.
2. Extract this ZIP.
3. Upload the *contents* of this folder to the root of the existing GitHub repository, replacing matching files and adding new files.
4. In GitHub, open Settings → Pages and ensure the existing Pages source is still configured.
5. Wait for deployment to complete, then open the same published URL in Chrome and refresh/reopen the app.
6. Check existing records are present before continuing. Do not clear browser site data.

## Notes on calculations
- Net rental income is rent received minus entered property costs, floored at zero. It is applied against shared recurring bills before the remaining bill balance is split between the two salaries.
- The £500 grocery budget is a tracking limit. Shared grocery spend is allocated by the salary-based percentages for the settlement calculation.
- Estimated disposable income = monthly take-home salary − allocated remaining shared bills − allocated shared groceries − active personal recurring bills − recorded personal expenses for that month. If the same personal recurring bill is also entered as a personal transaction, it will be deducted twice; enter it in one place only.
- Personal recurring bills do not affect shared bill contributions or settlement.
- If net rent exceeds recurring shared bills, excess rent is not carried forward or applied to groceries in this version.
- Data is stored in the browser's local storage. Use Settings → Export backup regularly. The app does not yet synchronise across devices.
