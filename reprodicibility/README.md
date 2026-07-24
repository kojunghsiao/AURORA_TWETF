# Reproducibility Folder

This folder contains machine-readable files used to audit the AURORA-TWETF reproducibility package.

## Files

- OUTPUT_MANIFEST.csv: lists repository files and output files with relative paths, sizes, modification times, and SHA256 hashes.
- pipeline_metadata_AURORA_TWETF.csv: documents operational differences among the main source-aware comparison, mechanism-control diagnostics, constant-lambda attribution, pre-evaluation reconstruction, cash-return sensitivity, canonical passive benchmarks, and feature-observability audit pipelines.
- random_seeds.md: summarizes random seeds and deterministic components.
- validation_reports/: contains notebook-generated validation reports where available.

## Notes

The manuscript uses “aligned out-of-sample evaluation window” for the main 319-trading-day evaluation period from 2024-11-27 to 2026-03-25. Some repository outputs use the label “strict-test” for the same evaluation period.

The diagnostic pipelines are not interchangeable with the main source-aware comparison. See pipeline_metadata_AURORA_TWETF.csv for claim use and pipeline-specific assumptions.
