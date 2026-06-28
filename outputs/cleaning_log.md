# Data Cleaning Log

## Issues Found

* Inconsistent text formatting and extra spaces
* Missing values in region, ship_mode, and discount fields
* Multiple date formats
* Exact duplicate records
* Duplicate order IDs with conflicting information
* Negative discount values
* Sales and profit calculation mismatches

## Cleaning Actions Performed

* Preserved the original dataset and worked on a separate cleaned file.
* Cleaned text fields using TRIM and PROPER functions.
* Filled missing region and ship_mode values with "Unknown".
* Standardized date formats and created shipping_delay_days.
* Removed exact duplicate records.
* Flagged duplicate order IDs with conflicting information.
* Applied business rule validations.
* Created calculated columns for sales, profit, profit margin, and data quality checks.
* Generated data quality and pivot summary reports.

## Business Rules Applied

* Missing region → Unknown
* Missing ship_mode → Unknown
* Missing discount → 0 where applicable
* Negative discount → Flagged as invalid
* Ship date before order date → Flagged for review

## Assumptions Made

* Missing region and ship_mode values represent unknown information.
* Missing discounts were treated as 0 where supporting sales data existed.
* Small rounding differences were ignored during validation.

## Records Removed

* 20 exact duplicate records removed.

## Records Flagged

* 24 duplicate order ID records flagged for review.
* 15 records flagged for negative discounts.
* 93 records flagged for invalid shipping dates.
* 64 sales calculation mismatches identified.
* 64 profit calculation mismatches identified.

## Limitations

* Conflicting duplicate order IDs require manual review.
* Validation was limited to the business rules provided in the assignment.
* Source data accuracy could not be independently verified.
