# DecodeLabs Data Analytics Internship

Repository containing all project submissions for the Data Analytics Internship at DecodeLabs.

---

## Projects

### Project 1 — Data Cleaning and Preparation

**Goal:** Clean a raw e-commerce dataset by handling missing values, duplicates, and formatting inconsistencies.

| Phase | Task | Result |
|---|---|---|
| Phase 1 | Strategic Imputation — filled 309 null CouponCode values with "No Coupon" | 309 records preserved |
| Phase 2 | Integrity Audit — verified all OrderIDs for duplicates | 0 duplicates found |
| Phase 3 | Standardization — proper casing, ISO 8601 dates, 2-decimal price rounding | 0 format errors |

**Deliverables:** Cleaned dataset (`Dataset_Cleaned.xlsx`), PDF Change Log documenting all 5 changes with impact and status.

**Tools:** Python, Pandas, openpyxl, ReportLab

---

### Project 2 — Exploratory Data Analysis (EDA)

**Goal:** Analyze the cleaned dataset to uncover patterns, distributions, trends, and business insights.

**Analysis performed:**
- Descriptive statistics (mean, median, std) across Quantity, UnitPrice, TotalPrice, ItemsInCart
- Distribution analysis — identified right-skewed TotalPrice (Mean Rs.1053 vs Median Rs.823)
- Outlier detection using IQR method with boxplot visualization
- Pearson correlation heatmap across numeric columns
- Business insights using the "So What?" framework

**Key findings:**
- Total revenue: Rs.12,64,761.96
- 497 out of 1,200 orders were Cancelled or Returned vs only 231 Delivered
- 74.2% of customers used a coupon — high discount dependency
- Instagram was the top acquisition channel with 259 orders

**Tools:** Python, Pandas, Matplotlib, Seaborn, NumPy

---

### Project 3 — SQL Data Analysis

**Goal:** Use SQL queries to extract business insights from the dataset using SELECT, WHERE, GROUP BY, HAVING, and aggregation functions.

**Queries implemented:**
- Basic SELECT with LIMIT for data preview
- WHERE clause filtering — by order status, price threshold, and multiple conditions
- GROUP BY with COUNT, SUM, AVG — revenue by product, orders by status, referral source performance
- HAVING — filter groups by aggregate thresholds
- Advanced queries — CASE WHEN for coupon segmentation, SUBSTR for monthly revenue trends

**Tools:** Python, Pandas, SQLite3

---

## Dataset

- **File:** `Dataset_for_Data_Analytics.xlsx`
- **Rows:** 1,200
- **Columns:** 14
- **Domain:** E-commerce orders (2023-2025)

---

## Tech Stack

| Tool | Usage |
|---|---|
| Python 3 | Core language |
| Pandas | Data manipulation |
| Matplotlib / Seaborn | Visualization |
| SQLite3 | SQL querying |
| Jupyter Notebook | Development environment |
| openpyxl | Excel I/O |

---

## Author

**Shubham**
B.Tech CSE — GGSIPU (2023-2027)
GitHub: [@shubhammgits](https://github.com/shubhammgits)