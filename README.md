# E-Commerce Sales Intelligence: End-to-End Data Analysis

A complete data analysis pipeline on a 1,200-row e-commerce dataset — covering data cleaning, exploratory analysis, SQL querying, and an interactive business dashboard.

---

## Project Overview

This project simulates a real-world analyst workflow: starting from a raw, dirty dataset and progressing through every stage of analysis to produce actionable business insights. The final output is a Power BI dashboard that translates cleaned data into executive-level decisions.

---

## Dataset

| Property | Details |
|---|---|
| Domain | E-Commerce Orders |
| Rows | 1,200 |
| Columns | 14 |
| Period | 2023 - 2025 |
| Key Fields | OrderID, Date, CustomerID, Product, Quantity, UnitPrice, TotalPrice, OrderStatus, PaymentMethod, ReferralSource, CouponCode |

---

## Project Structure

```
ecommerce-data-analysis/
│
├── data/
│   ├── dataset_raw.xlsx           # Original unprocessed dataset
│   └── dataset_cleaned.xlsx       # Production-ready cleaned dataset
│
├── notebooks/
│   ├── project1_cleaning.ipynb    # Data cleaning and preparation
│   ├── project2_eda.ipynb         # Exploratory data analysis
│   └── project3_sql.ipynb         # SQL-based querying and aggregation
│
├── dashboard/
│   └── ecommerce_dashboard.pbix   # Power BI dashboard file
│
├── reports/
│   └── change_log.pdf             # Data cleaning audit trail
│
└── README.md
```

---

## Phase 1 — Data Cleaning and Preparation

**Goal:** Transform raw data into a production-ready dataset with zero errors.

**What was done:**

| Change ID | Issue | Action | Impact |
|---|---|---|---|
| CR001 | 309 null values in CouponCode | Filled with "No Coupon" — nulls indicated no coupon used, not missing data | Preserved 309 records (25.75% of dataset) |
| CR002 | Duplicate OrderID audit | Verified all 1,200 OrderIDs are unique | 0 duplicates confirmed |
| CR003 | Inconsistent text casing | Applied proper case standardization across Product, PaymentMethod, OrderStatus, ReferralSource | 0 casing errors |
| CR004 | Date format inconsistency | Converted all dates to ISO 8601 format (YYYY-MM-DD) | 0 date format errors |
| CR005 | Floating point price errors | Rounded UnitPrice and TotalPrice to 2 decimal places | 0 financial precision errors |

**Verification Gate:** 0 nulls, 0 duplicates, 1,200 rows fully preserved.

**Tools:** Python, Pandas, openpyxl, ReportLab

---

## Phase 2 — Exploratory Data Analysis

**Goal:** Understand the shape, distribution, and patterns within the cleaned data.

**Analysis performed:**
- Descriptive statistics across all numeric columns (mean, median, std, min, max)
- Distribution analysis — identified right-skewed TotalPrice distribution
- Outlier detection using the IQR method (Q1 - 1.5×IQR / Q3 + 1.5×IQR)
- Boxplot visualization across Quantity, UnitPrice, TotalPrice
- Pearson correlation heatmap across numeric variables

**Key findings:**

| Metric | Value | Insight |
|---|---|---|
| Total Revenue | Rs. 12,64,761.96 | Baseline business scale |
| Mean Order Value | Rs. 1,053 | Pulled up by high-value outliers |
| Median Order Value | Rs. 823 | True central tendency — right-skewed data |
| Cancelled Orders | 250 | 20.8% of all orders |
| Returned Orders | 247 | 20.6% of all orders |
| Delivered Orders | 231 | Lowest among all statuses |
| Coupon Usage | 74.2% | Heavy discount dependency |
| Top Acquisition Channel | Instagram (259 orders) | Highest volume source |

**Tools:** Python, Pandas, Matplotlib, Seaborn, NumPy

---

## Phase 3 — SQL Data Analysis

**Goal:** Extract business insights using structured SQL queries on the cleaned dataset.

**Queries implemented:**

| Query | Concept Used | Business Question Answered |
|---|---|---|
| Top 10 orders by value | SELECT + ORDER BY DESC | Which orders drove the most revenue? |
| Delivered orders only | WHERE + equality filter | What does successful order data look like? |
| High-value orders > Rs.2000 | WHERE + comparison | Who are the high-value customers? |
| Revenue by product | GROUP BY + SUM + AVG | Which products generate the most revenue? |
| Orders by status | GROUP BY + COUNT | How severe is the cancellation problem? |
| Referral source performance | GROUP BY + SUM | Which channels drive the most orders? |
| Payment methods > 200 orders | HAVING | Which payment methods are dominant? |
| Coupon vs no-coupon revenue | CASE WHEN | Does discounting hurt avg order value? |
| Monthly revenue trend | SUBSTR + GROUP BY | Is there seasonal revenue variation? |

**Key SQL concept applied:** Logical execution order (FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY) — used to correctly structure all aggregate queries and avoid alias-related errors.

**Tools:** Python, Pandas, SQLite3

---

## Phase 4 — Power BI Dashboard

**Goal:** Translate all findings into an interactive, executive-level business dashboard.

**Dashboard pages:**

**Page 1 — Revenue Overview**
- Total revenue, total orders, avg order value KPI cards
- Monthly revenue trend line chart (2023-2025)
- Revenue by product category bar chart

**Page 2 — Order Health**
- Order status breakdown donut chart
- Cancelled vs Returned vs Delivered comparison
- Revenue at risk from non-delivered orders

**Page 3 — Customer and Channel Analysis**
- Referral source funnel chart
- Coupon vs non-coupon order volume and avg value comparison
- Payment method distribution

**Tools:** Power BI Desktop, DAX

---

## Business Recommendations

Based on the full analysis:

1. **Fulfillment crisis** — 497 orders (41.4%) are Cancelled or Returned vs only 231 Delivered. Immediate investigation into logistics and product quality is required.

2. **Discount dependency** — 74.2% of customers rely on coupons to purchase. A/B testing reduced discount rates is recommended before any coupon policy change.

3. **Channel investment** — Instagram drives the highest order volume (259 orders). Reallocating budget from underperforming channels to Instagram is data-backed.

4. **Pricing strategy** — Near-zero correlation between UnitPrice and Quantity sold indicates customers are not highly price-sensitive. Selective price increases on high-demand products are viable.

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python 3 | Core analysis language |
| Pandas | Data manipulation and cleaning |
| Matplotlib / Seaborn | Statistical visualization |
| SQLite3 | In-memory SQL querying |
| Jupyter Notebook | Development environment |
| Power BI Desktop | Interactive dashboard |
| openpyxl | Excel file I/O |
| ReportLab | PDF change log generation |

---

## Key Skills Demonstrated

Data cleaning and validation, missing value strategy, duplicate detection, exploratory data analysis, statistical distribution analysis, outlier detection (IQR), correlation analysis, SQL querying (SELECT, WHERE, GROUP BY, HAVING, CASE WHEN), data aggregation, business insight translation, dashboard design

---

## Author

**Shubham**
B.Tech Computer Science Engineering
GitHub: [@shubhammgits](https://github.com/shubhammgits)
LinkedIn: [linkedin.com/in/shhshubham](https://linkedin.com/in/shhshubham)