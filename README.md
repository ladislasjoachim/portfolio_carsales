# portfolio_carsales
My project where I analyze car sales in the US. The database is taken from https://www.kaggle.com/datasets/syedanwarafridi/vehicle-sales-data

# US Automotive Market Analysis
**2014–2015 | Python, pandas, Tableau | Data: Kaggle — Vehicle Sales Dataset**

An exploratory analysis of ~500,000 used vehicle listings from the US market, covering market structure, pricing factors, brand segmentation, and consumer preferences.

---

## Key Findings

**Market structure:** Sedans and SUVs together account for over 70% of all sales. Ford leads with ~95K sales, nearly double second-place Chevrolet (~60K). Automatic transmission dominates at 80%+.

**Mileage vs price (R² ≈ 0.53, exponential fit):** Price decays exponentially with mileage, not linearly — the steepest drop happens in the first ~50,000 miles. A car loses ~40% of its value by 50,000 miles and ~63% by 100,000 miles; above 150,000+ miles, residual value drops to $1,000–2,000. Mileage alone explains roughly half the price variation across individual listings — the rest comes from make, condition, and year.

**Depreciation by age:** Cars newer than 5 years retain value aggressively — each model year adds $1,000–2,000. After 10 years, depreciation slows significantly.

**Price by body type:** Convertibles (~$18,500) and crew cabs (~$17,900) are the most expensive. Hatchbacks (~$10,000) and wagons (~$10,300) are the most affordable.

**Brand range:** Rolls-Royce averages ~$156,000 vs Saturn at ~$3,500 — a 44× difference. The cheapest mainstream brands (Saturn, Pontiac, Mercury) are discontinued, explaining their low secondary market prices.

**Color preferences:** Neutral colors (black, white, gray, silver) account for 73% of all sales.

---

## Data Cleaning

Raw data was cleaned and validated in `notebooks/car_sales_cleaning.ipynb` before analysis:

| Step | Rows removed | Rows remaining |
|---|---|---|
| Initial load | — | 558,837 |
| Filter year ≥ 1995 (excludes rare vintage/collector listings) | 913 | 557,924 |
| Remove invalid transmission value (data-entry error) | 26 | 557,898 |
| Remove rows missing `vin`, `make`, or `odometer` | 10,258 | 547,640 |
| Remove duplicate `(vin, saledate)` pairs | 98 | 547,542 |
| Remove implausible selling price (Ford Escape listed at $230K — data-entry error) | 1 | 547,541 |
| **Final dataset** | | **547,541** |

Also standardized: ~10 duplicate brand names (e.g. `ford tk`, `ford truck` → `ford`) via fuzzy matching, inconsistent body-type labels (e.g. cab variants → `crew cab`), and malformed color/transmission values. Extreme mileage values (>300K) were kept, since high mileage is plausible for commercial/fleet vehicles and not necessarily an error.

---

## Project Structure

```
├── notebooks/                         # Data cleaning & analysis
├── vehicle_sales_presentation.pdf     # Full slide deck with charts
└── README.md
```

---

## Tools & Methods

- **Python** (pandas, NumPy) — data cleaning, aggregation, feature analysis
- **Tableau** — bar charts, scatter plots, trend lines, segmentation visuals
- **Dataset** — 558,837 raw listings (547,541 after cleaning), USA, December 2014 – July 2015
- **Statistical analysis** — exponential regression (R² ≈ 0.53) for mileage-price relationship

---

## Data Source & License

Data sourced from [Kaggle — Vehicle Sales Dataset](https://www.kaggle.com/datasets/syedanwarafridi/vehicle-sales-data), released under the MIT License. This project is for educational and portfolio purposes only. All conclusions are based on the provided dataset and may not reflect current market conditions.
