# 📊 Vendor Performance Analysis


# 📖 Overview

Vendor performance plays a crucial role in supply chain efficiency, inventory optimization, and business profitability. Organizations must continuously monitor purchasing patterns, sales performance, inventory turnover, and vendor contributions to make informed business decisions.

This project presents an end-to-end **Data Analytics solution** that transforms raw retail inventory data into meaningful business insights. The project integrates **SQL, Python, SQLite, Exploratory Data Analysis (EDA), Statistical Analysis, and Power BI** to evaluate vendor performance and provide actionable recommendations.

The complete workflow includes:

- Data ingestion from multiple CSV files
- Database creation using SQLite
- SQL-based data aggregation
- Data cleaning and feature engineering
- Exploratory Data Analysis
- Statistical hypothesis testing
- Interactive Power BI dashboard
- Business recommendations

---

# 🎯 Business Problem

Retail and wholesale businesses manage thousands of products supplied by numerous vendors. Without proper analysis, companies may experience:

- Poor inventory turnover
- Vendor dependency
- Excess inventory holding costs
- Inefficient pricing strategies
- Reduced profitability

The objective of this project is to answer the following business questions:

- Identify underperforming brands requiring promotional or pricing adjustments.
- Determine the vendors contributing the most to purchases and sales.
- Analyze the impact of bulk purchasing on unit costs.
- Evaluate inventory turnover across vendors.
- Compare profitability between high-performing and low-performing vendors.
- Generate data-driven recommendations to improve business performance.

---

# 🚀 Project Objectives

The primary objectives of this project are:

✔ Analyze vendor performance

✔ Improve inventory management

✔ Optimize pricing strategies

✔ Identify slow-moving inventory

✔ Evaluate purchasing efficiency

✔ Compare vendor profitability

✔ Support business decision-making using data analytics

---

# 🏗 Project Architecture

```text
                   Business Problem
                          │
                          ▼
                  Raw CSV Datasets
                          │
                          ▼
               SQLite Database Creation
                 (ingestion_db.py)
                          │
                          ▼
             SQL Data Aggregation & Joins
              (get_vendor_summary.py)
                          │
                          ▼
              Vendor Summary Dataset
                          │
          ┌───────────────┴───────────────┐
          ▼                               ▼
Exploratory Data Analysis          Statistical Analysis
          │                               │
          └───────────────┬───────────────┘
                          ▼
                 Business Insights
                          │
                          ▼
               Interactive Power BI Dashboard
                          │
                          ▼
                Business Recommendations
```

---

# 📂 Repository Structure

```text
Vendor-Performance-Analysis
│
├── data/                          # Raw datasets (Not included)
│
├── dashboard/
│   └── vendor_performance.pbix
│
├── report/
│   └── Vendor Performance Report.pdf
│
├── notebooks/
│   ├── Exploratory Data Analysis.ipynb
│   └── Vendor Performance Analysis.ipynb
│
├── scripts/
│   ├── ingestion_db.py
│   └── get_vendor_summary.py
│
├── vendor_sales_summary.csv
├── README.md
├── requirements.txt
└── .gitignore
```

---

# 💻 Technology Stack

| Category | Technologies |
|-----------|--------------|
| Programming Language | Python |
| Database | SQLite |
| Query Language | SQL |
| Data Manipulation | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Dashboard | Power BI |
| Notebook | Jupyter Notebook |
| ORM | SQLAlchemy |
| IDE | VS Code, Jupyter |

---

# 📊 Dataset Description

The project utilizes six retail datasets representing different stages of the inventory lifecycle.

| Dataset | Description |
|----------|-------------|
| Beginning Inventory | Initial inventory available in stock |
| Ending Inventory | Remaining inventory after sales |
| Purchases | Product purchase transactions |
| Sales | Product sales transactions |
| Purchase Prices | Product pricing information |
| Vendor Invoice | Vendor invoice and freight details |

The raw datasets are first loaded into a SQLite database, where SQL queries are used to combine and aggregate information into a single analytical dataset.

> **Note**
>
> The original dataset is approximately **2 GB** and is **not included** in this repository due to GitHub's file size limitations.
>
> To reproduce this project, place the original CSV files inside the `data/` directory before running the ingestion script.

---


## Install dependencies

