# call-center-dashboard# Call Center Dashboard

**One-line:** Interactive dashboard for call center KPIs (calls, duration, avg rating, customer gender split) built using Power BI / Excel.

## Features
- Monthly call trend chart and KPI cards (calls, duration, avg rating).
- Regional/representative level table with sparklines and mini-bars.
- Filters: year, month, product/rep (interactive slicers).
- Drilldown from KPI to rep-level performance.
- Exportable visuals and screenshot-friendly layout for presentations.

## Tech stack
- Power BI Desktop (.pbix) and Excel for prototype visuals
- Data: CSV exports (calls, customers, reps)
- Optional: Power BI Service for publishing (if available)

## Files in this repo
- `reports/CallCenter_Dashboard.pbix` — Power BI file (if included)
- `reports/call_center_dashboard.xlsx` — Original Excel dashboard (if used)
- `data/` — Raw & processed CSVs
- `screenshots/` — PNG screenshots of the dashboard
- `docs/design_notes.md` — Data model & calculation notes

## Data model & measures
- `Calls` fact table with date, rep, customer_id, duration, rating, amount
- `dim_customer`, `dim_rep`, `dim_date` lookup tables
- Measures (DAX):
  - `Total Calls = COUNTROWS(Calls)`
  - `Total Duration = SUM(Calls[duration])`
  - `Avg Rating = AVERAGE(Calls[rating])`
  - `Calls This Month = CALCULATE([Total Calls], SAMEPERIODLASTMONTH(dim_date[Date]))`

(Include full DAX formulas in `docs/design_notes.md`)

## How to run locally
1. Download or clone the repository.
2. Open `reports/CallCenter_Dashboard.pbix` in Power BI Desktop (or `call_center_dashboard.xlsx` in Excel).
3. If data files are relative, refresh data sources — update paths if needed (`data/raw/*.csv`).
4. Refresh the visuals. Save a copy if you customize.

## Deployment & sharing
- To share interactive dashboard: publish to Power BI Service and create a workspace. Optionally export to PDF or publish to web (if allowed by company policy).
- If pbix is sensitive/large, upload to Releases or provide a OneDrive link.

## Screenshots
See `/screenshots` for high-resolution images of the dashboard.

## License
MIT License — see `LICENSE` (optional)
