# Aquatic Ecotoxicity Risk Screener

A Python-based QSPR (Quantitative Structure-Property Relationship) pipeline designed to predict the acute aquatic toxicity ($pLC_{50}$) of organic pollutants directly from their molecular structures.

## Overview
Evaluating the environmental risks of chemical compounds often requires time-intensive laboratory bioassays. In this self-directed project, I built a predictive workflow to estimate aquatic toxicity endpoints from chemical topology using open-source cheminformatics and machine learning tools.

## Methodology & Workflow
* **Descriptor Extraction:** Parsed SMILES strings using **RDKit** to compute key physicochemical descriptors relevant to environmental fate and membrane permeability—specifically Molecular Weight, LogP, Topological Polar Surface Area (TPSA), hydrogen-bond donors, and hydrogen-bond acceptors.
* **Model Training:** Trained a `RandomForestRegressor` in **Scikit-Learn** to map these molecular descriptors against experimental $pLC_{50}$ values.
* **Validation & Feature Analysis:** Evaluated model performance on a benchmark dataset of organic pollutants ($N = 20$) using **Leave-One-Out Cross-Validation (LOOCV)** and examined feature importance to identify which structural properties drove toxicity predictions:
  * **LOOCV $R^2$ Score:** 0.589
  * **LOOCV RMSE:** 0.748

## Tools & Libraries
* **Language:** Python
* **Cheminformatics:** RDKit
* **Machine Learning:** Scikit-Learn
* **Data Handling:** Pandas, NumPy