```bash
pip install -r requirements.txt
```

---

# ▶ How to Run the Project

### Step 1

Place all raw CSV files inside

```text
data/
```

---

### Step 2

Run the database ingestion script

```bash
python scripts/ingestion_db.py
```

This script automatically:

- Reads all CSV files
- Creates SQLite tables
- Loads the data into the database

---

### Step 3

Generate the vendor summary dataset

```bash
python scripts/get_vendor_summary.py
```

The script performs:

- SQL joins
- Data aggregation
- Feature engineering
- Vendor-level KPI calculation

It generates

```text
vendor_sales_summary.csv
```

which serves as the primary dataset for exploratory data analysis and dashboard development.

---

### Step 4

Open the notebooks

```
Exploratory Data Analysis.ipynb
```

and

```
Vendor Performance Analysis.ipynb
```

to reproduce the complete analysis.

---

### Step 5

Open

```
dashboard/vendor_performance.pbix
```

using **Microsoft Power BI Desktop** to explore the interactive dashboard.

---

# 🔄 Project Workflow

```text
Raw CSV Files
      │
      ▼
SQLite Database
      │
      ▼
SQL Aggregation
      │
      ▼
Feature Engineering
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Statistical Analysis
      │
      ▼
Power BI Dashboard
      │
      ▼
Business Recommendations
```

---

## 📌 Project Highlights

- End-to-End Data Analytics Pipeline
- SQL-Based Data Aggregation
- Automated SQLite Database Creation
- Feature Engineering
- Exploratory Data Analysis (EDA)
- Statistical Hypothesis Testing
- Interactive Power BI Dashboard
- Business-Oriented Recommendations
- Reproducible Analytics Workflow

---


# 🔧 Data Pipeline

The project follows a structured ETL (Extract, Transform, Load) pipeline to convert raw transactional data into a clean analytical dataset.

## Step 1: Data Ingestion

The `ingestion_db.py` script automates the ingestion of multiple CSV files into a SQLite database.

### Responsibilities

- Reads all CSV files from the `data/` directory
- Creates SQLite tables automatically
- Stores each dataset using SQLAlchemy
- Eliminates manual database creation

**Input**

```
Beginning Inventory
Ending Inventory
Purchases
Purchase Prices
Sales
Vendor Invoice
```

**Output**

```
inventory.db
```

---

## Step 2: Vendor Summary Generation

The `get_vendor_summary.py` script performs SQL-based data aggregation to combine information from multiple tables into a single vendor-level dataset.

### SQL Operations

The script performs:

- Common Table Expressions (CTEs)
- LEFT JOIN operations
- Aggregations using SUM()
- Vendor-wise grouping
- Brand-wise aggregation
- Freight cost calculation

The final output contains one consolidated record for each vendor-brand combination.

---

# 🧹 Data Cleaning & Feature Engineering

Before performing the analysis, the dataset undergoes several preprocessing steps.

### Data Cleaning

- Converted numerical columns to appropriate data types
- Removed leading/trailing whitespace
- Replaced missing values with zero
- Standardized column formats

---

### Feature Engineering

Several business metrics were created to support analytical insights.

| Feature | Description |
|----------|-------------|
| Gross Profit | Total Sales − Total Purchase Cost |
| Profit Margin | Gross Profit as a percentage of Sales |
| Stock Turnover | Sales Quantity / Purchase Quantity |
| Sales-to-Purchase Ratio | Sales Dollars / Purchase Dollars |

These engineered features serve as key performance indicators (KPIs) throughout the project.

---

# 📈 Exploratory Data Analysis

Comprehensive exploratory data analysis (EDA) was performed to understand purchasing patterns, sales performance, vendor profitability, and inventory behavior.

The analysis included:

- Summary statistics
- Missing value analysis
- Distribution analysis
- Correlation analysis
- Outlier detection
- Inventory analysis
- Profitability analysis

---

## Summary Statistics

The statistical summary provided valuable insights into the characteristics of the dataset.

### Key Observations

### Negative Gross Profit

Some transactions produced negative gross profits, indicating products sold below their purchase cost.

Possible reasons include:

- Heavy discounts
- Promotional campaigns
- Pricing errors

---

### Zero Sales Products

Certain products were purchased but never sold.

