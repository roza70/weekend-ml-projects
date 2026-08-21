# Mars Orbital Landmark Classifier

Classifying Mars surface landmarks (craters, dunes, slope streaks, etc.) from HiRISE orbital images using a CNN. NASA JPL trained a real deployed tool on this exact dataset.

## Dataset
- **Source:** Zenodo (Mars orbital image HiRISE labeled dataset v3.2)
- **Size:** 64,947 grayscale images, 227×227 pixels
- **Classes:** 8 categories — other, crater, dark dune, slope streak, bright dune, impact ejecta, swiss cheese, spider
- **Split:** Pre-defined train/val/test split provided by dataset creators (to avoid data leakage from augmented image variants)

## EDA Summary
- Found 2,863 duplicate rows in the label file; removed them so row count matches the actual 64,947 image files.
- Severe class imbalance: "other" class makes up 81.2% of the data; the 7 landmark classes together make up the remaining ~19%.
- Verified all 8 classes visually — craters, dunes, slope streaks, spider patterns, and swiss cheese terrain all match expected geological features.

## Approach
- Keeping all 8 classes (not dropping "other") and handling imbalance using class weights during training.
- Using a stratified subset of the training data to manage memory (full dataset too large to load as float32 arrays).

## Status
✅ EDA complete
🚧 Next: preprocessing, CNN model training

## Tech Stack
tensorflow/keras, numpy, pandas, matplotlib, scikit-learn