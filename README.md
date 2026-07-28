# AURORA-TWETF: Forecast-to-Allocation Diagnostics for Taiwan ETF Portfolios

This repository contains the reproducibility package for the manuscript:

**Diagnosing forecast-to-allocation attribution in Taiwan ETF portfolios: cash exposure, risk aversion, and downside-risk control**


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

AURORA_TWETF/
├── README.md
├── EXECUTION_ORDER.md
├── ENVIRONMENT.md
├── requirements.txt
├── requirements_project_versions.txt
├── requirements_colab_full.txt
│
├── notebooks/
│   ├── 01_*.ipynb
│   ├── 02_*.ipynb
│   ├── ...
│   ├── 21_equivalence_pre_eval_lambda_optimizer_diagnostics.ipynb
│   ├── 22_cash_return_risk_free_sensitivity.ipynb
│   ├── 23_canonical_passive_benchmark_reconciliation.ipynb
│   ├── 24_bridge_main_source_aware_and_diagnostic_AURORA.ipynb
│   ├── 25_probability_fold_source_map.ipynb
│   ├── 26_fold_rule_sensitivity.ipynb
│   └── 27_oracle_probability_positive_control.ipynb
│
├── data/
│   ├── raw_yfinance/
│   ├── modeling/
│   ├── panels/
│   └── processed/
│
├── outputs/
│   └── AURORA_TWETF/
│       ├── canonical_passive_benchmarks/
│       │   ├── README.md
│       │   └── run_20260723_035525/
│       │
│       ├── equivalence_lambda_cash_sensitivity/
│       │   ├── README.md
│       │   └── run_20260722_133503/
│       │
│       ├── bridge_main_vs_diagnostic_AURORA/
│       │   └── run_20260725_003004/
│       │       ├── tables/
│       │       ├── diagnostics/
│       │       └── reports/
│       │
│       ├── probability_fold_source_map/
│       │   └── run_20260725_005830/
│       │       ├── tables/
│       │       ├── diagnostics/
│       │       └── reports/
│       │
│       ├── fold_rule_sensitivity/
│       │   └── run_<RUN_ID>/
│       │       ├── tables/
│       │       │   ├── table_S38_fold_rule_sensitivity_design.csv
│       │       │   ├── table_S39_fold_rule_probability_sensitivity.csv
│       │       │   ├── table_S40_fold_rule_portfolio_sensitivity.csv
│       │       │   ├── table_S41_fold_rule_source_composition.csv
│       │       │   └── table_S42_fold_rule_difference_vs_latest.csv
│       │       ├── diagnostics/
│       │       │   ├── fold_rule_selected_probability_map.csv
│       │       │   ├── fold_rule_probability_sensitivity_full.csv
│       │       │   ├── fold_rule_portfolio_sensitivity_full.csv
│       │       │   ├── fold_rule_source_composition_full.csv
│       │       │   ├── fold_rule_difference_vs_latest_full.csv
│       │       │   └── fold_rule_optimizer_diagnostics.csv
│       │       ├── returns/
│       │       │   ├── fold_rule_sensitivity_returns.parquet
│       │       │   └── fold_rule_sensitivity_returns.csv
│       │       ├── weights/
│       │       │   ├── fold_rule_sensitivity_weights.parquet
│       │       │   └── fold_rule_sensitivity_weights.csv
│       │       └── reports/
│       │           ├── NOTEBOOK26_fold_rule_sensitivity_validation_report.json
│       │           └── NOTEBOOK26_file_manifest_SHA256.csv
│       │
│       ├── oracle_probability_positive_control/
│       │   └── run_20260728_005644/
│       │       ├── tables/
│       │       │   ├── table_S35_oracle_positive_control_design.csv
│       │       │   ├── table_S36_oracle_positive_control_performance.csv
│       │       │   ├── table_S36b_oracle_positive_control_ordered_compact.csv
│       │       │   ├── table_S37_oracle_ordered_vs_shuffled_comparison.csv
│       │       │   └── notebook27_oracle_positive_control_interpretation_helper.csv
│       │       ├── diagnostics/
│       │       │   ├── oracle_positive_control_diagnostics.csv
│       │       │   ├── oracle_probability_design_full.csv
│       │       │   ├── oracle_positive_control_performance_full.csv
│       │       │   └── oracle_ordered_vs_shuffled_full.csv
│       │       ├── returns/
│       │       │   ├── oracle_positive_control_returns.parquet
│       │       │   └── oracle_positive_control_returns.csv
│       │       ├── weights/
│       │       │   ├── oracle_positive_control_weights.parquet
│       │       │   └── oracle_positive_control_weights.csv
│       │       └── reports/
│       │           ├── NOTEBOOK27_oracle_positive_control_validation_report.json
│       │           └── NOTEBOOK27_file_manifest_SHA256.csv
│       │
│       ├── tables/
│       │   ├── table_S5b_duplicate_probability_handling.csv
│       │   ├── table_S25b_full_equivalence_test_results.csv
│       │   ├── table_S32_main_vs_diagnostic_AURORA_bridge_rounded.csv
│       │   ├── table_S33_ROMA_P4_regime_template_specification.csv
│       │   ├── table_S34_AURORA_moment_optimizer_specification.csv
│       │   ├── table_S35_oracle_positive_control_design.csv
│       │   ├── table_S36_oracle_positive_control_performance.csv
│       │   ├── table_S36b_oracle_positive_control_ordered_compact.csv
│       │   ├── table_S37_oracle_ordered_vs_shuffled_comparison.csv
│       │   ├── table_S38_fold_rule_sensitivity_design.csv
│       │   ├── table_S39_fold_rule_probability_sensitivity.csv
│       │   ├── table_S40_fold_rule_portfolio_sensitivity.csv
│       │   ├── table_S41_fold_rule_source_composition.csv
│       │   └── table_S42_fold_rule_difference_vs_latest.csv
│       │
│       ├── diagnostics/
│       │   ├── main_vs_diagnostic_AURORA_bridge_daily.csv
│       │   ├── probability_fold_source_map.csv
│       │   ├── fold_rule_selected_probability_map.csv
│       │   ├── fold_rule_sensitivity_returns.csv
│       │   ├── fold_rule_sensitivity_weights.csv
│       │   ├── oracle_positive_control_returns.csv
│       │   ├── oracle_positive_control_weights.csv
│       │   └── oracle_ordered_vs_shuffled_full.csv
│       │
│       ├── reports/
│       │   ├── NOTEBOOK24_bridge_validation_report_20260725_003004.json
│       │   ├── NOTEBOOK25_probability_fold_source_map_validation_report_20260725_005830.json
│       │   ├── NOTEBOOK26_fold_rule_sensitivity_validation_report_<RUN_ID>.json
│       │   ├── NOTEBOOK26_file_manifest_SHA256_<RUN_ID>.csv
│       │   ├── NOTEBOOK27_oracle_positive_control_validation_report_20260728_005644.json
│       │   └── NOTEBOOK27_file_manifest_SHA256_20260728_005644.csv
│       │
│       ├── figures/
│       ├── returns/
│       └── weights/
│
├── reproducibility/
│   ├── README.md
│   ├── OUTPUT_MANIFEST.csv
│   ├── pipeline_metadata_AURORA_TWETF.csv
│   ├── random_seeds.md
│   └── validation_reports/
│       ├── NOTEBOOK24_bridge_validation_report_20260725_003004.json
│       ├── NOTEBOOK25_probability_fold_source_map_validation_report_20260725_005830.json
│       ├── NOTEBOOK26_fold_rule_sensitivity_validation_report_<RUN_ID>.json
│       └── NOTEBOOK27_oracle_positive_control_validation_report_20260728_005644.json
│
└── manuscript/
    ├── README.md
    ├── tables/
    ├── figures/
    │   ├── figure_1_framework.png
    │   ├── figure_2_drawdown_comparison.png
    │   └── figure_3_mechanism_attribution_improved.png
    └── supplementary_tables/
        ├── table_S5b_duplicate_probability_handling.csv
        ├── table_S25b_full_equivalence_test_results.csv
        ├── table_S32_main_vs_diagnostic_AURORA_bridge_rounded.csv
        ├── table_S33_ROMA_P4_regime_template_specification.csv
        ├── table_S34_AURORA_moment_optimizer_specification.csv
        ├── table_S35_oracle_positive_control_design.csv
        ├── table_S36_oracle_positive_control_ordered_compact.csv
        ├── table_S37_oracle_ordered_vs_shuffled_comparison.csv
        ├── table_S38_fold_rule_sensitivity_design.csv
        ├── table_S39_fold_rule_probability_sensitivity.csv
        ├── table_S40_fold_rule_portfolio_sensitivity.csv
        ├── table_S41_fold_rule_source_composition.csv
        └── table_S42_fold_rule_difference_vs_latest.csv
