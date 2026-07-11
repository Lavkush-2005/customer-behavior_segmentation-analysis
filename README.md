# Customer Behavior & Segmentation Analysis

End-to-end analysis of 3,900+ customer shopping transactions — from raw data cleaning in Python, to business-question SQL queries in PostgreSQL, to an interactive Power BI dashboard for stakeholders.

## Overview

This project explores customer shopping behavior across demographics, product categories, and shipping/subscription preferences. The goal was to turn a raw transactional dataset into actionable insights on revenue drivers, customer segments, and product performance — the kind of analysis a retail/e-commerce team would use to guide marketing and retention decisions.

**Pipeline:** `Python (cleaning + feature engineering) → PostgreSQL (SQL analysis) → Power BI (dashboard)`

## Dataset

- **Source:** `data/customer_shopping_behavior.csv`
- **Size:** ~3,900 rows, 18 columns
- **Fields:** Customer ID, Age, Gender, Item Purchased, Category, Purchase Amount, Location, Size, Color, Season, Review Rating, Subscription Status, Shipping Type, Discount Applied, Previous Purchases, Payment Method, Frequency of Purchases

## Project Workflow

### 1. Data Cleaning & Feature Engineering (Python)
`notebooks/Customer-Segmentation-and-Purchase-Behavior-Analysis.ipynb`
- Handled missing review ratings using category-wise median imputation
- Standardized column names for consistency
- Engineered an `age_group` feature (Young Adult / Adult / Middle Age / Senior) using quantile binning
- Converted purchase frequency labels (e.g., "Fortnightly", "Monthly") into a numeric `purchase_frequency_days` field
- Loaded the cleaned dataset into PostgreSQL via SQLAlchemy

### 2. Business Analysis (SQL)
`sql/customer_behavior_analysis.sql`

10 queries answering real business questions, including:
- Revenue split by gender
- Customers who used a discount but still spent above average
- Top-rated products
- Standard vs. Express shipping — average spend comparison
- Subscriber vs. non-subscriber spend and revenue
- Products with the highest discount usage
- Customer segmentation into **New / Returning / Loyal** tiers based on purchase history
- Top 3 best-selling products per category
- Correlation between repeat purchases and subscription status
- Revenue contribution by age group

### 3. Dashboard (Power BI)
`dashboard/customer_behavior_dashboard.pdf`

An interactive dashboard with slicers for **Subscription Status, Gender, Category, and Shipping Type**, featuring:
- KPI cards: total customers, average review rating, average purchase amount
- Subscription status breakdown
- Revenue and sales by product category, season, and age group

## Key Insights

- Non-subscribers make up **73%** of the customer base — a clear opportunity for subscription-focused marketing.
- Average purchase amount across all customers is **$59.76**, with average review rating at **3.75/5**.
- Clothing and Accessories generate the highest revenue among product categories.
- Repeat buyers (5+ previous purchases) show a distinct subscription pattern, useful for retention targeting.

## Tools & Tech Stack

`Python (pandas, SQLAlchemy)` · `PostgreSQL` · `SQL` · `Power BI`

## Repository Structure

```
customer-behavior-segmentation-analysis/
├── dashboard/
│   └── customer_behavior_dashboard.pdf
├── data/
│   └── customer_shopping_behavior.csv
├── notebooks/
│   └── Customer-Segmentation-and-Purchase-Behavior-Analysis.ipynb
├── sql/
│   └── customer_behavior_analysis.sql
├── LICENSE
└── README.md
```

## How to Reproduce

1. Clone the repo and install dependencies:  customer_behavior_dashboard.pdf
   ```bash
   pip install pandas sqlalchemy psycopg2-binary
   ```
2. Run the notebook in `notebooks/` to clean the data and load it into a local PostgreSQL database.
3. Run the queries in `sql/customer_behavior_analysis.sql` against the loaded table.
4. Open `dashboard/customer_behavior_dashboard.pdf` to view the final Power BI dashboard (or connect Power BI Desktop to your PostgreSQL instance to rebuild it live).

## Author
Lavkush,
Feel free to connect if you have questions or feedback on this project.

## Linkedin https://www.linkedin.com/in/lavkush2005kumar/
