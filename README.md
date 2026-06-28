# Part 1: Business Data Cleaning, Validation & Excel Reporting

## Problem Summary

The objective of this project was to clean, validate, and prepare a retail order dataset for business analysis. The raw dataset contained issues such as inconsistent text formatting, missing values, duplicate records, mixed date formats, invalid discounts, and calculation mismatches. The goal was to create a clean dataset, apply business rules, generate data quality reports, and build pivot-based business summaries.

---

## Dataset Description

The dataset contains order-level retail sales information, including:

* Order details (order_id, order_date, ship_date)
* Customer information
* Product category and sub-category
* Sales, cost, profit, and discount information
* Shipping details
* Payment and order status information

Original records: **932**

Final records after cleaning: **912**

---

## Tools Used

* Microsoft Excel
* Pivot Tables
* Excel Functions:

  * TRIM
  * PROPER
  * IF
  * YEAR
  * TEXT
  * COUNTIF
  * ROUND
  * ABS

---

## Cleaning Steps Performed

### 1. Raw Data Preservation

* Preserved the original dataset as raw_orders.xlsx.
* Performed all cleaning activities in cleaned_orders.xlsx.

### 2. Text Cleaning

* Removed leading and trailing spaces.
* Standardized text capitalization.
* Corrected inconsistent text formatting.
* Replaced missing region values with "Unknown".
* Replaced missing ship_mode values with "Unknown".

### 3. Date Validation

* Standardized order_date and ship_date formats.
* Converted text-based dates into valid Excel dates.
* Created shipping_delay_days column.
* Identified records where ship_date occurred before order_date.

### 4. Duplicate Handling

* Identified exact duplicate records.
* Removed exact duplicate records.
* Flagged duplicate order IDs containing conflicting information.

### 5. Business Rule Validation

* Filled missing discount values where applicable.
* Flagged negative discount values.
* Checked discount range validity.
* Flagged invalid shipping records.

### 6. Calculated Columns

Created:

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag

---

## Business Rules Applied

* Missing region values were replaced with "Unknown".
* Missing ship_mode values were replaced with "Unknown".
* Missing discount values were treated as 0 where applicable.
* Negative discount values were flagged as invalid.
* Ship dates earlier than order dates were flagged.
* Duplicate order IDs with conflicting information were retained and flagged for review.

---

## Summary of Data Quality Issues Found

| Issue                              | Count |
| ---------------------------------- | ----: |
| Missing Region Values              |    26 |
| Missing Ship Mode Values           |    22 |
| Missing Discount Values            |    18 |
| Exact Duplicate Records            |    20 |
| Duplicate Order ID Records Flagged |    24 |
| Negative Discount Records          |    15 |
| Invalid Shipping Records           |    93 |
| Sales Calculation Mismatches       |    64 |
| Profit Calculation Mismatches      |    64 |

---

## Summary of Pivot Reports

The following pivot reports were created:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-Category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Cancelled and Returned Orders by Region
6. Monthly Sales Trend

Sorting and filtering were applied where required.

---

## Key Business Insights

* East region generated the highest sales and profit among all regions.
* Technology and Furniture categories contributed significantly to overall revenue.
* Standard Class was the most frequently used shipping mode.
* A noticeable number of orders contained shipping or discount-related data quality issues.
* Monthly sales varied across both years, showing seasonal fluctuations.
* Several records contained sales and profit calculation mismatches, highlighting the importance of validation checks.

---

## Assumptions and Limitations

### Assumptions

* Missing region values represent unknown regional information.
* Missing ship_mode values represent unknown shipping methods.
* Missing discount values were treated as 0 where sufficient supporting information existed.
* Minor rounding differences were ignored during validation.

### Limitations

* Conflicting duplicate order IDs require manual business review.
* Validation was limited to the business rules provided in the assignment.
* Source data accuracy could not be independently verified.

---

## Screenshots Included

The repository includes screenshots showing:

* Raw dataset preview
* Cleaned dataset preview
* Pivot summary output 1
* Pivot summary output 2

Note: Some workbook sheets may require horizontal tab scrolling in Excel because the workbook contains multiple report tabs.
