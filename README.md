# Part 1: Business Data Cleaning, Validation & Excel Reporting

## Problem Summary

A retail company exported order-level sales data from multiple internal systems. The dataset contained several data quality issues including inconsistent text formatting, mixed date formats, missing values, duplicate records, invalid discounts, and business rule violations.

The objective of this project was to clean, validate, and standardize the dataset to create an analysis-ready version that can support business reporting and decision-making.

---

## Dataset Description

Dataset: Retail Orders Dataset

The dataset contains order-level transaction information including:

* Order ID
* Order Date
* Ship Date
* Customer Name
* Customer Segment
* Region
* State
* City
* Category
* Sub-Category
* Product Name
* Ship Mode
* Payment Status
* Order Status
* Sales
* Profit
* Discount

The raw dataset was provided as part of the capstone project and was preserved without modification.

---

## Tools Used

* Microsoft Excel 365
* Pivot Tables
* Excel Functions

  * TRIM
  * IF
  * COUNTIF
  * DATEVALUE
  * YEAR
  * TEXT
  * IFERROR
* Conditional Formatting
* Data Validation Techniques

---

## Cleaning Steps Performed

### Text Cleaning

The following fields were cleaned and standardized:

* customer_name
* segment
* region
* state
* city
* category
* sub_category
* ship_mode
* payment_status
* order_status

Actions performed:

* Removed leading and trailing spaces
* Corrected inconsistent text formatting
* Standardized similar category names
* Removed duplicate text values caused by extra spaces

### Date Cleaning

The following fields were standardized:

* order_date
* ship_date

Actions performed:

* Converted multiple date formats into a consistent DD-MM-YYYY format
* Corrected text-based date values
* Validated date sequences
* Calculated shipping delay days

### Missing Value Handling

| Field     | Action                           |
| --------- | -------------------------------- |
| Region    | Filled with Unknown              |
| Ship Mode | Filled with Unknown              |
| Discount  | Replaced with 0 where applicable |

### Duplicate Handling

* Exact duplicate rows were identified and removed.
* Duplicate order IDs were reviewed.
* Conflicting records were retained for analysis.

### Validation Checks

The following validations were performed:

* Invalid shipping dates
* Negative discounts
* High discounts
* Duplicate records
* Missing values
* Date consistency checks

---

## Business Rules Applied

The following business rules were implemented:

* Missing region values were filled as Unknown.
* Missing ship_mode values were filled as Unknown.
* Missing discounts were treated as 0 where valid.
* Negative discounts were flagged as invalid.
* High discount values were flagged for review.
* Ship dates occurring before order dates were flagged.
* Exact duplicate records were removed.
* Conflicting duplicate records were retained for analysis.

---

## Summary of Data Quality Issues Found

| Issue                 | Count                     | Action Taken        |
| --------------------- | ------------------------- | ------------------- |
| Missing Region        | 26                        | Filled with Unknown |
| Missing Ship Mode     | 21                        | Filled with Unknown |
| Missing Discount      | 18                        | Replaced with 0     |
| Exact Duplicate Rows  | 20                        | Removed             |
| Invalid Date Sequence | 91                        | Flagged             |
| Negative Discounts    | 15                        | Flagged             |
| High Discounts        | 8                         | Flagged             |
| Mixed Date Formats    | Multiple Formats Detected | Standardized        |

---

## Calculated Columns Created

The following calculated columns were added:

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag

These fields were used to support reporting and validation activities.

---

## Pivot Report Summary

The following pivot reports were created:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-Category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded, Cancelled, and Failed Orders by Region
6. Monthly Sales Trend

Sorting and filtering were applied where appropriate to improve analysis quality.

---

## Key Business Insights

### 1. Regional Performance

Sales and profit varied significantly across regions, highlighting differences in regional business performance.

### 2. Category Contribution

Certain categories contributed disproportionately to overall sales and profitability.

### 3. Customer Segment Analysis

Profit margins varied across customer segments, indicating opportunities for targeted business strategies.

### 4. Shipping Performance

Order volume differed across shipping modes, helping identify preferred fulfillment methods.

### 5. Order Quality Issues

A significant number of records contained shipping date inconsistencies and discount-related issues requiring review.

### 6. Data Quality Impact

Data quality issues such as duplicate records and missing values could have affected reporting accuracy if not corrected.

---

## Assumptions

* Unknown values were used when valid replacement information was unavailable.
* Missing discounts were treated as 0 based on assignment business rules.
* Duplicate order IDs were not automatically treated as errors.
* Date formats were standardized based on the original source format.

---

## Limitations

* Source systems were not available for independent validation.
* Flagged records were retained rather than automatically corrected.
* Business interpretations are based solely on the provided dataset.
* Some business context was unavailable beyond the supplied data.

---

## Screenshots Included

The repository includes the following screenshots:

* raw_data_preview.png
* cleaned_data_preview.png
* pivot_summary_1.png
* pivot_summary_2.png

These screenshots provide evidence of the cleaning process, calculated columns, and reporting outputs.

---

## Repository Contents

```text
data/
├── raw_orders.xlsx
└── cleaned_orders.xlsx

outputs/
├── data_quality_report.xlsx
├── pivot_summary.xlsx
└── cleaning_log.md

screenshots/
├── raw_data_preview.png
├── cleaned_data_preview.png
├── pivot_summary_1.png
└── pivot_summary_2.png

README.md
```

This project successfully transformed the raw retail dataset into a clean, validated, and analysis-ready dataset suitable for business reporting and decision-making.


