# Random Seeds

This file summarizes random seeds used in the AURORA-TWETF reproducibility package.

| Component | Seed | Notes |
|---|---:|---|
| Paired circular block bootstrap | 20260722 | Used for central bootstrap and equivalence diagnostics where applicable |
| Notebook 21 equivalence bootstrap | 20260722 | Base seed; comparison-specific offsets may be used |
| Shuffled-probability controls | See notebook output | Seed-level shuffled outputs are repository-only diagnostics |
| Forecasting models | See individual notebooks | Model-specific seeds are set in the corresponding forecasting notebooks |
| Train/validation/test split construction | Deterministic chronological split | No random split is used |
| Canonical passive benchmarks | Deterministic | No random seed required |
| Feature-observability audit | Deterministic | No random seed required |

All stochastic procedures are diagnostic and reproducibility-oriented. Validation reports and notebook cells document exact seed settings where applicable.
