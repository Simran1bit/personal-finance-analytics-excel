# 📊 Personal Finance Analytics Dashboard (Microsoft Excel)

An end-to-end Data Analytics project built entirely in Microsoft Excel.

The project demonstrates the complete analytics workflow—from cleaning a messy financial dataset to building an interactive dashboard that provides business insights into income, expenses, budgeting, payment behavior, and spending patterns.

---

## Dashboard Preview

![Dashboard](dashboard.png)

---

# Project Overview

The original dataset contained several real-world data quality issues including:

- Duplicate records
- Missing dates
- Missing categories
- Missing payment modes
- Missing locations
- Mixed date formats
- Currency symbols and text in amount column
- Negative values
- Placeholder values (99999)
- Category inconsistencies
- Payment mode inconsistencies

The objective was to transform this raw dataset into an analysis-ready dataset and create an interactive Excel dashboard.

---

# Dataset

Source:

[Kaggle - BudgetWise Finance Dataset]

(Replace this with the original Kaggle URL.)

Original Records : **15,900**

Final Records : **14,430**

---

# Dataset Summary

| Description | Count |
|-------------|------:|
| Raw Records | 15,900 |
| Final Records | 14,430 |
| Records Removed | 1,470 |

---

# Data Cleaning Process

The following cleaning operations were performed:

### Duplicate Removal
- Removed duplicate transaction records.

### Date Cleaning
- Standardized multiple date formats.
- Added a Date Flag column to distinguish available and missing dates.

### Category Cleaning
- Standardized category names.
- Built a mapping table.
- Used XLOOKUP to correct inconsistent categories.

### Payment Mode Cleaning
- Standardized payment modes.
- Replaced missing values with **Unknown**.

### Location Cleaning
- Standardized city names.
- Replaced missing locations with **Unknown**.

### Amount Cleaning
- Removed currency symbols.
- Converted text values into numeric format.
- Corrected negative values.
- Removed invalid placeholder records.
- Performed IQR-based outlier analysis.

---

# Excel Functions Used

- SUM
- SUMIF
- SUMIFS
- COUNTIF
- COUNTIFS
- IF
- IFS
- XLOOKUP
- FILTER
- UNIQUE
- LARGE
- INDEX
- MATCH
- MODE
- TEXT
- YEAR
- MONTH
- TRIM
- LOWER
- UPPER
- SUBSTITUTE
- SEARCH
- NUMBERVALUE

---

# Dashboard Features

✔ Financial Summary

- Total Income
- Total Expenses
- Net Balance
- Savings Rate
- Total Transactions

✔ Spending Analysis

- Category-wise Spending
- Monthly Expense Trend
- Budget vs Actual Spending

✔ Behavioral Analysis

- Payment Method Distribution
- City-wise Spending
- Income vs Expense Trend

✔ Key Insights

Automatically generated business insights including:

- Highest spending category
- Most preferred payment method
- Highest spending month
- Highest spending city

---

# Business Questions Answered

- How much income and expense occurred?
- Which category contributes the highest spending?
- Which payment method is most preferred?
- Are expenses within budget?
- Which month records the highest spending?
- Which city contributes the highest expenses?
- What are the major income sources?

---

# Skills Demonstrated

- Data Cleaning
- Data Validation
- Data Transformation
- Excel Dashboard Design
- Business Analysis
- Financial Analytics
- Data Visualization
- KPI Reporting

---

# Documentation

Detailed cleaning decisions, formulas, validation rules and business logic are available in:

**description.md**

---

# Tools Used

- Microsoft Excel
- Excel Charts
- Data Validation
- Conditional Formatting

---

# Project Outcome

Successfully transformed a messy financial dataset into an analysis-ready dataset and developed a professional Excel dashboard capable of answering key financial and business questions through interactive visualizations and KPI reporting.
