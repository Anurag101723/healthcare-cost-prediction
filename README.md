# 🏥 Healthcare Cost Prediction

> Predicting hospital billing costs using Random Forest and SHAP interpretability on 60,000 patient records.

![Python](https://img.shields.io/badge/Python-3.12-blue?style=flat&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.4-orange?style=flat&logo=scikit-learn&logoColor=white)
![SHAP](https://img.shields.io/badge/SHAP-0.44-red?style=flat)
![Status](https://img.shields.io/badge/Status-Complete-green?style=flat)

---

## 📌 Overview

Escalating healthcare costs are a global challenge. This project develops an **interpretable machine learning framework** to predict whether a patient will fall into a **low, medium, or high cost** billing category — enabling hospitals to plan resources proactively and insurers to anticipate claims.

Built as part of the M.Sc. Big Data & Business Analytics program at **FOM University of Applied Sciences, Essen**.

---

## 🎯 Key Results

| Metric | Score |
|---|---|
| Accuracy | **84%** |
| ROC AUC (macro) | **0.92** |
| Macro F1-Score | **0.81** |
| Precision | **0.83** |
| Recall | **0.81** |

---

## 📊 Dataset

- **Total records:** 60,000 patient episodes
- **Real records:** 48,000 (from tertiary-care hospital administrative systems)
- **Synthetic records:** 12,000 (generated via CTGAN to correct class imbalance)
- **Features:** 16 variables across 4 categories

| Category | Variables |
|---|---|
| Demographics | Age, Gender |
| Clinical | Primary Diagnosis (ICD), Procedure (CPT) |
| Administrative | Length of Stay, Discharge Status |
| Financial | Insurance Type, Total Billed Cost (EUR) |

---

## 🛠️ Tech Stack

- **Language:** Python 3.12
- **ML Model:** Random Forest Classifier (Scikit-learn)
- **Interpretability:** SHAP (TreeExplainer)
- **Preprocessing:** Pandas, NumPy, RobustScaler, SMOTE
- **Visualisation:** Matplotlib, Seaborn
- **Environment:** Jupyter Notebook

---

## 🔍 Methodology

```
Raw Data (60k records)
       ↓
Data Cleaning & Preprocessing
(missing values, encoding, scaling, SMOTE balancing)
       ↓
Feature Selection
(Chi-square, ANOVA F-test, RF importance)
       ↓
Random Forest Classifier
(5-fold CV, grid search hyperparameter tuning)
       ↓
SHAP Interpretability
(global rankings, dependence plots, force plots)
       ↓
Results & Insights
```

---

## 🔑 Key Findings

- **Length of Stay (LOS)** is the strongest cost predictor — but effect plateaus beyond 14 days
- **Procedure count** shows steep cost jumps between 3–5 procedures
- **Insurance type** ranks 4th in importance — private insurance patients are **28% more likely** to fall in the high-cost category
- **Elderly patients (>65)** with private insurance show the largest cost gap vs public insurance
- **Oncology and circulatory conditions** dominate high-cost cases

---

## 📁 Repository Structure

```
healthcare-cost-prediction/
│
├── Healthcare_cost_investigation.ipynb   # Main analysis notebook
├── README.md                             # Project documentation
```

---

## 🚀 How to Run

1. Clone the repository
```bash
git clone https://github.com/Anurag101723/healthcare-cost-prediction.git
cd healthcare-cost-prediction
```

2. Install dependencies
```bash
pip install pandas numpy scikit-learn shap matplotlib seaborn imbalanced-learn
```

3. Open the notebook
```bash
jupyter notebook Healthcare_cost_investigation.ipynb
```

---

## 👤 Author

**Anurag Rathore**  
M.Sc. Big Data & Business Analytics — FOM University of Applied Sciences  
📧 anuragakrathore@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/anurag1017) · [Portfolio](https://Anurag101723.github.io)
