# call-center-dashboard

**One-line:** Interactive dashboard for call center KPIs (calls, duration, avg rating, customer gender split) built using  Excel.

## Features
- Monthly call trend chart and KPI cards (calls, duration, avg rating).
- Regional/representative level table with sparklines and mini-bars.
- Filters: year, month, product/rep (interactive slicers).
- Drilldown from KPI to rep-level performance.
- Exportable visuals and screenshot-friendly layout for presentations.

## Tech stack
- Excel for prototype visuals
- Data: xlsx exports (calls, customers, reps)

## Files in this repo
- `reports/call_center_dashboard.xlsx` — Original Excel dashboard (if used)
- `data/` — Raw & processed xlsx
- `screenshots/` — PNG screenshots of the dashboard

## Data model & measures
- `Calls` fact table with date, rep, customer_id, duration, rating, amount
- `dim_customer`, `dim_rep`, `dim_date` lookup tables
- Measures (DAX):
  - `Total Calls = COUNTROWS(Calls)`
  - `Total Duration = SUM(Calls[duration])`
  - `Avg Rating = AVERAGE(Calls[rating])`
## How to run locally
1. Download or clone the repository.
2. Open `CallCenter_Dashboard.xlsx` in Excel
3. If data files are relative, refresh data sources — update paths if needed (`data/raw/*.xlsx`).
4. Refresh the visuals. Save a copy if you customize.

## Screenshots
See `/screenshots` for high-resolution images of the dashboard.

## License
MIT License — see `LICENSE` (optional)
