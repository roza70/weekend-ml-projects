# Kepler Exoplanet Classifier

NASA Kepler telescope er data diye planet candidate vs false-positive classify kora — a binary tabular classification project.

## Dataset

- **Source:** NASA Exoplanet Archive (Cumulative KOI Table)
- **Size:** 9,564 rows × 49 columns
- **Target:** `koi_pdisposition` (CANDIDATE vs FALSE POSITIVE)

## EDA Summary

- Target classes are nearly balanced (~50% CANDIDATE, ~51% FALSE POSITIVE) — no class imbalance issue here, unlike typical anomaly-detection datasets.
- Two columns (`koi_teq_err1`, `koi_teq_err2`) were completely empty and dropped.
- Identifier/text columns (`kepid`, `kepoi_name`, `kepler_name`, `koi_tce_delivname`) were dropped — not useful for prediction.
- Remaining missing values (~5% in error/uncertainty columns) were filled using median imputation.
- Correlation heatmap showed no strongly redundant features (highest correlation ~0.58), so all key features were retained.
- Target label encoded as binary: CANDIDATE = 1, FALSE POSITIVE = 0.

## Status

✅ EDA complete — moving to train/test split and model training next.

## Tech Stack

pandas, numpy, scikit-learn, matplotlib, seaborn
