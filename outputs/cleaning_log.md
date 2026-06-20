# Cleaning Log

## 1. Issues Found

The raw dataset contained the following data quality issues:

* Inconsistent date formats in `order_date` and `ship_date`
* Missing values in `region`
* Missing values in `ship_mode`
* Missing values in `discount`
* Extra spaces and inconsistent text formatting in fields such as:

  * customer_name
  * segment
  * category
  * ship_mode
* Exact duplicate records
* Duplicate order IDs
* Invalid date sequences where ship date occurred before order date
* Negative discount values
* High discount values requiring review

---

## 2. Cleaning Actions Performed

### Text Standardization

* Removed leading and trailing spaces using Excel cleaning techniques.
* Standardized text values across customer, segment, category, and shipping-related fields.
* Corrected inconsistent category and segment naming caused by extra spaces.

### Date Standardization

* Converted multiple date formats into a consistent DD-MM-YYYY format.
* Standardized both order_date and ship_date fields.
* Validated date values and corrected unrecognized date formats.

### Missing Value Handling

* Missing region values were replaced with "Unknown".
* Missing ship_mode values were replaced with "Unknown".
* Missing discount values were replaced with 0 where business rules allowed.

### Duplicate Handling

* Exact duplicate records were identified and removed.
* Duplicate order IDs were reviewed separately.
* Conflicting duplicate records were retained for analysis.

### Validation Checks

* Ship dates occurring before order dates were flagged.
* Negative discount values were flagged as invalid.
* High discount values were flagged for review.

---

## 3. Business Rules Applied

The following business rules were applied during cleaning:

* Missing region → Filled as Unknown
* Missing ship_mode → Filled as Unknown
* Missing discount → Treated as 0 when applicable
* Negative discount → Flagged as invalid
* High discount → Flagged for review
* Ship date earlier than order date → Flagged as invalid shipping record
* Exact duplicate rows → Removed
* Duplicate order IDs with conflicting information → Retained for analysis

---

## 4. Assumptions Made

* Unknown values were used when valid replacement information was not available.
* Missing discounts were assumed to be 0 when other sales-related fields were present and valid.
* Date conversions were performed based on the original format identified in the source data.
* Duplicate order IDs were not automatically treated as errors unless the records were exact duplicates.

---

## 5. Records Removed

| Issue                        | Count |
| ---------------------------- | ----- |
| Exact Duplicate Rows Removed | 20    |

---

## 6. Records Flagged

| Issue                 | Count |
| --------------------- | ----- |
| Invalid Date Sequence | 91    |
| Negative Discounts    | 15    |
| High Discounts        | 8     |

---

## 7. Limitations

* The cleaning process was performed using the available dataset only.
* Some business validations could not be independently verified due to lack of source-system access.
* Flagged records were retained for business review rather than automatically corrected.
* Data quality findings are based on the provided dataset and business rules supplied with the assignment.

---

## Cleaning Outcome Summary

The dataset was successfully cleaned, standardized, validated, and prepared for reporting and analysis. Data quality issues were documented, business rules were applied, calculated fields were created, and summary reports were generated for business review.
