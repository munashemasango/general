# California Housing — Baseline Regression Notebook

A concise, educational notebook that walks from loading the California Housing
dataset through data splits, a baseline OLS regression, residual diagnostics,
a feature ablation study, and a final held-out evaluation. It closes with a
few region-based visualizations (north/south, coastal/inland) and a
shareable summary.

This is meant as a **reference baseline** — a clean, reproducible starting
point for regression work on this dataset, not a finished or optimized
model, and not financial or investment advice.

## What's inside

| Section | What it does |
|---|---|
| Setup and data load | Loads `sklearn.datasets.fetch_california_housing` into a single DataFrame |
| 1. Confidence interval | 95% CI for the mean of a chosen feature (default: `MedInc`) |
| 2. Train / Val / Test split | 70% / 15% / 15% split with a fixed random seed |
| 3. Baseline OLS regression | `statsmodels` OLS fit on the training set, with full summary output |
| 4. Residual diagnostics | Residuals-vs-fitted plot, Q-Q plot, residual histogram, Breusch-Pagan test |
| 5. Feature ablation | Drops each feature in turn and measures the change in validation RMSE/MAE |
| 6. Final evaluation | Retrains on train+validation, reports RMSE, MAE, and R² on the held-out test set |
| 7. Region visualizations | KDE of house value by region, income-vs-value scatter, coastal-vs-inland boxplot |
| 8. Shareable summary | Plain-language recap suitable for a README or LinkedIn post |

## Dataset

[California Housing](https://scikit-learn.org/stable/datasets/real_world.html#california-housing-dataset),
loaded via `sklearn.datasets.fetch_california_housing()`. It's fetched
automatically the first time the notebook runs — no manual download needed,
though it does require internet access on that first run (scikit-learn
caches it locally afterward).

## Requirements

```
python >= 3.9
pandas
numpy
scipy
scikit-learn
statsmodels
matplotlib
seaborn
```

Install with:

```bash
pip install pandas numpy scipy scikit-learn statsmodels matplotlib seaborn
```

## How to run

1. Open `california-housing-baseline-regression.ipynb` in Jupyter, JupyterLab, or VS Code.
2. Run all cells top to bottom — every cell is self-contained.
3. To repeat the confidence-interval and visualization steps for a different
   feature, change `feature = 'MedInc'` in Section 1 to any other column
   name (e.g. `'AveRooms'`, `'HouseAge'`).

The notebook is provided **unexecuted** (no saved outputs), so numbers,
plots, and the exact OLS summary will populate when you run it — outputs
are only left blank here so the file stays small and diff-friendly in
version control.

## Notes and caveats

- OLS assumptions (linearity, homoscedasticity, normality of residuals) are
  checked, not assumed — see Section 4. If the Breusch-Pagan test or the
  residual plots suggest violations, treat the coefficient p-values and
  confidence intervals with appropriate caution.
- The feature ablation in Section 5 is a simple leave-one-out study on a
  linear model; it reflects each feature's marginal contribution to *this*
  model's accuracy, not a general causal importance ranking.
- The "north/south" and "coastal/inland" splits in Section 7 use simple,
  fixed latitude/longitude thresholds for illustration — they're a
  convenient way to show regional variation, not an authoritative
  geographic boundary.

## License

Provided for reference and educational use. See the repository root for the
overall license.
