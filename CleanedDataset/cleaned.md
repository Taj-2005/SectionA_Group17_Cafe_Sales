# Transaction Dataset — Data Cleaning & Quality Assurance Report
**Project:** Capstone G17 Analytics  
**Dataset Type:** Retail Transactional Records  
**Prepared For:** Business Intelligence & Dashboarding  
**Prepared By:** Data Engineering & Analytics Team  

---

## 1. Purpose of This Document
This document describes the complete data quality improvement and preprocessing performed on the raw transaction dataset prior to analytics consumption.

The goal of the cleaning process was to:

- Ensure **accuracy of financial metrics**
- Enable **reliable KPI computation**
- Prevent misleading business insights
- Prepare data for **BI dashboards & reporting pipelines**
- Maintain maximum usable data without introducing bias

This documentation ensures **reproducibility, auditability, and transparency**.

---

## 2. Dataset Overview

| Property | Value |
|--------|------|
| Raw Records | ~10,000 transactions |
| Cleaned Records | 6,658 transactions |
| Domain | Retail / Cafe POS |
| Primary Metrics | Revenue, Quantity Sold, Payment Behavior |
| Intended Usage | KPI dashboards, time-series analytics, customer behavior analysis |

---

## 3. Data Quality Issues Identified

| Category | Issues Found |
|--------|------|
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
**Ingestion → Standardization → Validation → Correction → Filtering → Verification**

---

## 5. Column Name Standardization

### Problem
Column names contained inconsistent casing and spacing, which breaks query engines and BI tools.

### Action Taken
- Converted to lowercase
- Removed spaces
- Replaced spaces with underscores

| Before | After |
|------|------|
| `Payment Method` | `payment_method` |
| `Price Per Unit` | `price_per_unit` |

### Benefit
Ensures compatibility with SQL, Python pipelines, and BI tools.

---

## 6. Text Normalization & Whitespace Removal

### Problem
Categorical values contained hidden whitespace:

"Cash"
" Cash "
"cash"


### Action Taken
- Trimmed whitespace
- Standardized capitalization

### Result
Prevents incorrect aggregation and duplicate categories.

---

## 7. Placeholder & Corrupted Value Handling

### Invalid Entries
- ERROR
- Unknown
- nan
- null

### Strategy

| Field Type | Action |
|----------|------|
| Categorical | Distribution-based replacement |
| Critical fields | Removed if unrecoverable |

### Reason
Placeholder values do not represent real transactions and distort analysis.

---

## 8. Numeric Validation & Imputation

### Affected Fields
- quantity
- price_per_unit

### Issues
- Missing values
- Zero values
- Non-numeric entries

### Approach
- Imputed realistic values
- Preserved valid transactions

### Importance
Prevents biased revenue and product demand metrics.

---

## 9. Revenue Recalculation

### Rule
total_spent = quantity × price_per_unit


### Action
Recalculated all revenue values after numeric validation.

### Impact
Ensures financial KPI accuracy.

---

## 10. Handling Missing Categorical Values

### Columns
- location
- payment_method

### Strategy
Distribution-based replacement using realistic business proportions.

### Justification
Transaction valid — classification missing.

---

## 11. Removal of Logically Impossible Records

Removed records where:

- Quantity ≤ 0
- Price ≤ 0

These represent system errors rather than transactions.

---

## 12. Date Standardization

Converted all dates into a consistent datetime format.

### Enabled Analytics
- Monthly trends
- Seasonal analysis
- Yearly performance

---

## 13. Duplicate Detection
Removed exact duplicate transactions.

### Prevents
- Revenue inflation
- Incorrect transaction counts

---

## 14. Final Validation

| Check | Status |
|------|------|
| Null critical fields | Passed |
| Placeholder values | Removed |
| Financial correctness | Verified |
| Logical constraints | Enforced |
| Duplicate records | Removed |
| Date format | Standardized |

---

## 15. Final Output

| Metric | Value |
|------|------|
| Valid Transactions | **6,658** |
| Data Quality | Production-ready |
| BI Compatibility | Yes |
| KPI Reliability | High |

---

## 16. Business Impact

After cleaning:

- Revenue KPIs became accurate
- Payment behavior segmentation reliable
- Product performance trustworthy
- Time-series trends analyzable

---

## 17. Conclusion
The dataset was transformed from a raw operational export into an analytics-grade dataset through systematic validation and correction.

This dataset is now suitable for dashboards, reporting, and advanced analytics.

---

## 18. Reproducibility
All transformations were rule-based and deterministic. Running the pipeline again on the raw dataset will produce identical results.