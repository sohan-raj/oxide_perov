# Oxide Perovskite — Notebook Work Summary

This repository contains a Jupyter notebook (`notebook/dataset_preparation.ipynb`) used to prepare a dataset of oxide/perovskite compounds and train several regression models. Below is a short summary of what was done recently.

- Installed `ipykernel` in the local conda environment so the notebook can be run as a kernel.
- Generated a `requirements.txt` listing the main Python dependencies (pandas, numpy, scikit-learn, xgboost, deap, scipy, seaborn, matplotlib).
- Added imputation to the preprocessing pipeline: `SimpleImputer(strategy='mean')` is used to fill missing feature values; the imputed DataFrame replaces `df` before train/test split.
- Trained three models (XGBoost, Random Forest, SVR) with hyperparameter tuning (genetic algorithm via `deap`).
- Persisted the final models using `joblib` into the `model/` directory:
  - `model/xgbr_model.joblib`
  - `model/rf_model.joblib`
  - `model/svr_model.joblib`

Notes:
- A small notebook cleanup was made (removed a stray `sampleImputer` token and inserted the imputation cell).
- The notebook contains the full preprocessing, feature-engineering (element property maps), model tuning, evaluation, and model-saving steps.

Next steps (optional):
- Execute the final notebook cells to regenerate the saved `.joblib` files if you re-run training.
- Freeze or pin exact dependency versions in `requirements.txt` for reproducible installs.

Location pointers:
- Notebook: `notebook/dataset_preparation.ipynb`
- Requirements: `requirements.txt`
- Saved models directory: `model/`

Short and sweet — run the notebook to reproduce the preprocessing and model training steps.
