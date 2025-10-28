# Product Line Performance – Tableau BI Project

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

## Observations:

No missing data detected.
Revenue formula consistent with provided values.
Some outlier pricing in “Binders” category, possibly from regional promotions.

## Dashboard Design – Z Layout

The Tableau dashboard follows a Z-pattern layout for clear data storytelling:

Summary KPIs – Revenue, Units, and Unit Price
Revenue Trends by Region – monthly performance
Heatmap of Product Revenue – identify top-selling items
Sales Rep Scatter Plot – performance outliers and quartiles

Average Unit Price Comparison – pricing consistency across regions

## Key Visuals
1. High-Level KPIs
2. Revenue Trend by Region
3. Revenue by Item (Heatmap)
4. Revenue by Sales Rep (Scatter Plot)
5. Unit Price by Region

## Insights & Recommendations
Area	Insight	Recommendation
Regional Performance	The North Region consistently outperforms others but shows the widest unit price variance.	Review pricing policy and apply standardized pricing or discounts based on margins.
Sales Team	2 reps (Julia & Frank) generate 35% of total revenue; 3 reps underperform.	Provide targeted sales training and reassign territories.
Product Lines	Binders and Staplers show declining revenue trends despite stable unit prices.	Consider limited-time promotions or bundling strategies.
Pricing Strategy	Average Unit Price varies 15–20% between regions.	Audit regional pricing and evaluate competitive benchmarks.

## Executive Summary (PDF)

A concise one-page summary of key findings and business actions.
## Download Business_Recommendations.pdf

🔗 View the Dashboard Live

Explore the interactive Tableau Story:
➡️ Product Line Performance on Tableau Public

🧰 Tools Used

Tableau Public – dashboard creation and storytelling
Python (Pandas) – data exploration and validation
Excel – quick review and data checks
GitHub – project documentation and sharing

🪄 Author

Adriano [Your Last Name]
Master’s Student in Data Science & Analytics – USP/Esalq
📍 Based in Amsterdam
🔗 Tableau Public Profile

🔗 LinkedIn Profile
