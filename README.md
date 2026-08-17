# Notebooks & Reference Code

A public collection of notebooks and small code projects I'm sharing as
**reference material — for learning, reuse, and demonstration purposes.**

Everything here is meant to be readable end-to-end: each notebook loads its
own data (usually a well-known public dataset), documents *why* each step
happens alongside the code that does it, and ends with a short, shareable
summary you can reuse in a README, blog post, or LinkedIn write-up.

## What you'll find here

- **Self-contained notebooks** — each one runs top to bottom without
  external setup beyond the listed Python packages.
- **A short "why" note after every major step** — the goal is to make the
  reasoning as visible as the code, not just hand you a working script.
- **Baselines, not finished products** — these are meant as clean starting
  points to build on, not production-ready or fully tuned models.

## Repository structure

Each notebook lives in its own folder (or at the root, for smaller
projects) alongside a notebook-specific `README.md` that covers what it
does, the data it uses, and how to run it. This file is the repository's
front page — start with a notebook's own README for details on that
project.

```
.
├── README.md                                      <- you are here
└── california-housing-baseline-regression/
    ├── california-housing-baseline-regression.ipynb
    └── README.md
```

## How to use this repo

1. Pick a notebook and open its own `README.md` for a summary of what it
   covers and what packages it needs.
2. Open the `.ipynb` file in Jupyter, JupyterLab, or VS Code and run it top
   to bottom.
3. Adapt the code for your own data or question — that's the intent.

## Scope and disclaimer

- This repo is for **reference and educational purposes**. Nothing here —
  including any notebook that touches financial, housing, or investment
  data — is financial, investment, or professional advice.
- Notebooks favor clarity and reproducibility over performance. Where a
  notebook makes a modeling choice (a train/val/test split ratio, a fixed
  random seed, a simplified regional cutoff, etc.), it's called out in that
  notebook's markdown so you can see the assumption and change it.

## Contributing / feedback

This is primarily a personal reference collection, but issues and PRs
pointing out errors, unclear explanations, or suggested additions are
welcome.

## License

See individual notebooks for any dataset-specific licensing notes. Unless
stated otherwise, code in this repository is provided for reference and
educational use.
