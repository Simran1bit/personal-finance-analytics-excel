# Project Documentation

---

# 1. Dataset Overview

The dataset contains personal financial transactions.

### Original Dataset Size

- **Rows:** 15,900
- **Columns:** 9

### Dataset Issues

The dataset intentionally contains multiple inconsistencies, including:

- Missing values
- Mixed date formats
- Currency symbols
- Duplicate records
- Incorrect categories
- Placeholder values
- Negative values
- Missing payment methods

---

# 2. Cleaning Workflow

## Step 1 – Duplicate Transactions

**Problem:**  
Duplicate transaction IDs were found.

**Observation:**  
Some transactions appeared more than once.

**Decision:**  
Removed duplicate records while keeping the first occurrence.

**Tool Used:**  
- Remove Duplicates (Excel)

---

## Step 2 – Standardizing City Names

**Problem:**  
City names were inconsistent.

**Examples:**
- Lucknow
- LUC
- lucknow

**Observation:**  
Different abbreviations and text cases represented the same city.

**Decision:**  
Created a standardized city mapping table.

**Functions Used:**
- LOWER
- TRIM
- XLOOKUP

---

## Step 3 – Cleaning Payment Modes

**Problem:**  
Payment methods were stored using abbreviations.

**Examples:**

| Original | Standardized |
|----------|--------------|
| B | Bank Transfer |
| U | UPI |

**Observation:**  
Abbreviated values reduced readability and consistency.

**Decision:**  
Mapped abbreviations to their full payment method names.

**Functions Used:**
- IFS
- LEFT
- SEARCH
- XLOOKUP

---

## Step 4 – Standardizing Categories

**Problem:**  
Category names contained spelling mistakes and inconsistent labels.

**Examples:**
- educatn
- educ
- education

**Observation:**  
The same category appeared under multiple names.

**Decision:**  
Created a separate category mapping table and standardized all categories using XLOOKUP.

**Reason:**  
A mapping table is reusable, scalable, and easier to maintain than hardcoded formulas.

---

## Step 5 – Cleaning Date Values

**Problem:**  
Dates were stored in multiple formats.

**Examples:**
- dd-mm-yyyy
- mm/dd/yyyy
- blank

**Issue:**  
Changing the cell format does not convert text into actual Excel dates.

**Decision:**  
Converted text dates into proper Excel date values.

**Additional Features Created:**
- Date Flag
  - Available
  - Missing

**Functions Used:**
- DATE
- YEAR
- MONTH
- ISNUMBER

---

## Step 6 – Cleaning Amount Values

**Problem:**  
The Amount column contained multiple formatting issues.

**Issues Identified:**
- Currency symbols
- Negative values
- Text values
- Placeholder values

**Examples:**
- ₹4500
- Rs.3000
- INR 2500
- 999999
- -500

**Decision:**
- Removed currency symbols
- Converted values to numeric format
- Converted negative values using ABS()
- Removed invalid placeholder records

**Functions Used:**
- NUMBERVALUE
- SUBSTITUTE
- ABS

---

## Step 7 – Outlier Detection

**Problem:**  
Outliers needed to be identified.

**Initial Mistake:**  
Calculated the IQR using both income and expense transactions together.

**Result:**  
Approximately 44% of the records were incorrectly identified as outliers.

**Correction:**  
Calculated separate IQR thresholds for:
- Income
- Expense

**Lesson Learned:**  
Different distributions should not share the same outlier threshold.

---

## Step 8 – Category Validation

**Problem:**  
The Category column was often inconsistent with transaction Notes.

**Example:**

| Category | Notes |
|----------|-------|
| Rent | Coffee |

**Observation:**  
Transaction notes more accurately represented the actual spending category.

**Decision:**  
Created a Notes-to-Category mapping table and updated categories using XLOOKUP.

---

## Step 9 – Final Dataset

### Final Dataset Size

- **Rows:** 14,430
- **Columns:** 9

**Status:**  
✅ Ready for Analysis

---

# 3. Feature Engineering

The following additional fields were created:

- Month
- Year
- Date Flag
- Final Category
- Budget Mapping

---

# 4. Analysis Performed

The dataset was analyzed to answer various business and personal finance questions, including:

- Financial Summary
- Budget Analysis
- Category Analysis
- Monthly Trends
- Payment Behaviour
- Income Sources
- City Spending
- Transaction Frequency
- Largest Financial Events

---

# 5. Dashboard

The dashboard includes:

### KPIs
- Financial KPIs
- Spending KPIs

### Charts
- Category Analysis
- Monthly Trends
- Payment Behaviour
- Budget Distribution

### Interactive Filters
- Year
- Month

---

# 6. Lessons Learned

This project reinforced several important data analytics concepts:

- Data cleaning consumes significantly more time than visualization.
- A reusable mapping table is more maintainable than hardcoded formulas.
- Business understanding is necessary before removing outliers.
- Missing values should not always be deleted.
- Proper documentation is just as important as dashboard creation.
