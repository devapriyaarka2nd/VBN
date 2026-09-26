# Exact Run Protocol

## Before running
- In Colab: Runtime → Change runtime type → GPU.
- Run Notebook 00 and verify all image/mask folders.
- Do not proceed if any dataset path check fails.

## Proposed model
Run Notebooks 01, 02, 03.
For each dataset, retain:
- split_manifest.csv
- training_history.csv
- validation_threshold_curve.csv
- frozen_threshold.json
- per_image_metrics_validation_threshold.csv
- per_image_metrics_fixed_0p5.csv
- test_predictions.npz
- run_summary.csv
- model weights
- deployment_benchmark.json
- quantitative_xai.csv and XAI arrays

## Domain shift
Run Notebook 04.
Threshold selection must use source validation only.
No target fine-tuning, target early stopping, or target threshold search.

## Ablation
Run Notebook 05.
Every variant must be freshly initialized and trained on the identical split.
Do not infer ablation values from the full model.

## Baselines
Run Notebooks 06–15.
All comparisons must use the same split manifests as the proposed model.

## Statistics
Run Notebook 16 only after all compared models have per-image metrics.
Use the paired Wilcoxon test and Holm correction as implemented.

## Robustness
Run Notebook 17 using the already-trained proposed model and frozen threshold.
Do not retune thresholds after adding perturbations.

## Figures
Run Notebooks 18 and 19 only after the corresponding result files exist.
No notebook creates fake missing values.

## Final audit
Run Notebook 20.
Do not update the manuscript with final numbers until the audit passes the required checks.
