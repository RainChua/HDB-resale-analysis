# HDB Resale Price Analysis

## Overview
This repository contains an exploratory analysis of HDB resale flat prices using several CSV data files. The notebook `HDB Feb Outlier Analysis.ipynb` loads multiple source files, combines them, and analyzes resale price trends and outliers.

## Data
- All raw CSV files are stored in the `data/` folder.
- Example filenames present in this workspace:
  - `ResaleFlatPricesBasedonApprovalDate19901999.csv`
  - `ResaleFlatPricesBasedonApprovalDate2000Feb2012.csv`
  - `ResaleFlatPricesBasedonRegistrationDateFromMar2012toDec2014.csv`
  - `ResaleFlatPricesBasedonRegistrationDateFromJan2015toDec2016.csv`
  - `ResaleflatpricesbasedonregistrationdatefromJan2017onwards.csv`

## Notebook Summary
The notebook performs the following steps (run cells in order):

- **Imports**: `pandas`, `pathlib`, `matplotlib` (for plotting).
- **Load & combine**: Scans the `data/` folder, loads CSV files into DataFrames, and concatenates them into `combined_df`.
- **Year extraction**: Extracts `Year` from the `month` column (expected format `YYYY-MM`) or falls back to date parsing.
- **Min / Max by year**: Computes `min` and `max` of `resale_price` per year and prints them.
- **Plot min/max**: Plots min and max resale prices over years (matplotlib). Optionally uses a square figure.
- **Counts above 1,000,000**: Computes count and percentage of records where `resale_price > 1,000,000` per year and prints a summary table.
- **Combined plot**: Visualizes counts (bars) and percentage (line) using a twin y-axis so both absolute and relative metrics are visible.

## Requirements
- Python 3.8+
- pandas
- matplotlib

Install quickly with:

```bash
pip3 install pandas matplotlib
```

(Or create a `requirements.txt` with `pandas` and `matplotlib` and run `pip3 install -r requirements.txt`.)

## How to run
1. Open `HDB Feb Outlier Analysis.ipynb` in Jupyter (or VS Code Jupyter extension).
2. Ensure the `data/` folder is in the project root and contains the CSV files.
3. Run cells sequentially. Check printed output for per-year summaries and view the plots inline.

## Notes & Next Steps
- The notebook expects a `resale_price` column; if column names differ across files adapt the column detection logic.
- Twin y-axis charts are useful to show absolute counts and relative percentages together, but interpret with care due to different scales.
- Possible next steps: interactive Plotly versions, filtering by flat type/region, or saving summary tables to CSV.

---
Generated from `HDB Feb Outlier Analysis.ipynb`.
