# Early Hospital Readmission Risk Prediction

Machine learning project to predict whether a patient with diabetes will
be readmitted to the hospital within 30 days.

## Overview

This project uses the UCI Diabetes 130-US Hospitals dataset to analyze
factors associated with early hospital readmission and build a binary
classification model.

The project focuses on:
- Exploratory Data Analysis
- Patient-level train/test splitting
- Feature engineering
- Categorical feature encoding
- Class imbalance handling
- Model comparison
- Classification threshold optimization
- Model interpretation

## Dataset

**Diabetes 130-US Hospitals for Years 1999–2008**

The dataset contains hospital encounters involving diabetic patients
across 130 U.S. hospitals during 1999–2008.

Target:
- `<30` → 1 (early readmission)
- `>30` → 0
- `NO` → 0

## Approach

1. Data cleaning and quality analysis
2. Patient-level train/test split to prevent leakage
3. Exploratory data analysis
4. Feature engineering for healthcare utilization and diagnosis groups
5. Numerical/categorical preprocessing using Scikit-learn
6. Class imbalance handling
7. Model training and comparison
8. Threshold optimization using validation data
9. Final evaluation on an untouched test set
10. Feature importance analysis

## Models

- Logistic Regression
- Random Forest
- XGBoost

## Results

| Model | ROC-AUC | PR-AUC |
|---|---:|---:|
| Logistic Regression | 0.6281 | 0.1850 |
| Random Forest | 0.6348 | 0.1982 |
| XGBoost | 0.6497 | 0.2049 |

Final test performance:

- **ROC-AUC:** 0.6582
- **PR-AUC:** 0.2028
- **Early-readmission recall:** 0.54
- **Early-readmission F1:** 0.26

The classification threshold was selected using the validation set rather
than using the default 0.50 threshold.

## Key Findings

- Previous inpatient utilization was among the strongest predictive signals.
- Previous emergency utilization showed a meaningful relationship with
  early readmission.
- Diagnosis-related features contributed substantially to model predictions.
- Class imbalance created a significant precision-recall trade-off.

## Tech Stack

Python · Pandas · NumPy · Scikit-learn · XGBoost · Matplotlib · Seaborn · Google Colab

## Repository Structure

```text
early-hospital-readmission-prediction/
├── early_hospital_readmission_prediction.ipynb
└── README.md
```

## Dataset Source

**Diabetes 130-US Hospitals for Years 1999–2008**

UCI Machine Learning Repository  
https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008

## Limitations

- The dataset represents hospital encounters from 1999–2008, so the results may not directly represent current healthcare settings.
- The model identifies predictive relationships rather than causal effects.
- The positive class is relatively small, creating a precision-recall trade-off.
- The model would require external validation before any real-world clinical use.
