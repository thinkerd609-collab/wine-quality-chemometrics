# 🍷 Wine Quality Chemometrics — Predictive Quality Control System
 
> **Turning laboratory chemistry into business value using Python, SQL, and Machine Learning**
 
[![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)](https://python.org)
[![SQL](https://img.shields.io/badge/SQL-SQLite-lightgrey?logo=sqlite)](https://sqlite.org)
[![ML](https://img.shields.io/badge/ML-Random%20Forest-green?logo=scikit-learn)](https://scikit-learn.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
 
---
 
## 📌 Project Overview
 
Traditional wine production relies on lab testing *after* bottling — meaning defects are often caught too late, resulting in costly waste. This project builds an **automated, end-to-end predictive quality control pipeline** that flags low-quality batches *during fermentation*, before packaging occurs.
 
As an analytical chemist transitioning into data analytics, I built this to demonstrate how domain expertise in chemistry, combined with modern data tools, creates real operational value.
 
---
 
## 💸 Business Impact
 
| Scenario | Cost |
|---|---|
| ❌ Reactive: defect caught after packaging | $13,000 |
| ✅ Proactive: early fermentation correction | $1,500 |
| 💰 **Savings per deflected incident** | **$11,500** |
 
---
 
## 🛠️ Tech Stack
 
| Tool | Purpose |
|---|---|
| Python (pandas, scikit-learn, statsmodels) | Data cleaning, modeling, regression |
| SQL (SQLite) | Storing predictions, querying results |
| Excel | Reporting and business-readable outputs |
| Jupyter Notebook | Analysis and visualization |
 
---
 
## 🔬 Problem Statement
 
Wine production plants lose significant revenue when defective batches are discovered post-packaging. Traditional manual testing is:
- **Slow** — creates bottlenecks waiting for lab results
- **Late** — defects are often found after packaging
- **Expensive** — reactive waste removal costs ~8.6x more than early correction
This automated pipeline solves all three problems.
 
---
 
## 📊 Statistical Validation
 
Ordinary Least Squares (OLS) regression identified the key chemical drivers of wine quality:
 
| Chemical Factor | P-Value | Conclusion |
|---|---|---|
| Volatile Acidity | 3.62e-40 | Highly significant — reduces quality |
| Alcohol Content | 1.80e-67 | Highly significant — improves quality |
| **Model R²** | **0.3242** | Explains 32% of quality variance |
 
> The extremely low p-values confirm these relationships are not random — they provide management with **mathematical certainty** for operational adjustments.
 
---
 
## ⚙️ Data Pipeline Architecture
 
```
Raw CSV Data
     │
     ▼
[1. Ingestion]
     Reads winequality-red.csv
     Removes duplicates & nulls
     │
     ▼
[2. Feature Engineering]
     Calculates preservative stability ratios
     Scales chemical features
     │
     ▼
[3. Modeling]
     Random Forest Classifier
     Predicts quality: PASS / FAIL
     │
     ▼
[4. Storage]
     Writes predictions to factory_production.db (SQLite)
     Queryable for reporting & dashboards
```
 
---
 
## 📁 Project Structure
 
```
wine-quality-chemometrics/
│
├── Analysis.ipynb                          # Full analysis notebook
├── winequality-red.csv                     # Raw dataset (UCI Wine Quality)
├── factory_production.db                   # SQLite database with predictions
├── Ubaid_Predictive_Quality_Control_Report.pdf  # Business report
└── README.md
```
 
---
 
## 🚀 How to Run
 
```bash
# 1. Clone the repository
git clone https://github.com/ur-chemist/wine-quality-chemometrics.git
cd wine-quality-chemometrics
 
# 2. Install dependencies
pip install pandas scikit-learn statsmodels matplotlib seaborn jupyter
 
# 3. Launch the notebook
jupyter notebook Analysis.ipynb
```
 
---
 
## 📈 Key Findings
 
- **Volatile acidity** is the strongest negative predictor of wine quality
- **Alcohol content** is the strongest positive predictor
- The Random Forest model enables **real-time batch evaluation** during fermentation
- Automated pipeline **eliminates manual spreadsheet errors** in quality tracking
---
 
## 👨‍🔬 About the Author
 
**Ubaid Ur Rahman** — Analytical Chemist turned Data Analyst
 
I hold a Bachelor's in Analytical Chemistry and a Google Data Analytics Certificate. This project bridges my laboratory background with modern data engineering to solve real industrial problems.
 
- 🔗 [LinkedIn](https://www.linkedin.com/in/ubaid-ur-rahman-data-analyst/)
- 📧 Open to data analyst opportunities
---
 
## 📄 License
 
This project is open source under the [MIT License](LICENSE).
 
