# Asteroid Hazard Classifier

NASA NEO (Near-Earth Object) data diye asteroid hazardous naki na classify kora — a binary tabular classification project with imbalanced classes.

## Dataset

- **Source:** Kaggle (NASA Asteroids Classification)
- **Size:** 4,687 asteroids × 40 columns (reduced to 16 features after cleaning)
- **Target:** Hazardous (True/False)

## EDA Summary

- Target is imbalanced: 83.9% Not Hazardous, 16.1% Hazardous.
- No missing values in the raw dataset.
- Identified and removed duplicate-unit columns (diameter/velocity/distance measured in km, miles, feet — kept only one unit per measurement).
- Removed constant columns (Orbiting Body, Equinox — no variation).
- Correlation heatmap revealed multiple orbit-related features with >0.9 correlation (Semi Major Axis, Orbital Period, Aphelion Dist, etc.) — kept one representative feature per group.
- Final feature set: 16 columns.

## Status

✅ EDA and feature selection complete
🚧 Next: preprocessing, train/test split, and model training (with focus on precision/recall due to class imbalance)

## Tech Stack

pandas, numpy, scikit-learn, matplotlib, seaborn
