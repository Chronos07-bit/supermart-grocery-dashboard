# Supermart Grocery Sales Dashboard

A single-page, interactive management dashboard built by Arka Bhattacharya for the Sapphire IQ student project. It helps the management team understand sales, profit, products, discounts and geographic performance in one place, without going through the full dataset.

**Live demo:** `https://chronos07-bit.github.io/supermart-grocery-dashboard/`

## What it shows
| Section | Business question | Content |
|---|---|---|
| 1. Overall Sales Performance | How is the overall grocery business performing? | Total sales, profit, margin, orders, average order value, average discount; category share; sales by region; monthly sales & profit trend |
| 2. Product Performance | Which products and categories drive sales and profit? | Sales by category and sub-category; table flagging sub-categories with high sales but below-average margin |
| 3. Profit and Discount | How are discounts and profit related? | Profit by category and region; profit margin by discount level; discount–profit correlation |
| 4. Geographic Performance | Which locations contribute most? | Sales by state; top 10 cities by sales; city table flagging high sales with low margin |

Each section ends with auto-generated insight bullets that update with the filters.
Filters: Year, Category, Region.

## Data
`data/supermart_grocery_sales.csv` holds 9,994 orders (2015–2018) with 12 columns. The same data is embedded in `index.html`, so the page needs no server.

Notes: every order is in Tamil Nadu, so geographic detail is by city. The Region column has only one "North" order. The source PDF has dates in mixed formats, so only the order year and month are kept.

## Metric definitions
- **Total Sales / Profit** = sum of `Sales` / `Profit` for the filtered orders.
- **Profit Margin %** = Profit ÷ Sales.
- **Average Order Value** = Sales ÷ number of orders.
- **High sales, low profit** = sales at or above the median of the group (sub-category or city) but margin below the overall margin.
- **Discount vs profit** = Pearson correlation across orders (discount vs profit margin, and vs profit amount).

## Run locally
Open `index.html` in a browser (needs internet for the Chart.js CDN script).

## Publish on GitHub Pages
1. Create a repo named `supermart-grocery-dashboard` and upload `index.html`, `README.md` and the `data` folder.
2. Settings → Pages → Deploy from a branch → `main` / `(root)` → Save.
3. Submit the repo link (and the Pages link).

## Tech
HTML, CSS, vanilla JavaScript, Chart.js 4.4.1.
