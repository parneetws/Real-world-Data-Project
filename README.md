# Real-World Data Project — Retail Sales Analysis

End-to-end data science project on the **Superstore Sales** dataset — a real-world retail dataset covering orders, customers, products, and profits across regions and years.

-----

## Dataset

**Superstore Sales** — 9,994 rows, 21 columns

```
https://raw.githubusercontent.com/dsrscientist/dataset1/master/superstore_sales.csv
```

Covers: orders, customers, products, categories, regions, shipping, discounts, sales, and profit.

-----

## Domain

**Retail / Business Analytics**

Questions this project answers:

- Which products and categories are actually profitable?
- Does offering discounts hurt or help profit?
- Which regions and customer segments drive revenue?
- How has the business grown year over year?
- Can we predict profit from order details?

-----

## Setup

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
python retail_analysis.py
```

-----

## What the Script Does

### 1. Data Cleaning

- Standardizes column names
- Parses `order_date` and `ship_date` to datetime
- Computes `ship_lag` (days between order and shipment)
- Drops nulls and duplicates
- Extracts `year`, `month`, `quarter` features
- Adds `profit_margin` column

### 2. Business Summary (Terminal)

- Total orders, customers, revenue, profit, avg margin
- Revenue & profit broken down by category
- Top 5 and bottom 5 sub-categories by profit
- Sales and profit by region

### 3. Profit Prediction Model

Uses **Linear Regression** to predict profit per order.

**Features used:**

|Feature    |Description               |
|-----------|--------------------------|
|`sales`    |Order revenue             |
|`quantity` |Units ordered             |
|`discount` |Discount applied          |
|`ship_lag` |Days to ship              |
|`category` |Product category (encoded)|
|`region`   |Sales region (encoded)    |
|`ship_mode`|Shipping method (encoded) |

**Evaluation:** MAE (Mean Absolute Error) and R² score

### 4. Dashboard — 10 Visualizations

|Plot                        |What it shows                        |
|----------------------------|-------------------------------------|
|Monthly Trend (dual axis)   |Revenue + profit over time           |
|Sales by Category (pie)     |Category revenue share               |
|Profit by Sub-Category      |Horizontal bar, red = loss-making    |
|Discount vs Profit (scatter)|Color-coded by sales amount          |
|Sales by Region             |Revenue per region                   |
|Profit Margin by Segment    |Category + customer segment breakdown|
|Quarterly Sales by Year     |YoY quarterly comparison             |
|Shipping Lag Distribution   |Days to ship by shipping mode        |
|Actual vs Predicted Profit  |Model scatter plot with R²           |
|Feature Coefficients        |Which features drive profit up/down  |

-----

## Key Findings

- **Discounts above ~20% consistently produce negative profit** — the discount vs profit scatter makes this very clear
- **Tables and Bookcases are loss-making** sub-categories despite decent sales volume
- **Technology** is the strongest category by both revenue and margin
- **Q4 consistently peaks** across all years — seasonal holiday effect
- **West region** leads in overall sales and profit
- The regression model confirms: **discount is the biggest negative driver** of profit

-----

## Files

```
├── retail_analysis.py    # main script
├── retail_dashboard.png  # 10-panel output dashboard (generated on run)
└── README.md             # this file
```

-----

## How This Fits Into the Project Series

|Project            |Focus                                        |
|-------------------|---------------------------------------------|
|Data Cleaning      |Preprocessing & missing values               |
|EDA                |Statistical exploration & patterns           |
|ML Modeling        |Prediction & model evaluation                |
|**Retail Analysis**|**End-to-end, real-world domain application**|