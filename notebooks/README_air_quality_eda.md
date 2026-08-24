# UCI Air Quality EDA — Reader Edition

This repository is an educational walkthrough of **Exploratory Data Analysis (EDA)** using the UCI Air Quality dataset.

The notebook is written for a reader learning how analytical reasoning develops from raw data. It treats EDA as a process of reducing uncertainty rather than a checklist of visualizations.

## What the notebook teaches

The analysis follows one reasoning chain:

**Context → Structure → Data quality → Cleaning assumptions → Distributions → Relationships → Time → Stability → Synthesis**

Each section contains:

- the EDA question being answered;
- why that question matters;
- commented Python code;
- explanations of less-obvious syntax;
- interpretation of the resulting evidence;
- boundaries on what the evidence supports.

Comments in code are labelled where useful as:

- `EDA ACTION` — the analytical operation;
- `SYNTAX` — how a Python expression works;
- `REASONING` — why the operation belongs in the analysis.

## Dataset

The UCI Air Quality dataset contains hourly environmental observations from an Italian city, including certified reference measurements, metal-oxide sensor responses, temperature, and humidity.

The source notebook loaded 9,357 rows and 15 columns. A documented `-200` sentinel represents missing measurements.

## Main educational findings

The notebook demonstrates that:

- a dataframe can report no nulls while still containing encoded missing values;
- missingness can differ drastically across variables;
- imputation changes distributional shape and variance;
- means and medians can tell different stories in skewed data;
- statistical outliers are not automatically data errors;
- correlation is an association summary rather than a causal conclusion;
- subsetting the data changes the correlation question;
- weekday and weekend NO₂ distributions differ in the source sample;
- hourly NO₂ has a recurring daily profile;
- autocorrelation reveals short-term persistence and a strong daily cycle;
- rolling statistics test whether relationships remain stable through time.

## Responsible interpretation

The notebook distinguishes three layers throughout:

1. **Observation** — what the data or graph directly shows.
2. **Interpretation** — a plausible meaning of that pattern.
3. **Limitation** — what cannot be concluded from the evidence alone.

Dataset-relative high-concentration events are deliberately described as unusual observations, not as regulatory or health thresholds.

## Files

- `air_quality_eda.ipynb` — complete reader-facing educational notebook.

## Source

Vito, S. (2008). *Air Quality* [Dataset]. UCI Machine Learning Repository.  
DOI: https://doi.org/10.24432/C59K5F