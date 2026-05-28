# Healthcare Cost Prediction

Random Forest classifier for hospital billing classification with SHAP interpretability on 60,000 patient records.

---

## Overview

Escalating healthcare costs are a persistent global challenge. This project develops an interpretable machine learning framework to classify patients into low, medium, or high billing cost categories, enabling hospitals to plan resources proactively and insurers to anticipate claims.

The framework combines a full preprocessing pipeline, SMOTE class balancing, Random Forest classification, and SHAP post-hoc explainability to ensure predictions are both accurate and transparent.

Built as part of the M.Sc. Big Data and Business Analytics program at FOM University of Applied Sciences, Essen.

---

## Results

| Metric | Score |
|---|---|
| Model | Random Forest Classifier |
| Accuracy | 84% |
| ROC AUC (macro) | 0.92 |
| Macro F1-Score | 0.81 |
| Precision | 0.83 |
| Recall | 0.81 |

## Class-Wise Performance

| Class | Precision | Recall | F1 |
|---|---|---|---|
| Low Cost | 0.88 | 0.85 | 0.86 |
| Medium Cost | 0.79 | 0.78 | 0.78 |
| High Cost | 0.80 | 0.78 | 0.79 |

---

## Dataset

| Property | Value |
|---|---|
| Total records | 60,000 patient episodes |
| Real records | 48,000 |
| Synthetic records | 12,000 (CTGAN, for class balancing) |
| Features | 16 variables |
| Target | Billing cost category (Low, Medium, High) |
| Privacy | De-identified to GDPR standards |

## Variable Categories

| Category | Variables |
|---|---|
| Demographics | Age, Gender |
| Clinical | Primary Diagnosis (ICD), Procedure (CPT) |
| Administrative | Length of Stay, Discharge Status |
| Financial | Insurance Type, Total Billed Cost (EUR) |

---

## Top Cost Drivers (SHAP Analysis)

| Rank | Feature | Direction |
|---|---|---|
| 1 | Length of Stay | Longer stays strongly predict high cost. Effect plateaus beyond 14 days |
| 2 | Number of Procedures | Steep cost jump between 3 and 5 procedures |
| 3 | Primary Diagnosis Group | Circulatory and respiratory conditions predict higher cost |
| 4 | Insurance Type | Private insurance shifts prediction toward higher cost |
| 5 | Admission Type | Emergency admissions correlate with higher predicted cost |

---

## Key Findings

- Private insurance patients are 28% more likely to fall in the high-cost category
- For patients over 65, the private-public cost gap widens significantly
- Length of stay explains the most variance but shows diminishing returns beyond 14 days
- Medium-cost cases are the hardest to classify due to overlap with both ends
- Administrative variables sometimes outweigh clinical severity in cost prediction

---

## Methodology

```
Raw Data (60,000 records)

Data Cleaning and Preprocessing
Missing value handling, encoding, RobustScaler

Feature Selection
Chi-square tests, ANOVA F-tests, RF importance filtering

Class Balancing
SMOTE on training set to address high-cost class imbalance

Random Forest Classifier
5-fold cross-validation, grid search hyperparameter tuning
n_estimators=200, max_depth=12

SHAP Interpretability
TreeExplainer, global rankings, dependence plots, force plots

Evaluation
Accuracy, ROC AUC, F1, Precision, Recall across cost classes
```

---

## Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3.12 |
| ML Model | Random Forest (Scikit-learn) |
| Explainability | SHAP (TreeExplainer) |
| Imbalance Handling | SMOTE (imbalanced-learn) |
| Preprocessing | Pandas, NumPy, RobustScaler |
| Visualisation | Matplotlib, Seaborn |
| Environment | Jupyter Notebook |

---

## Repository Structure

```
healthcare-cost-prediction/
|
|-- Healthcare_cost_investigation.ipynb
|-- cleaned_healthcare_dataset.csv
|-- eda.py
|-- literature_review_table.xlsx
|-- research_summary.txt
|-- README.md
```

---

## How to Run

```bash
git clone https://github.com/Anurag101723/healthcare-cost-prediction.git
cd healthcare-cost-prediction
pip install pandas numpy scikit-learn shap matplotlib seaborn imbalanced-learn
jupyter notebook Healthcare_cost_investigation.ipynb
```

---

## Author

Anurag Rathore  
anuragakrathore@gmail.com  
linkedin.com/in/anurag1017  
anurag101723.github.io
