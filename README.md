# California Housing — Exploratory Analysis & Baseline Regression

A reproducible end-to-end analysis of the California Housing dataset combining exploratory data analysis, statistical inference, geographic comparisons, and an interpretable OLS regression baseline.

## Project focus

The notebook answers four practical questions:

1. **What does the dataset look like?** — distributions, outliers, completeness, and feature relationships.
2. **Which variables appear most informative?** — correlation analysis and feature ablation.
3. **Do broad geographic groupings show different house-value patterns?** — North/South and Coastal/Inland comparisons.
4. **How strong is a transparent linear baseline?** — OLS diagnostics, validation performance, and final test evaluation.

## Analysis pipeline

**Data quality → EDA → Correlation → Confidence interval → Geographic tests → Train/Validation/Test split → OLS → Residual diagnostics → Feature ablation → Final test evaluation**

## Key findings

- The dataset contains **20,640 complete observations**.
- `MedInc` is the strongest linear correlate of `MedHouseVal` (about **0.69**).
- Removing `MedInc` caused the largest validation RMSE increase in the ablation study (about **+0.148**).
- `Latitude` and `Longitude` also contribute meaningful predictive signal.
- The completed baseline achieved approximately:
  - **RMSE:** 0.7218
  - **MAE:** 0.5217
  - **R²:** 0.6060
- The Breusch–Pagan test produced a p-value effectively equal to **0.000**, indicating heteroscedasticity and highlighting a limitation of classical OLS inference.
- The simple North/South and Coastal/Inland mean comparisons were not statistically significant at the 5% level (p ≈ 0.075 and p ≈ 0.195 respectively).

## Why this matters

This project is deliberately **baseline-first**. The purpose is not to present a production valuation system, but to establish a transparent benchmark and demonstrate a complete analytical workflow before introducing more complex models.

## Dataset

The notebook uses the California Housing dataset loaded through `sklearn.datasets.fetch_california_housing`.

`MedHouseVal` is expressed in units of **$100,000s**.

## Repository contents

- `california-housing-regression-analysis-final.ipynb` — full analysis notebook

## Reproduction

Run the notebook from top to bottom in a Python 3 environment with:

- pandas
- numpy
- matplotlib
- seaborn
- scipy
- scikit-learn
- statsmodels

The notebook loads the dataset through scikit-learn, so no separate data file is required.

## Next steps

Natural extensions are robust regression, nonlinear tree-based models, feature engineering, interactions, and richer geographic or temporal data.

> **Disclaimer:** This is an educational data-science project. It is not financial or investment advice.
