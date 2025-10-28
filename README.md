# 📊 Product Line Performance – Tableau BI Project

![Header](images/header_banner.png)

### Overview
This project analyzes **The Paper Company’s** performance across its newer **non-paper office supply product lines**.  
As a Data Analyst, I was tasked to explore 12 months of sales data from **3 regions** and **11 sales reps**, and provide insights and recommendations for **Angela**, the Head of Finance.

The goal: identify which product lines and regions drive the most revenue, detect performance issues, and uncover improvement opportunities.

---

### Objectives & KPIs

| Objective | Description | KPI |
|------------|--------------|-----|
| Review current product lines and identify areas for improvement | Track top-performing products, regions, and reps | Revenue |
| Identify areas that can improve revenue | Understand variance in sales volume and pricing | Units |
| Monitor pricing and operational consistency | Detect pricing anomalies between regions | Unit Price |

** KPI Definitions**

- **Revenue** = Units × Unit Price  
- **Units** = Total quantity sold  
- **Unit Price** = Average sale price per unit  

---

### Dataset
- **Source:** [Kaggle – Office Supplies Sales Dataset](https://www.kaggle.com/)
- **File:** `/data/OfficeSupplies.csv`
- **Rows:** 3,960 records  
- **Columns:** `Order Date`, `Region`, `Rep`, `Item`, `Units`, `Unit Price`  
- **Period Covered:** 12 months  

A quick validation script (`notebooks/data_exploration.ipynb`) checks for missing values, duplicates, and verifies calculated revenue consistency.

---

### Data Exploration (Python)
Before visualization, I performed a short data quality check in Python (Pandas).

```python
import pandas as pd

df = pd.read_csv('data/OfficeSupplies.csv')
df.info()
df.describe()
df.isna().sum()
df['Revenue'] = df['Units'] * df['Unit Price']
