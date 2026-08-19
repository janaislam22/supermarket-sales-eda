# supermarket-sales-eda
# Supermarket Sales – Exploratory Data Analysis

## Overview
This project performs data cleaning and exploratory data analysis (EDA) on a supermarket sales dataset containing 1,014 transactions across 3 branches (Cairo, Giza, Alex) over a 3-month period. The goal is to clean the raw data, engineer useful features, and extract business insights around sales performance, profitability, and customer satisfaction.

## Dataset
- **File:** `SuperMarket.csv`
- **Rows:** 1,014 transactions
- **Columns:** 17 (Invoice ID, Branch, City, Customer Type, Gender, Product Line, Unit Price, Quantity, Tax 5%, Sales, Date, Time, Payment, COGS, Gross Margin %, Gross Income, Rating)

## Data Cleaning
- Removed 14 duplicate rows.
- Fixed inconsistent `Gender` values (`F`/`M` → `Female`/`Male`).
- Standardized messy column names (e.g. `"   Customer type"` → `Customer_Type`).
- Converted `Unit_Price` and `Sales` to numeric types and imputed missing values (24 and 20 missing respectively) using the median.
- Converted `Date` to datetime format.
- Dropped `Gross_Margin_Percentage` — the column held a single constant value (4.76%) across all rows and added no analytical value.
- Standardized text formatting in the `Branch` column.

## Feature Engineering
- Extracted `Day`, `month`, and `year` from the `Date` column.
- Created a `satisfied based on rating` flag: transactions with a Rating ≥ 7 are labeled "Satisfied", otherwise "Not Satisfied".

## Analysis & Key Findings
- **Total sales:** ~318,834 (avg. transaction value: ~318.8)
- **Top city by sales:** Naypyitaw (~109,192)
- **Top branch by gross income:** Giza (~5,265)
- **Most profitable product line:** Food and Beverages (highest in both sales and gross income)
- **Sales by gender:** Female customers account for the higher share of total sales (~190,540)
- **Most common payment method:** E-wallet
- **Peak sales day:** Saturday
- **Peak sales month:** January
- **Overall customer satisfaction:** based on the ≥7 rating threshold
- **Satisfaction rate by branch:** Alex and Giza both hover around 52%, Cairo lower at ~45%

## Visualizations
Bar and pie charts were used to visualize:
- Sales by city
- Gross income by branch
- Revenue and profit by product line
- Sales distribution by gender
- Transaction count by payment method
- Satisfaction rate by branch
- Sales by day of week and by month
- Overall customer satisfaction split

## Tools & Libraries
- Python
- pandas
- matplotlib

## How to Run
1. Place `SuperMarket.csv` in the same directory as the notebook.
2. Install dependencies: `pip install pandas matplotlib`
3. Run the notebook cells in order (top to bottom) to reproduce the cleaning, analysis, and visualizations.
