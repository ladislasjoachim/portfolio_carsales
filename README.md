# portfolio_carsales
My project where I analyze car sales in the US. The database is taken from https://www.kaggle.com/datasets/syedanwarafridi/vehicle-sales-data

# US Automotive Market Analysis
**2014–2015 | Python, pandas, Tableau | Data: Kaggle — Vehicle Sales Dataset**

An exploratory analysis of ~500,000 used vehicle listings from the US market, covering market structure, pricing factors, brand segmentation, and consumer preferences.

---

## Key Findings

**Market structure:** Sedans and SUVs together account for over 70% of all sales. Ford leads with ~95K sales, nearly double second-place Chevrolet (~60K). Automatic transmission dominates at 80%+.

**Mileage vs price (R² = 0.976):** Strong negative correlation. A car loses ~40% of its value after 50,000 km and ~63% after 100,000 km. After 150,000+ km, residual value drops to $1,000–2,000.

**Depreciation by age:** Cars newer than 5 years retain value aggressively — each model year adds $1,000–2,000. After 10 years, depreciation slows significantly.

**Price by body type:** Convertibles (~$18,500) and crew cabs (~$17,900) are the most expensive. Hatchbacks (~$10,000) and wagons (~$10,300) are the most affordable.

**Brand range:** Rolls-Royce averages ~$156,000 vs Saturn at ~$3,500 — a 44× difference. The cheapest mainstream brands (Saturn, Pontiac, Mercury) are discontinued, explaining their low secondary market prices.

**Color preferences:** Neutral colors (black, white, gray, silver) account for 73% of all sales.

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
- **Dataset** — ~500,000 vehicle listings, USA, December 2014 – July 2015
- **Statistical analysis** — linear regression (R² = 0.976) for mileage-price relationship

---

## Data Source & License

Data sourced from [Kaggle — Vehicle Sales Dataset](https://www.kaggle.com/datasets/syedanwarafridi/vehicle-sales-data), released under the MIT License. This project is for educational and portfolio purposes only. All conclusions are based on the provided dataset and may not reflect current market conditions.