This indicates:

- Dead stock
- Slow-moving inventory
- Overstocking

---

### Freight Cost Variation

Freight costs showed substantial variability across vendors.

Possible causes include:

- Different shipment sizes
- Vendor location differences
- Logistics inefficiencies

---

### Premium Products

Purchase prices ranged from inexpensive products to premium offerings costing several thousand dollars.

This demonstrates significant pricing diversity across brands.

---

### Stock Turnover

Stock turnover values varied considerably.

Interpretation:

- High turnover → Faster inventory movement
- Low turnover → Slow-moving inventory
- Zero turnover → Unsold inventory

---

# 📊 Data Filtering

To improve the reliability of the analysis, the following records were excluded:

- Gross Profit ≤ 0
- Profit Margin ≤ 0
- Total Sales Quantity = 0

This ensured that statistical analyses focused on profitable transactions and actively selling products.

---

# 🔍 Correlation Analysis

A correlation matrix was created to understand relationships among numerical variables.

### Key Findings

### Purchase Price vs Sales

Very weak correlation

This indicates that increasing purchase prices does not necessarily increase revenue.

---

### Purchase Quantity vs Sales Quantity

Extremely strong positive correlation

This suggests effective inventory replenishment and demand matching.

---

### Profit Margin vs Sales Price

Weak negative correlation

Higher selling prices are not always associated with higher profit margins, likely due to competitive pricing strategies.

---

### Stock Turnover vs Profitability

Very weak correlation

Rapid inventory movement alone does not guarantee higher profitability.

---

# 📌 Business Questions

The analysis focuses on answering six business questions.

---

## 1. Which brands require promotional strategies?

### Objective

Identify brands generating high margins but low sales.

### Finding

Approximately **198 brands** were identified.

These brands represent opportunities for:

- Promotional campaigns
- Better product visibility
- Pricing optimization

---

## 2. Which vendors contribute the most?

### Objective

Determine vendor dependency.

### Finding

Top 10 vendors account for approximately **65.69%** of total purchases.

This indicates:

- High supplier concentration
- Potential supply chain risk
- Need for vendor diversification

---

## 3. Does bulk purchasing reduce cost?

### Objective

Evaluate purchasing efficiency.

### Finding

Large purchase orders reduced unit costs by approximately **72%**.

Business implication:

Bulk purchasing creates economies of scale and improves procurement efficiency.

---

## 4. Which vendors have poor inventory turnover?

### Objective

Identify slow-moving inventory.

### Finding

Approximately **$2.71 million** worth of inventory remains unsold.

Business impact:

- Higher storage costs
- Lower cash flow
- Increased inventory holding risk

---

## 5. How do high-performing vendors differ from low-performing vendors?

Confidence interval analysis was performed on vendor profit margins.

### Results

| Vendor Group | Average Profit Margin |
|--------------|----------------------:|
| Top Vendors | 31.17% |
| Low-performing Vendors | 41.55% |

Interpretation:

Low-performing vendors earn higher margins but generate substantially lower sales volumes.

---

## 6. Is the difference statistically significant?

A hypothesis test was conducted.

### Null Hypothesis (H₀)

There is no significant difference between the profit margins of top-performing and low-performing vendors.

### Alternative Hypothesis (H₁)

A significant difference exists.

### Result

The null hypothesis was rejected.

### Conclusion

The two vendor groups operate under statistically different profitability models.

---

# 📊 Statistical Techniques Used

The project incorporates multiple analytical techniques.

- Descriptive Statistics
- Correlation Analysis
- Confidence Intervals
- Hypothesis Testing
- Comparative Analysis
- Business KPI Analysis

---

# 📈 Key Findings

The analysis revealed several important business insights.

- 198 brands require promotional strategies.
- Top 10 vendors contribute nearly two-thirds of purchases.
- Bulk purchasing reduces procurement cost significantly.
- Approximately $2.71M inventory remains unsold.
- Inventory turnover alone is not a reliable indicator of profitability.
- Low-performing vendors earn higher margins but have weaker sales performance.
- Profitability differences between vendor groups are statistically significant.

---


# 📊 Power BI Dashboard

An interactive Power BI dashboard was developed to visualize key business metrics and support data-driven decision-making.

