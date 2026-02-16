# Transaction Dataset — Data Cleaning & Quality Assurance Report

**Project:** Capstone G17 Analytics
**Dataset Type:** Retail Transactional Records
**Prepared For:** Business Intelligence & Dashboarding
**Prepared By:** Data Engineering & Analytics Team

---

## 1. Purpose

This document details the complete data quality improvement and preprocessing pipeline applied to the raw transaction dataset prior to analytics consumption. The cleaning process was designed to ensure accuracy of financial metrics, enable reliable KPI computation, prevent misleading business insights, prepare data for BI dashboards and reporting pipelines, and maintain maximum usable data without introducing bias. All transformations are documented here to guarantee reproducibility, auditability, and transparency.

---

## 2. Dataset Overview

| Property | Value |
|---|---|
| Raw Records | ~10,000 transactions |
| Cleaned Records | 6,658 transactions |
| Domain | Retail / Cafe POS |
| Primary Metrics | Revenue, Quantity Sold, Payment Behavior |
| Intended Usage | KPI dashboards, time-series analytics, customer behavior analysis |

---

## 3. Data Quality Issues Identified

| Category | Issues Found |
|---|---|
| Structural | Inconsistent column names |
| Categorical | Whitespace, unknown labels, placeholder values |
| Numeric | Missing, zero, and invalid values |
| Financial | Incorrect revenue calculations |
| Temporal | Invalid date formats |
| Logical | Impossible transactions |
| Duplicates | Repeated entries |
| Null Handling | Missing categorical and numeric values |

---

## 4. Cleaning Methodology

The pipeline followed a sequential six-stage process:

**Ingestion → Standardization → Validation → Correction → Filtering → Verification**

Each stage was applied in order to prevent downstream contamination of clean records by upstream issues.

---

## 5. Column Name Standardization

Raw column headers contained inconsistent casing and spacing, which breaks query engines, BI tools, and Python/SQL pipelines. All column names were converted to lowercase with spaces replaced by underscores.

| Before | After |
|---|---|
| `Payment Method` | `payment_method` |
| `Price Per Unit` | `price_per_unit` |

This ensures full compatibility across SQL engines, pandas DataFrames, and BI connectors.

---

## 6. Text Normalization & Whitespace Removal

Categorical fields contained hidden leading/trailing whitespace and inconsistent capitalization, causing the same value to be treated as multiple distinct categories. All string values were trimmed and capitalization was standardized, eliminating phantom duplicate categories and ensuring correct aggregation.

**Example — before normalization:**
```
"Cash" / " Cash " / "cash"  →  treated as 3 separate categories
```
**After normalization:**
```
"Cash"  →  single unified category
```

---

## 7. Placeholder & Corrupted Value Handling

The following invalid entries were identified across categorical and numeric fields:
```
ERROR / Unknown / nan / null
```

| Field Type | Action Taken |
|---|---|
| Categorical | Replaced using distribution-based proportional assignment |
| Critical fields | Removed entirely if unrecoverable |

Placeholder values carry no transactional meaning and directly distort aggregated metrics. Distribution-based replacement preserves dataset size while maintaining realistic category proportions.

---

## 8. Numeric Validation & Imputation

The `quantity` and `price_per_unit` fields contained missing values, zero entries, and non-numeric strings. Affected records were either imputed with realistic values derived from the dataset's existing distribution or removed where imputation was not feasible. This prevents biased revenue calculations and misrepresented product demand metrics.

---

## 9. Revenue Recalculation

Following numeric validation, all revenue values were recalculated from first principles to eliminate any pre-existing errors in the source data:
```
total_spent = quantity × price_per_unit
```

This ensures all downstream financial KPIs are derived from validated, consistent inputs rather than potentially corrupt source figures.

---

## 10. Missing Categorical Value Imputation

The `location` and `payment_method` fields contained missing values in otherwise valid transaction records. Rather than discarding these records, missing categories were assigned using distribution-based replacement that reflects realistic business proportions observed in the complete dataset. This retains valid transactions while avoiding the introduction of artificial bias.

---

## 11. Removal of Logically Impossible Records

Records violating basic transactional logic were removed entirely, as they represent system errors rather than real transactions:

- `quantity ≤ 0`
- `price_per_unit ≤ 0`

No legitimate transaction can have a non-positive quantity or price. Retaining these records would silently corrupt all revenue and volume metrics.

---

## 12. Date Standardization

All date values were parsed and converted to a consistent `datetime` format, resolving mixed format strings present in the raw export. This enables time-based analytics including monthly trend analysis, seasonal performance tracking, and year-over-year comparisons.

---

## 13. Duplicate Detection & Removal

Exact duplicate records — rows identical across all fields — were identified and removed. Duplicate transactions inflate revenue figures, overcount transaction volumes, and skew per-product and per-customer metrics.

---

## 14. Final Validation Checks

| Check | Status |
|---|---|
| Null values in critical fields | ✓ Passed |
| Placeholder values removed | ✓ Passed |
| Financial correctness verified | ✓ Passed |
| Logical constraints enforced | ✓ Passed |
| Duplicate records removed | ✓ Passed |
| Date format standardized | ✓ Passed |

---

## 15. Final Output

| Metric | Value |
|---|---|
| Valid Transactions | **6,658** |
| Data Quality | Production-ready |
| BI Compatibility | Yes |
| KPI Reliability | High |

---

## 16. Business Impact

The cleaned dataset enables the following analytics capabilities that were unreliable or impossible on the raw data:

- **Revenue KPIs** are now accurate and free of calculation errors
- **Payment behavior segmentation** produces reliable category distributions
- **Product performance metrics** reflect true demand patterns
- **Time-series analysis** is enabled by consistent, parseable date fields

---

## 17. Conclusion

The dataset was transformed from a raw operational export into an analytics-grade resource through a systematic, rule-based validation and correction pipeline. Each transformation addresses a specific, documented data quality failure. The resulting dataset is suitable for production dashboards, executive reporting, and advanced analytics workloads.

---

## 18. Reproducibility

All transformations are rule-based and deterministic. Re-running the pipeline against the original raw dataset will produce byte-identical output. No manual overrides or non-deterministic operations were applied at any stage.