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






<p align="center">
  <img src="6 Assets/Banner.png" width="100%">
</p>

# 📈 Investment Portfolio Optimization Using Predictive Modeling

*A machine learning and statistical modeling pipeline for ranking stocks and constructing high-return portfolios over time.*

* Dataset timeline: **2010 January – 2023 December**
* Topics covered: **Financial Forecasting, Portfolio Analytics, ML Models**
* Models used: **RollingOLS, Logistic Regression, Random Forest**
* Data period: **Monthly panel data from Jan 2006 to Dec 2023**
* Skills demonstrated: **Data cleaning, PCA, feature engineering, multi-model comparison, dashboarding**
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

This project builds a full forecasting pipeline using panel data on financial ratios, applying three-stage imputation, multicollinearity filtering, and PCA. The cleaned and scaled dataset is used to train six predictive models aimed at forecasting short-term returns.

Model outputs are used to rank stocks monthly from 2006 to 2023. Top 30 stocks are selected into portfolios, tracked over time, and compared via interactive dashboards to assess which model performs best.

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
  <img src="6 Assets/Portfolio5.png" width="80%">
</p>

---

## 🎯 Key Findings

* Double-scaling combined with PCA leads to more stable model performance.
* Random Forest ranked portfolios outperform in binary classification tasks.
* RollingOLS (Model 3) produces the most interpretable return predictions across time.

<p align="center">
  <img src="6 Assets/Findings1.png" width="80%">
  <img src="6 Assets/Findings2.png" width="80%">
  <img src="6 Assets/Findings3.png" width="80%">
  <img src="6 Assets/Findings4.png" width="80%">
  <img src="6 Assets/Findings5.png" width="80%">
</p>

---

## 💡 Key Recommendations

* Use Random Forest for future binary ranking models.
* Apply double scaling + PCA to reduce noise and multicollinearity.
* Rebalance portfolios monthly to adapt to regime changes and market cycles.

<p align="center">
  <img src="6 Assets/Recommendation1.png" width="80%">
  <img src="6 Assets/Recommendation2.png" width="80%">
  <img src="6 Assets/Recommendation3.png" width="80%">
  <img src="6 Assets/Recommendation4.png" width="80%">
  <img src="6 Assets/Recommendation5.png" width="80%">
</p>

---

## 📊 Output Dashboard

<p align="center">
  <img src="6 Assets/Dashboard1.png" width="80%">
  <img src="6 Assets/Dashboard2.png" width="80%">
  <img src="6 Assets/Dashboard3.png" width="80%">
  <img src="6 Assets/Dashboard4.png" width="80%">
  <img src="6 Assets/Dashboard5.png" width="80%">
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

