# End-to-End-Sales-Insights-Trend-Analysis-Dashboard

### Dashboard Link : https://app.powerbi.com/groups/me/reports/0eb009a7-718b-49b2-ae89-f37594cd5feb/d310e5b2a851965d3936?experience=power-bi

## Problem Statement
Businesses often generate large volumes of sales transactions but struggle to identify:

- High-performing products
- Profitable regions
- Revenue trends
- Impact of promotions
- Sales-performance relationships

This dashboard was developed to convert raw sales data into actionable business insights.

---

## Tools Used

- Power BI
- Power Query
- DAX
- Microsoft Excel

---

# Dashboard Pages

## 1. Executive Overview

### Objective
Provide a high-level summary of overall business performance.

### Visuals Included
- KPI Cards
  - Total Sales
  - Net Sales
  - Profit
  - Units Sold
- Sales Trend Analysis
- Geographic Sales Map
- Date Slicers

### Business Value
Allows stakeholders to quickly monitor overall sales performance and profitability.

---

## 2. Product Performance Analysis

### Objective
Identify top-performing and underperforming products.

### Visuals Included
- Product-wise Revenue Analysis
- Product-wise Profit Analysis
- Top Products Ranking
- Sales vs Profit Scatter Plot

### Business Value
Helps identify products contributing most to revenue and profitability.

---

## 3. Regional Performance Analysis

### Objective
Compare sales performance across cities.

### Visuals Included
- City-wise Sales Distribution
- City-wise Profit Analysis
- Geographic Heat Map

### Business Value
Supports regional performance evaluation and strategic decision-making.

---

# Data Preparation Process

The dataset was transformed using Power Query through the following ETL workflow:

## Step 1: Data Import
- Imported raw sales data from Excel.

## Step 2: Data Cleaning
- Promoted headers.
- Corrected data types.
- Standardized column formats.

## Step 3: Product Data Enrichment
- Merged Product Dimension table using Product ID.
- Imported product pricing information.

## Step 4: Promotion Data Enrichment
- Merged Promotion Dimension table using Promotion ID.
- Imported discount percentage information.

## Step 5: Missing Value Handling
- Replaced null promotion percentages with 0.

## Step 6: Business Calculations
Created:
- Total Sales
- Discount Amount
- Net Sales
- Profit

## Step 7: Record Identification
- Generated unique Order IDs.

## Step 8: Final Validation
- Removed redundant columns.
- Verified calculated values.

---

# Data Model

## Star Schema Design

### Fact Table
Fact Sales

Contains:
- Order ID
- Product ID
- Promotion ID
- Units Sold
- Total Sales
- Discount
- Net Sales
- Profit

### Dimension Tables

#### Dim Product
Contains:
- Product ID
- Product Name
- Category
- Price Per Unit

#### Dim Promotion
Contains:
- Promotion ID
- Promotion Percentage

#### Dim Date
Contains:
- Date Attributes
- Month
- Quarter
- Year

---

# DAX Measures

## Total Sales

```DAX
Total Sales = SUM('Fact Sales'[Total Sales])
```

## Total Profit

```DAX
Total Profit = SUM('Fact Sales'[Profit])
```

## Net Sales

```DAX
Net Sales = SUM('Fact Sales'[Net Sales])
```

## Total Orders

```DAX
Total Orders = COUNT('Fact Sales'[Order ID])
```

## Average Order Value

```DAX
Average Order Value =
DIVIDE(
    [Net Sales],
    [Total Orders]
)
```

---

# Key Insights

## Product Insights

- Apple iPhone 14 emerged as the highest revenue-generating product.
- A small group of products contributed a significant portion of total revenue.

## Regional Insights

- Sales performance varied significantly across cities.
- Some cities generated high sales but comparatively lower profitability.

## Profitability Insights

- Net Sales and Profit showed a strong positive relationship.
- Products with higher sales generally contributed more to overall profit.

## Promotion Insights

- Promotions influenced sales volume across multiple product categories.
- Orders without promotions were handled by assigning a 0% discount during data preparation.

---

# Project Workflow

Raw Data
→ Data Cleaning
→ Data Modeling
→ Data Transformation
→ KPI Engineering
→ Dashboard Development
→ Business Insight Generation

---

# Visuals

## Executive Overview

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/14c3b612-e682-471c-9004-2e6a9708288b" />



## Product Analysis

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bb3ccac4-2807-4636-ae5f-6ca0d3e84501" />


## Comparison Sales/Profit/Quantity Analysis

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/06580961-2d90-44fa-9b54-1084592c4914" />


---

# Author

Rajveer Tamrakar

Aspiring Data Analyst | Power BI | SQL | Excel | Python
