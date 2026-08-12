<div align="center">

# 🍷 Wine Quality Chemometrics

> **Applying chemometric methods and machine learning to predict wine quality from physicochemical measurements**

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![SQLite](https://img.shields.io/badge/SQLite-Database-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)
[![Pandas](https://img.shields.io/badge/Pandas-Data-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)

![Status](https://img.shields.io/badge/Status-Portfolio%20Project-brightgreen?style=flat-square)
![Dataset](https://img.shields.io/badge/Dataset-UCI%20Wine%20Quality-blue?style=flat-square)
![Samples](https://img.shields.io/badge/Samples-1%2C599%20rows-orange?style=flat-square)

</div>

---

## 📌 Overview

This project applies **chemometric methods** to the [UCI Wine Quality dataset](https://archive.ics.uci.edu/dataset/186/wine+quality) to explore how physicochemical measurements predict sensory quality scores.

The focus was not on building a perfect model — it was on practicing the **full analytical workflow** a QA data analyst would run in a real industrial setting:

```
Raw Data → Cleaning → EDA → Statistical Modeling → ML Classification → SQL Storage → Report
```

| Property | Detail |
|---|---|
| 📂 Dataset | UCI Wine Quality — Red Wine |
| 📊 Rows | 1,599 samples |
| 🧪 Features | 11 physicochemical variables |
| 🎯 Target | Quality score (0–10, human-rated) |

---

## 📁 Project Structure

```
wine-quality-chemometrics/
│
├── 📓 Analysis.ipynb                            # Main notebook: EDA, regression, modeling
├── 📄 winequality-red.csv                       # Raw dataset (UCI)
├── 🗄️  factory_production.db                    # SQLite database — model predictions
├── 📋 Predictive_Quality_Control_Report.pdf     # Written QC-style analytical report
└── 📘 README.md
```

---

## 🔬 Methodology

### 1️⃣ Data Cleaning & Ingestion
- Loaded raw CSV and removed duplicate records
- Checked for nulls and outliers across all 11 chemical features
- Prepared a clean dataframe ready for analysis

### 2️⃣ Exploratory Data Analysis (EDA)
- Correlation matrix across all physicochemical variables
- Distribution analysis of key features (volatile acidity, alcohol, sulphates)
- Identified which variables show the strongest relationship with quality scores

### 3️⃣ Statistical Modeling — OLS Regression

Ordinary Least Squares regression to identify the **chemical drivers of quality**:

| Variable | Coefficient Direction | P-Value | Significance |
|---|---|---|---|
| Volatile Acidity | Negative ↓ | 3.62e-40 | ✅ Highly significant |
| Alcohol Content | Positive ↑ | 1.80e-67 | ✅ Highly significant |
| **R² (overall model)** | — | — | **0.3242** |

> ⚠️ **Honest note on R²:** Wine quality scores are assigned by human tasters, which introduces subjectivity a chemical model cannot fully capture. An R² of 0.32 is **expected** in this context — it confirms which variables matter statistically, but does not imply the model is production-ready. This is documented intentionally.

### 4️⃣ Machine Learning — Random Forest Classifier
- Quality scores binned into **Low / Medium / High** categories
- Random Forest trained to classify batches by quality grade
- Feature importance extracted and compared against OLS regression findings
- Classifier outperforms OLS for practical batch-level pass/fail decisions

### 5️⃣ SQL Database Integration
- Model predictions written into a **SQLite database** (`factory_production.db`)
- Threshold queries flag batches predicted below minimum acceptable quality
- Structured for potential integration with a QA reporting dashboard

### 6️⃣ Written QC Report
The PDF report documents:
- Problem statement and methodology
- Statistical findings with honest interpretation
- Model limitations and dataset constraints
- How this workflow maps to real QA/QC lab practice

---

## 📊 Key Findings

```
🔴 Volatile Acidity   →   strongest NEGATIVE predictor of wine quality
🟢 Alcohol Content    →   strongest POSITIVE predictor of wine quality
📉 R² = 0.3242        →   modest but expected for human-rated sensory targets
🌲 Random Forest      →   more practical than OLS for batch classification
```

---

## 🛠️ Tools & Libraries

| Tool | Purpose |
|---|---|
| 🐍 Python | Core analysis and modeling |
| 🐼 Pandas | Data cleaning and manipulation |
| 🤖 Scikit-learn | OLS regression and Random Forest |
| 📈 Matplotlib / Seaborn | Visualization |
| 🗄️ SQLite / SQLAlchemy | Database storage |
| 📓 Jupyter Notebook | Analysis environment |

---

## ⚠️ Limitations & Planned Improvements

This is a **student portfolio project**, not a production system. Known limitations are documented here, not hidden:

- [ ] Dataset is public (UCI) — not real industrial production data
- [ ] R² is modest (0.32) — acceptable for sensory targets; real QA needs domain-specific data
- [ ] Single train/test split used — k-fold cross-validation would give more reliable estimates
- [ ] No confusion matrix or feature importance plot saved yet — next additions to the notebook
- [ ] SQL queries are basic — production version would include automated QC summary reports

---

## 💡 What I Learned

- How to read OLS output beyond R² — p-values, coefficient direction, and operational meaning
- Why a low R² on sensory data is expected and how to communicate that honestly
- How to connect a Python analysis pipeline to a SQL database for structured storage
- How to write a QC report that separates what the data shows from what the model cannot claim

---

## 👤 Author

<div align="center">

**Ubaid Ur Rehman**

BS Chemistry (Final Semester) | The Islamia University of Bahawalpur
CGPA: 3.84 / 4.0 | CM Honhaar Scholar | IChC 2026 Qualifier

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ubaid-ur-rehman-chemist)
[![GitHub](https://img.shields.io/badge/GitHub-Profile-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ur-chemist)

</div>

---

<div align="center">

*Built as part of a portfolio demonstrating analytical chemistry + data skills for QA and R&D roles*

</div>
