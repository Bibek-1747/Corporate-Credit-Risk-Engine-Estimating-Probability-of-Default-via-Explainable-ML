# 🏦 Corporate Credit Risk Engine
### Probability of Default (PD) Modelling — Basel III Aligned

A portfolio-grade, end-to-end PD modelling project built for quant/credit risk roles.

---

## 📁 Project Structure

```
.
├── corporate_credit_risk_engine.ipynb   ← Main notebook (all 7 steps)
├── requirements.txt
├── data.csv                             ← TEJ dataset (download from Kaggle)
├── plots/                               ← Auto-created; all saved figures
│   ├── 01_class_imbalance.png
│   ├── 02_ratio_distributions.png
│   ├── 03_correlation_heatmap.png
│   ├── 04_smote_balance.png
│   ├── 05_model_evaluation_curves.png
│   ├── 06_confusion_matrices.png
│   ├── 07_shap_beeswarm.png
│   ├── 08_shap_bar.png
│   ├── 09_shap_waterfall.png
│   ├── 10_pd_calibration.png
│   └── 11_final_comparison.png
└── outputs/                             ← Auto-created; all exported CSVs
    ├── model_comparison.csv
    ├── feature_importance.csv
    └── selected_features.csv
```

---

## 🔢 Pipeline Overview

| Step | Description | Key Technique |
|------|-------------|---------------|
| 1 | Data Ingestion & EDA | Missing value audit, class imbalance plots |
| 2 | Feature Engineering | Winsorisation, VIF filter (threshold=10), Basel III categorisation |
| 3 | Class Imbalance | SMOTE on training set only |
| 4 | Model Training | LR baseline, RF + XGB with RandomizedSearchCV |
| 5 | SHAP Explainability | Beeswarm, bar chart, waterfall plots |
| 6 | PD Calibration | Platt Scaling, reliability diagram, Brier Score |
| 7 | Final Summary | Multi-metric comparison table + CSV export |

---

## 📊 Evaluation Metrics

| Metric | Why it matters in credit risk |
|--------|-------------------------------|
| ROC-AUC | Discriminatory power — can the model rank defaulters above non-defaulters? |
| F1 (minority) | Balance of precision/recall on the bankrupt class |
| PR-AUC | More informative than ROC-AUC under severe class imbalance |
| KS Statistic | Regulatory standard — max separation between PD distributions |
| Brier Score | Calibration quality — how close are predicted PDs to observed rates? |

---

## 🎓 Basel III / IRB Context

Under **Basel III IRB**, banks use internal PD models to compute:

```
Risk-Weighted Assets (RWA) = f(PD, LGD, EAD, Maturity)
Minimum Capital = 8% × RWA
```

This engine produces **well-calibrated PD estimates** that could feed directly
into an IRB rating system. Key regulatory alignment:
- **Explainability**: SHAP satisfies SR 11-7 / ECB TRIM model documentation
- **Calibration**: Platt scaling corrects score-to-probability drift
- **Feature selection**: VIF analysis prevents unstable coefficient estimates
- **Validation**: KS Statistic and PR-AUC match industry validation frameworks

---

## 🛠 Dependencies

Python 3.9+ | pandas | numpy | scikit-learn | xgboost | shap | imbalanced-learn | statsmodels | matplotlib | seaborn | scipy

---
