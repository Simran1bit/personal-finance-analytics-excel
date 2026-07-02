# Project Documentation

---

# 1. Dataset Overview

Dataset contains personal financial transactions.

Original Size

Rows : 15,900

Columns : 9

The dataset intentionally contains multiple inconsistencies including:

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

## Step 1

Problem

Duplicate Transactions

Observation

Duplicate transaction IDs were found.

Decision

Removed duplicate rows while keeping the first occurrence.

Formula / Tool

Excel Remove Duplicates

---

## Step 2

Problem

Inconsistent City Names

Examples

Lucknow
LUC
lucknow

Observation

Multiple abbreviations represented the same city.

Decision

Created a standardized city mapping.

Functions Used

LOWER

TRIM

XLOOKUP

---

## Step 3

Problem

Payment Modes

Examples

B
Bank Transfer

U
UPI

Observation

Payment modes were abbreviated.

Decision

Mapped abbreviations to full names.

Functions Used

IFS

LEFT

SEARCH

XLOOKUP

---

## Step 4

Problem

Category Column

Observation

Contained spelling mistakes and inconsistent labels.

Examples

educatn

educ

education

Decision

Created category mapping sheet.

Used XLOOKUP for final categories.

Reason

Mapping table is reusable and easier to maintain.

---

## Step 5

Problem

Mixed Date Formats

Examples

dd-mm-yyyy

mm/dd/yyyy

blank

Issue

Formatting does not convert text into actual Excel dates.

Solution

Converted text dates into proper Excel date values.

Created

Date Flag

Available

Missing

Functions Used

DATE

YEAR

MONTH

ISNUMBER

---

## Step 6

Problem

Amount Column

Issues

Currency symbols

Negative values

Text values

Placeholder values

Examples

₹4500

Rs.3000

INR 2500

999999

-500

Decision

Removed currency symbols

Converted to numeric

Converted negatives using ABS

Removed invalid placeholder records

Functions Used

NUMBERVALUE

SUBSTITUTE

ABS

---

## Step 7

Problem

Outlier Detection

Initial Mistake

Calculated IQR using both income and expense.

Result

Incorrectly labelled 44% of records as outliers.

Correction

Calculated separate IQR limits for:

Income

Expense

Lesson Learned

Different distributions should not share the same outlier threshold.

---

## Step 8

Problem

Category Validation

Observation

Notes often represented actual category.

Example

Category

Rent

Notes

Coffee

Decision

Created Category Mapping table using Notes.

Applied XLOOKUP.

---

## Step 9

Final Dataset

Rows

14,430

Columns

9

Ready for Analysis

Yes

---

# 3. Feature Engineering

Created

Month

Year

Date Flag

Final Category

Budget Mapping

---

# 4. Analysis

Performed

Financial Summary

Budget Analysis

Category Analysis

Monthly Trends

Payment Behaviour

Income Sources

City Spending

Transaction Frequency

Largest Financial Events

---

# 5. Dashboard

KPIs

Charts

Insights

Interactive Filters

Year

Month

---

# 6. Lessons Learned

This project demonstrated that:

Cleaning consumes significantly more time than visualization.

A reusable mapping table is preferable to hardcoded formulas.

Business understanding is necessary before removing outliers.

Missing values should not always be deleted.

Documentation is as important as dashboard creation.
