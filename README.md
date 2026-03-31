#  End-to-End Customer Churn Analysis

> A comprehensive data analytics project combining **SQL Server**, **Power BI**, and **Machine Learning** to analyze customer churn and predict future churners for a telecom firm.

---

##  Project Title
**End-to-End Customer Churn Analysis — Telecom Domain**

##  Brief Summary
Analyzed 6,418 customer records to uncover churn patterns, built an interactive multi-page Power BI dashboard, and trained a Random Forest ML model that predicted 384 at-risk customers.

---

##  Overview

Customer churn is one of the biggest challenges for subscription-based businesses. This project performs an **end-to-end churn analysis** for a telecom company — from raw data ingestion to a fully interactive dashboard and a machine learning prediction pipeline.

**Project Goals:**
- Visualize customer demographics and geographic churn patterns
- Study payment & account behaviour of churned vs. retained customers
- Identify the churner profile to support targeted retention campaigns
- Predict future churners using a Machine Learning model

---

##  Problem Statement

The telecom company is experiencing a churn rate of nearly **27%**, resulting in significant revenue loss. The business needs to:
1. Understand *why* customers are leaving
2. Identify *which* customer segments are most at risk
3. Take *proactive* action before customers actually churn

---

##  Dataset

| Attribute | Details |
|-----------|---------|
| Source | Telecom Customer Dataset (CSV) |
| Total Records | 6,418 customers |
| Churn Rate | 26.99% (1,732 churned) |
| New Joiners | 411 |
| Key Features | Demographics, Geography, Contract Type, Payment Method, Services Subscribed |

---

##  Tools & Technologies

| Tool | Purpose |
|------|---------|
| **SQL Server / SSMS** | ETL, data cleaning, views creation |
| **Power BI** | Interactive dashboard, DAX measures, data modelling |
| **Python (Jupyter Notebook)** | Machine learning model, data processing |
| **Scikit-learn** | Random Forest Classifier |
| **Pandas** | Data manipulation |

---

##  Methods

### Step 1 — ETL in SQL Server
- Created `db_Churn` database in SQL Server
- Imported raw CSV into staging table
- Explored data for nulls and distinct values
- Cleaned data using `ISNULL`, loaded into production table
- Created `vw_ChurnData` and `vw_JoinData` views

### Step 2 — Power BI Data Transformation
- Connected Power BI directly to SQL Server
- Created calculated columns in Power Query: **Churn Status**, **Monthly Charge Range**, **Age Group**, **Tenure Group**
- Built mapping tables and unpivoted services columns

### Step 3 — DAX Measures
- Built core measures: `Total Customers`, `New Joiners`, `Total Churn`, `Churn Rate`
- These power all KPI cards and visuals across dashboard pages

### Step 4 — Power BI Dashboard
- Multi-page interactive dashboard (Summary, Churn Analysis, Churn Prediction pages)
- Charcoal Grey / Purple / Gold theme with tooltips and slicers
- Covers demographics, geography, payment info, and service usage

### Step 5 — Machine Learning (Random Forest)
- Label Encoded all categorical features
- Trained `RandomForestClassifier` with 100 estimators on 80% training data
- Evaluated using confusion matrix and classification report
- Exported predictions to `Predictions.csv`

### Step 6 — ML Predictions in Power BI
- Imported `Predictions.csv` into Power BI
- Built dedicated **Churn Prediction page** showing 384 predicted churners by demographics, geography, and contract type

---

## 💡 Key Insights

| Insight | Detail |
|---------|--------|
| 📄 Month-to-Month Churn | **46.53%** — far higher than annual/biennial contracts |
| 📍 Highest Churn State | **Jammu & Kashmir at 57.19%** — needs targeted campaigns |
| 🏆 Top Churn Reason | **761 customers left due to competitor** — pricing gap |
| 🔒 No Online Security | **84.64% churn rate** — major upsell opportunity |
| 👴 Age 50+ Churn | **43% churn rate** — needs dedicated engagement strategy |
| 🤖 ML Predicted | **384 customers** likely to churn — actionable for retention |

---

## 📊 Dashboard / Model Output

**Dashboard Pages:**
1. **Summary** — Overall KPIs, demographics, churn by category
2. **Churn Analysis** — Geography, payment method, service usage breakdown
3. **Churn Prediction** — 384 ML-predicted churners segmented by profile

**ML Model Details:**

| Parameter | Value |
|-----------|-------|
| Algorithm | Random Forest Classifier |
| No. of Trees | 100 estimators |
| Train Size | 80% — 4,805 rows |
| Test Size | 20% — 1,202 rows |
| Output | `Predictions.csv` |

---

## ▶️ How to Run This Project

### Prerequisites
- SQL Server / SSMS installed
- Power BI Desktop installed
- Python 3.x with Jupyter Notebook (Anaconda recommended)

### 1. SQL Setup
```sql
-- Create database
CREATE DATABASE db_Churn;

-- Import CSV into staging table via SSMS Import Wizard
-- Run cleaning scripts to create production table
-- Create views: vw_ChurnData, vw_JoinData
```

### 2. Power BI Dashboard
- Open `Churn_Analysis.pbix` in Power BI Desktop
- Update the SQL Server connection to your local instance (`.\SQLEXPRESS` or your server name)
- Refresh data

### 3. Machine Learning Model
```bash
# Install dependencies
pip install pandas scikit-learn jupyter

# Launch Jupyter Notebook
jupyter notebook
```
- Open `Churn_Prediction.ipynb`
- Run all cells
- `Predictions.csv` will be generated in the working directory

### 4. Load Predictions into Power BI
- Import `Predictions.csv` into Power BI
- Navigate to the **Churn Prediction** page to view results

---

## ✅ Results & Conclusion

- Successfully identified that **month-to-month contracts** and **lack of online security** are the strongest churn drivers
- **Competitor pricing** is the #1 stated churn reason — a direct business action item
- Customers aged **50+** and those in **J&K** require targeted retention campaigns
- The Random Forest model predicted **384 future churners**, enabling proactive outreach before churn occurs
- This end-to-end pipeline is replicable across retail, finance, and healthcare sectors

---

## 🔭 Future Work

- [ ] Deploy the ML model as a REST API using Flask or FastAPI
- [ ] Automate data refresh pipeline using SQL Server Agent
- [ ] Incorporate real-time churn scoring with Power BI live connection
- [ ] Experiment with XGBoost and SHAP for improved model explainability
- [ ] Build a customer segmentation model (RFM / K-Means) for campaign targeting

---


---

*This project is part of my Data Analytics Portfolio — 2026*
