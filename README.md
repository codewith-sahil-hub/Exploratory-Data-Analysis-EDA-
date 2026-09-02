# CodeAlpha_ExploratoryDataAnalysis

## Task 2: Exploratory Data Analysis — Data Analytics Internship (CodeAlpha)

EDA on the book price/rating dataset produced in Task 1
(`CodeAlpha_WebScraping`), using **pandas, matplotlib, seaborn, and scipy**.

## Files

```
CodeAlpha_ExploratoryDataAnalysis/
├── eda_analysis.py              # Main EDA script (run this)
├── generate_sample_data.py      # Generates sample data for demo purposes
├── product_price_analysis.csv   # Sample dataset (swap for your real scraped data)
├── charts/                      # Output visualizations
│   ├── price_distribution.png
│   ├── price_by_rating.png
│   └── correlation_heatmap.png
└── requirements.txt
```

> **Note:** `product_price_analysis.csv` here is a generated sample matching
> the schema from Task 1 (title, price_gbp, price_bucket, rating_stars,
> in_stock, value_score), used because this dataset was built where live
> scraping wasn't possible. Replace it with your real Task 1 output —
> `eda_analysis.py` works identically either way.

## EDA workflow followed

1. **Meaningful questions asked up front** (see top of `eda_analysis.py`) —
   e.g. does rating correlate with price, are premium items less often in
   stock, are outliers real or errors, is the data clean enough to trust.
2. **Structure exploration** — shape, dtypes, `.describe()`.
3. **Data quality check** — missing values, duplicate rows, before any
   conclusions are drawn.
4. **Trends & anomalies** — price distribution, average price by rating,
   IQR-based outlier detection.
5. **Hypothesis testing** — Pearson correlation (rating vs. price) and
   Welch's t-test (in-stock vs. out-of-stock pricing), both with p-values.
6. **Visualization** — histogram, boxplot, correlation heatmap saved to
   `charts/`.

## How to run

```bash
pip install -r requirements.txt
python eda_analysis.py
```

Console output includes structure summary, data quality report, and
hypothesis test results. Charts are saved to `charts/`.

## Key findings (on the sample dataset)

- Moderate, statistically significant correlation between rating and price
  (r ≈ 0.39, p < 0.001) — higher-rated items trend more expensive, but
  price alone doesn't determine rating.
- Statistically significant price difference between in-stock and
  out-of-stock items (p ≈ 0.018).
- A handful of IQR-flagged price outliers — worth manual review rather
  than automatic removal, since they may be legitimate premium items.
- Data quality issues (duplicates, missing ratings) were present and
  handled explicitly rather than silently ignored.

## Notes

Completed as part of the CodeAlpha Data Analytics Internship —
Task 2: Exploratory Data Analysis.
