# Equivalence, Pre-Evaluation Lambda, Optimizer, and Cash-Return Sensitivity Outputs

This folder contains Notebook 21 and Notebook 22 outputs for the AURORA-TWETF mechanism-attribution diagnostics.

The manuscript uses the run:

`run_20260722_133503`

This run supports the following manuscript and supplementary results:

- constant-lambda equivalence tests;
- equivalence-margin documentation;
- pre-evaluation constant-lambda calibration;
- pre-evaluation constant-lambda performance;
- optimizer reliability diagnostics;
- constraint-binding diagnostics;
- cash-return and nonzero-risk-free-rate sensitivity.

Key manuscript-supported findings from this run include:

- Dynamic AURORA is practically equivalent to the ex post constant-lambda control across six tested metrics.
- Dynamic AURORA is practically equivalent to the ex post no-probability constant-lambda control across six tested metrics.
- The pre-evaluation calibration selects lambda = 21.0 and reproduces the same qualitative high-cash, cash-cap-bound behavior in a self-contained AURORA-compatible reconstruction.
- Optimizer diagnostics show successful solves and no material constraint violations for the pre-evaluation reconstruction.
- Cash-return sensitivity changes absolute performance levels but does not change the attribution conclusion.

The repository preserves the original run folder to maintain the notebook-generated audit trail.
