# 📈 Investment Portfolio Optimization using Machine Learning & RollingOLS  
*Built with PCA, VIF, Double Scaling, and Multi-Model Predictive Ranking*

---

## 🧠 Project Summary

This project builds a robust stock ranking and portfolio optimization pipeline using financial statement data, predictive modeling, and machine learning.  
We forecast 3-month forward stock returns and rank companies using models like RollingOLS, Logistic Regression, and Random Forest on a PCA-transformed dataset.

---

## 🗂️ Repository Structure

Investment-Portfolio-Optimzation/
│
├── 1 Raw Data/ # Original Excel input files
├── 2 Codes/ # Jupyter notebooks for data prep, modeling & ranking
├── 3 Processed Data/ # Cleaned datasets with PCA & scaling applied
├── 4 Presentation/ # PPT slides summarizing the project
├── 6 Dashboard/ # Interactive return charts (monthly, cumulative)
├── .gitignore
├── LICENSE
└── README.md


---

## 🔍 Problem Statement

**Goal:**  
Rank stocks based on predicted 3-month forward returns using firm fundamentals and model-based forecasts.

**Challenges Addressed:**
- High multicollinearity among financial ratios
- Missing value imputation
- Dimensionality reduction
- Classification vs regression trade-offs
- Robust portfolio construction

---

## 🔧 Features & Workflow

### ✅ Data Preparation
- Three-stage missing value imputation
- Winsorization for outlier treatment (2.5% → 10%)
- Single and double scaling (StandardScaler + RobustScaler)
- VIF-based multicollinearity reduction
- PCA-based dimensionality reduction (31 financial ratios → 10 components)

### 🤖 Models Built
| Model | Type | Scaling | Target | Technique |
|-------|------|---------|--------|-----------|
| Model 2 | RollingOLS | Single | Return (Reg) | Statsmodels RollingOLS |
| Model 3 | RollingOLS | Double | Return (Reg) | With enhanced scaling |
| Model 4 | Logistic | Single | High/Low Binary | Classification |
| Model 5 | Logistic | Double | High/Low Binary | Improved robustness |
| Model 6 | Random Forest | Double | High/Low Binary | Non-linear + Feature Importance |

### 💼 Portfolio Construction
- Top 30 stocks selected monthly based on model rankings
- Portfolios rebalanced monthly from 2006–2023
- Portfolio performance evaluated using:
  - Average 3-month returns
  - Cumulative returns (percentage & dollar)
  - Interactive HTML dashboards

---

## 📊 Outputs

Explore:
- 📈 Monthly Return Dashboard: `/6 Dashboard/Interactive Chart_Portfolio Returns - Monthly.html`  
- 💰 Cumulative Returns ($): `/6 Dashboard/Interactive Chart_Portfolio Returns - Cumulative $.html`  
- 📈 Cumulative Returns (%): `/6 Dashboard/Interactive Chart_Portfolio Returns - Cumulative %.html`  
- 📂 Predicted Stock Rankings: `/12 Predicted Portfolios - Top 30 Stocks_6 Models_2006-23.xlsx`  
- 📂 Portfolio Returns: `/13 Portfolio Returns - Monthly & Cumulative_2006-23.xlsx`

---

## 🚀 Getting Started

### 1. Clone the Repository

git clone https://github.com/SamHossain2025/Investment-Portfolio-Optimzation.git
cd Investment-Portfolio-Optimzation


2. Install Requirements

Use pip:

pip install -r requirements.txt

Or create a conda environment:

conda create -n portfolio-opt python=3.10
conda activate portfolio-opt
pip install -r requirements.txt

3. Run the Pipeline

Open the notebooks under 2 Codes/ in order:

01 Code_Data Cleaning & Prep.ipynb

02–06: Model training notebooks

11 Code_Portfolio Building & Return Calc.ipynb

🧾 Requirements

pandas

scikit-learn

statsmodels

openpyxl

plotly

matplotlib

python-pptx

numpy

You can install these using:

pip install pandas scikit-learn statsmodels openpyxl plotly matplotlib python-pptx numpy

🧠 Key Learnings

How to combine statistical and ML models to rank stocks

The value of PCA + VIF in reducing overfitting

Power of double-scaling in handling financial data

Designing a complete investment pipeline—from raw data to dashboards

👤 Author

Sam Hossain
MMA Candidate 2025 | Queen's University
📫 LinkedIn
 | ✉️ hossainsam@gmail.com

📜 License

MIT License © Sam Hossain 2025
Feel free to fork, adapt, or contribute!


---

✅ Once you copy-paste this into your `README.md` file and push it to GitHub, your project will look sharp, professional, and complete.

Let me know if you'd like a **version with screenshots or badges** added too!