The dashboard enables users to monitor vendor performance, inventory efficiency, sales trends, and profitability through dynamic filters and visualizations.

## Dashboard Features

- Vendor Performance Analysis
- Sales Performance Overview
- Purchase Analysis
- Gross Profit Analysis
- Profit Margin Comparison
- Inventory Turnover Analysis
- Brand Performance
- Top Vendor Contribution
- Slow Moving Inventory Analysis

---

# 📈 Business Insights

The analysis generated several actionable business insights that can improve operational efficiency and profitability.

## Vendor Performance

- Top 10 vendors contribute nearly **66%** of total purchases.
- Heavy dependency on a small number of vendors introduces supply chain risk.
- Vendor diversification can improve procurement resilience.

---

## Pricing Strategy

- Approximately **198 brands** generate high profit margins but relatively low sales.
- These brands represent opportunities for:
  - Targeted marketing campaigns
  - Promotional discounts
  - Optimized pricing strategies

---

## Bulk Purchasing

Bulk purchasing significantly lowers procurement costs.

Benefits include:

- Reduced unit purchase price
- Better supplier negotiations
- Higher purchasing efficiency
- Improved profitability

---

## Inventory Management

Approximately **$2.71 million** worth of inventory remains unsold.

This indicates:

- Overstocking
- Slow-moving products
- Poor inventory turnover

Reducing excess inventory can improve cash flow and reduce storage costs.

---

## Profitability Analysis

Low-performing vendors generate higher profit margins but considerably lower sales volumes.

In contrast,

Top-performing vendors achieve higher sales through greater transaction volume despite comparatively lower margins.

---

# 💡 Business Recommendations

Based on the analysis, the following recommendations are proposed.

### 1. Optimize Pricing Strategy

Review pricing for high-margin, low-volume products to increase sales without significantly reducing profitability.

---

### 2. Diversify Vendor Network

Reduce dependency on a limited number of suppliers by onboarding additional vendors.

Benefits include:

- Lower procurement risk
- Improved bargaining power
- Better supply chain resilience

---

### 3. Improve Inventory Planning

Reduce excess inventory by

- Forecasting demand
- Optimizing reorder quantities
- Monitoring slow-moving products

---

### 4. Increase Bulk Purchasing

Where appropriate, negotiate larger purchase orders to reduce procurement costs.

---

### 5. Promote Slow-Selling Brands

Develop targeted promotional campaigns for brands with

- High margins
- Low sales volume

---

### 6. Monitor Vendor KPIs

Track important performance indicators such as

- Gross Profit
- Profit Margin
- Stock Turnover
- Purchase Volume
- Sales Volume

through interactive dashboards.

---

# 📌 Project Outcomes

This project successfully demonstrates:

- End-to-End Data Analytics Pipeline
- SQL-Based Data Aggregation
- Automated Data Ingestion
- Exploratory Data Analysis
- Statistical Validation
- Business Intelligence Dashboard Development
- Data-Driven Decision Making

---

# 🚀 Future Enhancements

Potential improvements include:

## Machine Learning

- Sales Forecasting
- Demand Forecasting
- Vendor Performance Prediction
- Inventory Optimization
- Customer Purchase Prediction

---

## Dashboard Improvements

- Real-time dashboard refresh
- Drill-through reports
- Predictive analytics
- KPI alerts
- Executive summary page

---

# 📚 Skills Demonstrated

This project demonstrates proficiency in:

### Programming

- Python
- SQL

### Data Analysis

- Pandas
- NumPy
- Exploratory Data Analysis
- Feature Engineering

### Databases

- SQLite
- SQLAlchemy

### Visualization

- Matplotlib
- Seaborn
- Power BI

### Statistics

- Descriptive Statistics
- Correlation Analysis
- Confidence Intervals
- Hypothesis Testing

### Business Intelligence

- KPI Analysis
- Vendor Performance Analysis
- Inventory Analytics
- Profitability Analysis

---


## 🙏 Acknowledgements

This project was developed as part of a comprehensive data analytics portfolio to demonstrate practical applications of:

- SQL
- Python
- Exploratory Data Analysis
- Statistical Analysis
- Business Intelligence
- Power BI

The analysis focuses on solving real-world business problems using data-driven decision-making and best practices in analytics.