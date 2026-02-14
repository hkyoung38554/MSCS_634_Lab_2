# MSCS-634 Lab 2: Classification Using KNN and RNN (Wine Dataset)

## Purpose
This lab evaluates two distance-based classifiers on the sklearn Wine dataset:
1) K-Nearest Neighbors (KNN)
2) Radius Neighbors (RNN)

The goal is to test how parameter choices (k for KNN, radius for RNN) affect classification accuracy and to visualize accuracy trends.

## Dataset
- Source: `sklearn.datasets.load_wine()`
- 178 samples, 13 numeric chemical features
- 3 target classes (wine cultivars)

Train/test split:
- 80% training, 20% testing
- Stratified split with `random_state=42`

## Methods
### KNN parameters tested
- k = 1, 5, 11, 15, 21

### RNN parameters tested
- radius = 350, 400, 450, 500, 550, 600

Accuracy is measured on the test set for each parameter value.

## Key Results (Accuracy Trends)
Using the specified split (stratified 80/20, `random_state=42`):

**KNN Accuracy**
- k=1  → 0.7778
- k=5  → 0.8056
- k=11 → 0.8056
- k=15 → 0.8056
- k=21 → 0.8056

**RNN Accuracy**
- radius=350 → 0.7222
- radius=400 → 0.6944
- radius=450 → 0.6944
- radius=500 → 0.6944
- radius=550 → 0.6667
- radius=600 → 0.6667

Overall, KNN performed better than RNN across the tested parameter ranges in this run.

## Observations
- KNN stabilized after k=5 on this split, suggesting that adding more neighbors did not improve accuracy further with raw features.
- RNN accuracy decreased as radius increased, likely because larger radii include more distant neighbors and weaken class boundary separation.

## Challenges / Decisions
- RNN depends heavily on the scale of features because distances change with feature magnitude.
- The lab followed the required radius values; these radii are large because the raw Wine features include values with large numeric ranges.

## Files
- `Lab2_MSCS634.ipynb`: Notebook containing the full workflow, results tables, and plots.
- `README.md`: Lab overview, results, and observations.
