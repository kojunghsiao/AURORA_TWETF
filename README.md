# AURORA-TWETF: Forecast-to-Allocation Diagnostics for Taiwan ETF Portfolios

This repository contains the reproducibility package for the manuscript:

**Diagnosing forecast-to-allocation effects in Taiwan ETF portfolios: cash exposure, uncertainty-aware allocation, and downside-risk control**

Authors: Ko-Jung Hsiao and Chien-Chih Hsiao  
Affiliation: Department of Electrical Engineering, Yuan Ze University, Taiwan

Repository DOI / permanent URL: **Hsiao, K.-J. & Hsiao, C.-C. AURORA-TWETF reproducibility package v1.0.1. Zenodo. https://doi.org/10.5281/zenodo.21535796 (2026).**

---

## 1. Project overview

AURORA-TWETF is a diagnostic research framework for studying how noisy regime-probability forecasts are transformed into ETF and cash portfolio weights.

The empirical study focuses on semiconductor-sensitive Taiwan ETF allocation using four Taiwan ETFs:

- 0050
- 006208
- 00692
- 00881
- cash

The main conclusion is diagnostic rather than prescriptive:

> The selected AURORA specification improves Sharpe, Sortino, and maximum-drawdown behavior relative to the ROMA-P4 baseline in the aligned out-of-sample evaluation window, but mechanism-control, defensive-control, constant-lambda, equivalence, and cash-return diagnostics show that the observed downside-risk behavior is driven mainly by persistent cash exposure, cash-cap binding, and elevated effective risk aversion rather than separable dynamic probability-timing value.

This repository is provided for reproducibility and reviewer audit. It is **not financial advice** and does not provide investment recommendations.

---

## 2. What this repository contains

This repository contains:

- data-download and preprocessing notebooks;
- feature and label construction notebooks;
- purged walk-forward forecasting notebooks;
- AURORA allocation notebooks;
- ROMA baseline and source-aware comparison notebooks;
- bootstrap inference and implementation-sensitivity notebooks;
- mechanism-control, defensive-control, and constant-lambda attribution notebooks;
- probability-skill baseline diagnostics;
- feature-observability audit outputs;
- canonical passive benchmark construction;
- cash-return and nonzero-risk-free-rate sensitivity;
- processed tables, figures, return matrices, weights, reports, and metadata.

Raw market data are downloaded from public yfinance-accessible sources by the data-ingestion notebooks and are not redistributed unless permitted by the original providers.

---

## 3. Repository structure

```text
AURORA_TWETF/
├── README.md
├── EXECUTION_ORDER.md
├── ENVIRONMENT.md
├── requirements.txt
├── notebooks/
│   ├── 01_*.ipynb
│   ├── 02_*.ipynb
│   ├── ...
│   ├── 21_equivalence_pre_eval_lambda_optimizer_diagnostics.ipynb
│   ├── 22_cash_return_risk_free_sensitivity.ipynb
│   └── 23_canonical_passive_benchmark_reconciliation.ipynb
├── data/
│   ├── raw_yfinance/
│   ├── modeling/
│   └── processed/
├── outputs/
│   ├── tables/
│   ├── figures/
│   ├── reports/
│   ├── returns/
│   ├── weights/
│   └── diagnostics/
├── reproducibility/
│   ├── OUTPUT_MANIFEST.csv
│   ├── pipeline_metadata_AURORA_TWETF.csv
│   ├── random_seeds.md
│   └── validation_reports/
└── manuscript/
    ├── tables/
    ├── figures/
    └── supplementary_tables/
