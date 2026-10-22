# Aquatic-Ecotoxicity-Risk-Screener
A cheminformatics and machine learning pipeline to predict acute aquatic toxicity ($pLC_{50}$) from molecular structures using Quantitative Structure-Activity Relationship (QSAR) modeling.

## Overview
This project evaluates the environmental toxicity of organic pollutants by mapping molecular properties to experimental aquatic toxicity endpoints. It demonstrates an end-to-end workflow from SMILES parsing and molecular descriptor extraction to supervised machine learning and rigorous cross-validation.

## Methodology & Workflow
- **Feature Engineering:** Extracted key physicochemical descriptors (Molecular Weight, LogP, TPSA, H-bond donors, and H-bond acceptors) from SMILES strings using RDKit.
- **Model Training:** Built a `RandomForestRegressor` via Scikit-Learn to model the relationship between chemical topology and toxicity.
- **Validation:** Utilized Leave-One-Out Cross-Validation (LOOCV) to ensure robust performance evaluation on a benchmark dataset of organic pollutants ($N=20$).
  - **LOOCV $R^2$ Score:** 0.589
  - **LOOCV RMSE:** 0.748

## Tech Stack
- **Language:** Python
- **Cheminformatics:** [RDKit](Descriptor calculation)
- **Machine Learning:** [Scikit-Learn](RandomForestRegressor, cross-validation metrics)
- **Data Manipulation:** Pandas, NumPy
