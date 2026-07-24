# Execution Order for AURORA-TWETF Reproducibility Package

This file describes the recommended execution order for reproducing the manuscript results for:

**Diagnosing forecast-to-allocation effects in Taiwan ETF portfolios: cash exposure, uncertainty-aware allocation, and downside-risk control**

The repository contains more than 23 notebooks. Reviewers do **not** need to inspect every notebook manually. The notebook sequence below explains which notebooks generate the key data, tables, figures, and diagnostic outputs used in the manuscript.

---

## 1. Important notes before running

### Data access

Raw market data are downloaded from public yfinance-accessible sources. Raw data redistribution rights may depend on the original providers, so raw data files may not be included in the repository.

The data-ingestion notebooks reconstruct the required price panels and return matrices from public sources.

### Evaluation window terminology

The manuscript refers to the main test period as the:

```text
319-trading-day aligned out-of-sample evaluation window
