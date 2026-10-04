# Retail Sales Analytics Dashboard

An end-to-end retail sales analytics project that cleans transaction data with Python, calculates business KPIs, and presents interactive insights through Power BI.

## Project Overview

This project analyzes retail transaction data to understand sales performance, category contribution, customer behavior, and monthly revenue trends. The workflow follows a simple analytics pipeline:

**Raw Kaggle Dataset → Python/Pandas Cleaning & EDA → Cleaned CSV → Power BI → DAX KPIs → Interactive Dashboard → Business Insights**

## Business Question

- Which product categories contribute the most revenue?
- How does revenue change over time?
- What are the key sales KPIs such as total revenue, quantity sold, number of orders, and average order value?
- How can an interactive dashboard help stakeholders identify strong and weak sales periods?

## Key Metrics / KPIs

| KPI | Final Value |
|---|---:|
| Total Revenue | ₹456,000 |
| Total Quantity Sold | 2,514 |
| Total Orders | 1,000 |
| Average Order Value (AOV) | ₹456.00 |
| Unique Customers | 1,000 |

## Final Business Insights

### 1. Electronics is the leading revenue category
Electronics generated **₹156,905**, approximately **34.4%** of total revenue, making it the highest-revenue category.

### 2. Clothing is a close second
Clothing generated **₹155,580**, approximately **34.1%** of total revenue. The small gap between Electronics and Clothing indicates that both categories are important revenue drivers.

### 3. Beauty has the smallest revenue share
Beauty generated **₹143,515**, approximately **31.5%** of total revenue. Although it contributes less revenue than the other two categories, it remains a significant part of the portfolio.

### 4. May 2023 was the strongest month
The highest monthly revenue occurred in **May 2023**, with **₹53,150** in revenue. This period can be investigated further for promotions, customer demand, or category-level drivers.

### 5. Revenue is broadly balanced across categories
The three categories have relatively similar revenue contributions, with no single category dominating the business. This suggests that the business has a diversified category mix rather than depending entirely on one category.

### 6. Customer gender revenue is relatively balanced
Female customers contributed **₹232,840**, while male customers contributed **₹223,160**. The dashboard can use this dimension for additional customer-segment analysis.

## Technical Stack

### Data & Analysis
- **Python** — data cleaning and exploratory analysis
- **Pandas** — data loading, transformation, aggregation, and validation
- **Jupyter Notebook** — reproducible analysis workflow
- **Matplotlib** — charts and exploratory visualizations

### Business Intelligence
- **Microsoft Power BI Desktop** — interactive dashboard development
- **DAX** — KPI and measure calculations
- **Power Query** — data import and transformation

### Version Control
- **Git**
- **GitHub**

## DAX Measures

### Total Revenue

```DAX
Total Revenue = SUM('retail_sales_dataset'[Total Revenue])
```

### Average Order Value

```DAX
AOV = DIVIDE(
    [Total Revenue],
    DISTINCTCOUNT('retail_sales_dataset'[Transaction ID])
)
```

### Optional Total Quantity

```DAX
Total Quantity = SUM('retail_sales_dataset'[Quantity])
```

> If your Power BI table has a different name, replace `retail_sales_dataset` with the exact table name shown in the Fields pane.

## Dashboard Features

The final Power BI report contains:

- **Card visuals** for top-level KPIs
  - Total Revenue
  - AOV
  - Total Quantity / Orders
- **Line or Area chart** for monthly revenue trends
- **Bar chart** for revenue by product category
- **Date slicer** for dynamic time filtering
- Interactive cross-filtering between visuals

> The dataset does not contain a `Region` column, so the dashboard uses available dimensions such as Date, Product Category, and Gender for filtering.

## Dataset

The dataset contains **1,000 retail transactions** and the following fields:

- Transaction ID
- Date
- Customer ID
- Gender
- Age
- Product Category
- Quantity
- Price per Unit
- Total Amount
- Total Revenue *(derived during cleaning)*

`Total Revenue` is calculated as:

**Total Revenue = Price per Unit × Quantity**

## Project Structure

```text
retail-sales-analytics-dashboard/
│
├── data/
│   └── cleaned_retail_sales.csv
│
├── notebooks/
│   └── retail_analysis.ipynb
│
├── dashboard/
│   └── retail_sales_dashboard.png
│
├── README.md
└── .gitignore
```

## How to Reproduce the Analysis

1. Clone or download this repository.
2. Open `notebooks/retail_analysis.ipynb` in Jupyter Notebook or VS Code.
3. Load the raw/cleaned retail dataset with Pandas.
4. Check row count, column names, missing values, and duplicate rows.
5. Create the derived `Total Revenue` field.
6. Save the cleaned dataset as `cleaned_retail_sales.csv`.
7. Open Power BI Desktop.
8. Import the cleaned CSV.
9. Create the DAX measures shown above.
10. Build the KPI cards, monthly trend chart, category bar chart, and slicers.
11. Use the dashboard to explore trends and category performance.

## Data Quality Checks

The original dataset was checked for:

- Row count
- Column names and consistency
- Missing values
- Duplicate rows
- Derived revenue calculation

The final cleaned file preserves the transaction-level records while adding a calculated `Total Revenue` field for analytics.

## Limitations

- The dataset contains category-level information rather than individual product names.
- There is no geographic/region field, so regional analysis is not possible from this dataset alone.
- The data represents a limited retail sample, so insights should not automatically be generalized to a larger business without additional data.
- The dataset does not contain detailed marketing, inventory, discount, or competitor-price information.

## Future Improvements

- Add region/store information for geographic analysis.
- Add product-level data for top-product analysis.
- Include discounts, promotions, and inventory levels.
- Add customer segmentation and repeat-purchase analysis.
- Build automated data refresh and scheduled reporting.
- Extend the dashboard with forecasting and anomaly detection.

## Conclusion

This project demonstrates a complete beginner-to-intermediate business analytics workflow: raw transaction data is validated and transformed with Python, business KPIs are calculated using DAX, and the results are communicated through an interactive Power BI dashboard.

The final analysis shows **₹456,000** in revenue across **1,000 transactions**, with an **AOV of ₹456.00**. Electronics is the leading revenue category, while the overall category mix remains relatively balanced. The monthly trend also highlights **May 2023** as the strongest sales period.

---

## Author

**Priyal Dalal**

Retail Sales Analytics Project | Python | Pandas | Power BI | DAX | GitHub
