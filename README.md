<p align="center">
  <img src="6 Assets/Banner.png" width="100%">
</p>

# 📈 Investment Portfolio Optimization Using Predictive Modeling

*A machine learning and statistical modeling pipeline for ranking stocks and constructing high-return portfolios over time.*

* Dataset timeline: **2010 January – 2023 December**
* Topics covered: **Portfolio Analytics, ML Models, Financial Forecasting**
* Models used: **RollingOLS, Logistic Regression, Random Forest**
* Skills demonstrated: **Data cleaning, PCA, Feature engineering, Multi-model comparison, Dashboarding**
* Expected outcome:

  * **Rank stocks using predictive models**
  * **Construct and evaluate top-performing portfolios**

---

## 👥 Authors

**Sam Hossain** and MMA Team Gordon Members (Alisha Sahota, Anthony Ramelo, Chris Wu, Elizabeth Zhang, Emily Zhao)

---

## 🔍 Problem Statement

**Goal:**

Rank stocks based on predicted 3-month forward returns using firm fundamentals and model-based forecasts.

**Challenges Addressed:**

* High multicollinearity among financial ratios
* Missing value imputation
* Dimensionality reduction using PCA
* Classification vs regression trade-offs
* Robust portfolio construction and rebalancing

---

## 🔧 Workflow

### ✅ Data Preparation

* Three-stage missing value imputation
* Winsorization for outlier treatment (2.5% → 10%)
* Single and double scaling (StandardScaler + RobustScaler)
* VIF-based multicollinearity reduction
* PCA-based dimensionality reduction (31 financial ratios → 10 components)

<p align="center">
  <img src="6 Assets/Data1.png" width="80%">
</p>

### 🤖 Models Built

| Model   | Type          | Scaling | Target          | Technique                       |
| ------- | ------------- | ------- | --------------- | ------------------------------- |
| Model 2 | RollingOLS    | Single  | Return (Reg)    | Statsmodels RollingOLS          |
| Model 3 | RollingOLS    | Double  | Return (Reg)    | With enhanced scaling           |
| Model 4 | Logistic      | Single  | High/Low Binary | Classification                  |
| Model 5 | Logistic      | Double  | High/Low Binary | Improved robustness             |
| Model 6 | Random Forest | Double  | High/Low Binary | Non-linear + Feature Importance |

**✨ Verdict:** Model 6 (Random Forest) offers the best performance on binary classification, while Model 3 (RollingOLS Double-scaled) is optimal for regression-based portfolio ranking.

<p align="center">
  <img src="6 Assets/Model1.png" width="80%">
  <img src="6 Assets/Model2.png" width="80%">
  <img src="6 Assets/Model3.png" width="80%">
  <img src="6 Assets/Model4.png" width="80%">
  <img src="6 Assets/Model5.png" width="80%">
  <img src="6 Assets/Model6.png" width="80%">
  <img src="6 Assets/Model7.png" width="80%">
  <img src="6 Assets/Model8.png" width="80%">
  <img src="6 Assets/Model9.png" width="80%">
  <img src="6 Assets/Model10.png" width="80%">
</p>

### 💼 Portfolio Construction

* Rank all stocks monthly using model predictions
* Select top 30 stocks each month as portfolio
* Rebalance portfolios monthly from 2006 to 2023
* Track and store monthly & cumulative returns for each model
* Evaluate using: average 3-month returns, cumulative returns in %, and \$ terms
* Visualize results via interactive dashboards and Excel files

<p align="center">
  <img src="6 Assets/Portfolio1.png" width="80%">
  <img src="6 Assets/Portfolio2.png" width="80%">
  <img src="6 Assets/Portfolio3.png" width="80%">
  <img src="6 Assets/Portfolio4.png" width="80%">
</p>

---

## 🎯 Key Findings

* Double-scaling combined with PCA leads to more stable model performance.
* Random Forest ranked portfolios outperform in binary classification tasks.
* RollingOLS (Model 3) produces the most interpretable return predictions across time.

<p align="center">
  <img src="6 Assets/Findings1.png" width="80%">
  <img src="6 Assets/Findings2.png" width="80%">
</p>

---

## 💡 Key Recommendations

* Use Random Forest for future binary ranking models.
* Apply double scaling + PCA to reduce noise and multicollinearity.
* Rebalance portfolios monthly to adapt to regime changes and market cycles.

---

## 📊 Output Dashboard

<p align="center">
  <img src="6 Assets/Dashboard1.png" width="80%">
  <img src="6 Assets/Dashboard2.png" width="80%">
  <img src="6 Assets/Dashboard3.png" width="80%">
</p>

---

## 🚀 How to Run This Project

1. **Clone the repository**

   ```bash
   git clone https://github.com/SamHossain2025/Investment-Portfolio-Optimization.git
   cd Investment-Portfolio-Optimization
   ```

2. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Launch Jupyter Notebook**

   ```bash
   jupyter notebook
   ```

4. **Open and execute notebooks**

   * `01 Code_Data Cleaning & Prep.ipynb`
   * `02–06`: Model training notebooks
   * `11 Code_Portfolio Building & Return Calc.ipynb`

---

## 🧬 Data Sources

* Internal company-level financials dataset (non-public)
* Portfolio backtesting conducted over cleaned data between 2006–2023

---

## 🔓 License

This project is licensed under the [MIT License](LICENSE)

