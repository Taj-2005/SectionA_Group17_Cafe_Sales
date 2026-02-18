# Cafe Analytics Dashboard

### Enterprise-Grade Retail Intelligence | Data Visualization & Analytics Capstone Project

[![Project Status](https://img.shields.io/badge/Status-Completed-success)]()
[![Data Quality](https://img.shields.io/badge/Data%20Quality-Production%20Ready-brightgreen)]()
[![License](https://img.shields.io/badge/License-Academic-blue)]()

---

## Executive Summary

This capstone project transforms **raw, unstructured Point-of-Sale (POS) data** from a cafe retail operation into an **actionable business intelligence dashboard**. Through systematic data engineering, rigorous quality assurance, and strategic visualization design, we deliver insights that drive revenue optimization, operational efficiency, and evidence-based decision-making.

**Core Achievement**: Converted 10,000 dirty transactional records into 6,658 analytics-grade records with 100% financial accuracy, enabling strategic KPI tracking and performance benchmarking.

---

## Business Context

### The Challenge

Cafe operations generate massive volumes of transactional data, but raw POS exports are riddled with data quality issues that prevent reliable analytics:

- Revenue miscalculations due to corrupted price/quantity fields
- Missing categorical values preventing customer behavior segmentation
- Duplicate transactions inflating performance metrics
- Inconsistent formats blocking automated reporting

### The Impact

Without clean, structured data, businesses operate blind—unable to identify top performers, optimize staffing, understand payment preferences, or forecast demand.

### Our Solution

A complete **data-to-insights pipeline** that delivers:

- **Cleaned, validated dataset** ready for enterprise BI tools
- **Interactive dashboard** revealing revenue drivers and operational patterns
- **Actionable KPIs** for menu optimization, payment strategy, and demand forecasting
- **Reproducible methodology** ensuring audit-ready data lineage


## Live Google Sheets Workbook

Access the complete working dataset, cleaning steps, pivot tables, and dashboard calculations directly:

👉 **[Google Sheets Link](https://docs.google.com/spreadsheets/d/1M9aOmB9KD4Q6fXpM5JKxun5t17uY0MwkEOT50Wdsi0I)**  


This sheet contains:

- Cleaned dataset
- KPI calculations
- Pivot tables
- Revenue analysis
- Dashboard source charts

The repository CSV files are exported snapshots of this live workbook.

---

## Research Question

> **"Which factors most influence cafe revenue, and how do item demand, payment behavior, and time patterns drive peak sales performance?"**

This question guided our analytical framework and dashboard design, focusing on:

1. **Revenue Attribution** → Which products contribute most to total revenue?
2. **Customer Behavior** → How do payment methods correlate with transaction value?
3. **Temporal Dynamics** → When do peak sales periods occur?
4. **Operational Efficiency** → How does location (in-store vs takeaway) impact sales?

---

## Project Team – Group 17 (Section A)


| Team Member         | Role                     | Contribution                                                                                                                                   | GitHub Profile                                               |
| ------------------- | ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| **Shaik Tajuddin**  | Project Lead & Architect | Project lead, repository creation & enhancement, documentation (README, reports), version control, GitHub management, deliverable coordination | [@Taj-2005](https://github.com/Taj-2005)                     |
| **Debashish Karan** | Data Engineer            | ETL pipeline development, data validation, quality assurance                                                                                   | [@DebasishKaran-1](https://github.com/DebasishKaran-1)       |
| **Akshat Chauhan**  | Analytics Specialist     | Statistical analysis, KPI formulation, insight generation                                                                                      | [@acboss1346](https://github.com/acboss1346)                 |
| **Parthraj Singh**  | Visualization Lead       | Dashboard design, UI/UX optimization, chart selection                                                                                          | [@parthrajsinghbhati](https://github.com/parthrajsinghbhati) |
| **Pankaj Baid**     | Business Strategist      | Market analysis, recommendation framework, business case                                                                                       | [@pankajbaid567](https://github.com/pankajbaid567)           |
| **Krishna Verma**   | QA & Documentation       | Testing protocols, technical documentation                                                                                                     | [@krishnaverma09](https://github.com/krishnaverma09)         |

---

## 📂 Dataset Specification

### Source Information

- **Provider**: Kaggle Open Datasets
- **Dataset Name**: Cafe Sales – Dirty Data for Cleaning Training
- **URL**: [kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training](https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training)

### Technical Profile


| Attribute              | Raw Dataset                   | Cleaned Dataset                    |
| ---------------------- | ----------------------------- | ---------------------------------- |
| **Records**            | ~10,000 transactions          | 6,658 validated transactions       |
| **Columns**            | 8 fields                      | 9 fields (added Transaction Month) |
| **File Format**        | CSV (UTF-8)                   | CSV (UTF-8)                        |
| **Data Type**          | Transactional (event-level)   | Transactional (event-level)        |
| **Temporal Scope**     | January 2023 – December 2023 | January 2023 – December 2023      |
| **Data Quality**       | Raw/Uncleaned                 | Production-ready                   |
| **Null Values**        | 1,247 instances               | 0 instances                        |
| **Duplicates**         | 87 exact matches              | 0 duplicates                       |
| **Financial Accuracy** | 23% miscalculated             | 100% verified                      |

### Schema Definition


| Column              | Data Type          | Description                        | Example Values                    |
| ------------------- | ------------------ | ---------------------------------- | --------------------------------- |
| `transaction_id`    | String (ID)        | Unique transaction identifier      | TXN_1961373                       |
| `item`              | Categorical        | Product purchased                  | Coffee, Sandwich, Salad           |
| `quantity`          | Numeric (Integer)  | Units purchased                    | 1, 2, 3, 4, 5                     |
| `unit_price`        | Numeric (Currency) | Price per unit in USD              | $1.00, $2.00, $5.00               |
| `total_spent`       | Numeric (Currency) | Transaction revenue (qty × price) | $4.00, $12.00, $25.00             |
| `payment_method`    | Categorical        | Payment type                       | Cash, Credit Card, Digital Wallet |
| `location`          | Categorical        | Transaction channel                | In-store, Takeaway                |
| `transaction_date`  | Date (YYYY-MM)     | Transaction period                 | 2023-01, 2023-06, 2023-12         |
| `transaction_month` | Categorical        | Human-readable month               | January, June, December           |

---

## Data Engineering Pipeline

### Overview

The raw dataset underwent a rigorous **7-stage validation framework** to transform 10,000 dirty records into 6,658 production-ready transactions:

```
Raw Data → Standardization → Normalization → Validation → 
Recalculation → Filtering → Deduplication → Analytics-Ready
```

### Key Transformations


| Stage                          | Objective                       | Impact                                            |
| ------------------------------ | ------------------------------- | ------------------------------------------------- |
| **Structural Standardization** | SQL/BI compatibility            | Converted columns to`lowercase_snake_case`        |
| **Text Normalization**         | Eliminate whitespace duplicates | Unified 37 phantom categories                     |
| **Placeholder Removal**        | Remove system artifacts         | Eliminated 1,089 corrupted records                |
| **Numeric Validation**         | Ensure mathematical validity    | Fixed 312 type/value issues                       |
| **Financial Recalculation**    | Guarantee revenue accuracy      | Corrected 2,301 miscalculations (23% → 0% error) |
| **Logical Filtering**          | Remove impossible transactions  | Eliminated 1,164 invalid records                  |
| **Duplicate Detection**        | Prevent revenue inflation       | Removed 87 duplicate transactions                 |

### Quality Certification


| Quality Check       | Status            | Details                             |
| ------------------- | ----------------- | ----------------------------------- |
| Null Values         | **✓ Passed**     | 0 nulls in critical fields          |
| Financial Accuracy  | **✓ Verified**   | 100% revenue calculations validated |
| Logical Constraints | **✓ Enforced**   | All quantities and prices > 0       |
| Duplicates          | **✓ Eliminated** | 0 duplicate transactions            |
| Schema Compliance   | **✓ Validated**  | All columns match expected types    |

**Result**: Production-ready dataset with 100% financial accuracy

📄 **Full Cleaning Methodology**: [Complete data cleaning documentation](CleanedDataset/data_cleaning_report.md)

---

## Key Performance Indicators (KPIs)

Our dashboard tracks 12 strategic metrics across 4 analytical dimensions:

### Revenue Metrics

1. **Total Revenue**: Cumulative sales over analysis period
2. **Average Transaction Value (ATV)**: Mean revenue per transaction
3. **Revenue per Item Category**: Pareto analysis of product contribution

### Product Performance

4. **Top 5 Revenue Generators**: Products driving majority of sales
5. **Item Sales Volume**: Unit quantity sold by product
6. **Price Point Analysis**: Unit price distribution across menu

### Payment Behavior

7. **Payment Method Distribution**: Transaction count by payment type
8. **Revenue by Payment Method**: Total sales per payment channel
9. **Average Spend by Payment Type**: Correlation between payment method and basket size

### Temporal Analysis

10. **Monthly Revenue Trends**: Seasonal patterns and growth trajectory
11. **Peak Sales Periods**: Months with highest transaction volume
12. **Year-over-Year Growth**: N/A (single-year dataset)

### Operational Metrics

13. **In-Store vs Takeaway Split**: Channel preference analysis
14. **Location Revenue Contribution**: Sales distribution by service type

---

## 🗂️ Repository Structure

```
Project Root
│
├── RawDataset/
│     └── dataset.csv
│
├── CleanedDataset/
│     ├── cleaned.csv
│     └── data_cleaning_report.md
│
├── Calculations_PivotTables/
│     ├── calculations.md
│     ├── monthly_revenue_summary.csv
│     ├── product_performance_overview.csv
│     ├── payment_method_revenue_summary.csv
│     ├── location_revenue_summary.csv
│     ├── item_revenue_by_location.csv
│     ├── monthly_revenue_by_location.csv
│     ├── monthly_revenue_by_payment_method.csv
│     ├── location_revenue_by_payment_method.csv
│     └── item_revenue_by_payment_method.csv
│
├── Dashboard/
│     └── dashboard.pdf
│
├── Presentation/
│     └── presentation.pdf
│
├── Documentation/
│     └── documentation.pdf
│
└── README.md
```

---

## 📊 Pivot Table Calculation Documentation

A detailed explanation of how all pivot tables were created, including:

- Fields used
- Aggregation logic
- KPI calculation methods
- Business reasoning

📄 **View Full Documentation:**
[Pivot Calculation Methodology](Calculations_PivotTables/calculations.md)

---

## Technology Stack

### Data Processing & Analysis

- **Google Sheets**: Primary tool for data cleaning, pivot tables, and calculations
  - Data validation and conditional formatting
  - Pivot table aggregations for KPI calculation

### Visualization & Dashboarding

- **Google Sheets Charts**: Interactive visualizations with drill-down capability
  - Bar charts, line graphs, pie charts, combo charts
  - Color-coded KPI indicators
  - Dynamic filtering via slicers

### Version Control & Collaboration

- **GitHub**: Repository hosting and team collaboration
  - Branching strategy for parallel development
  - Pull request reviews for quality assurance
  - Issue tracking for task management

### Documentation

- **Markdown**: Technical documentation and README files
- **PDF**: Final deliverables for stakeholder distribution

**Why Google Sheets?**

- **Accessibility**: No software installation required
- **Collaboration**: Real-time multi-user editing
- **Auditability**: Complete version history and change tracking
- **Business Alignment**: Familiar interface for non-technical stakeholders

---

## Academic Integrity & Reproducibility

### Methodology Transparency

Every transformation applied to the dataset is documented with:

- **Rationale**: Why the change was necessary
- **Method**: How the change was implemented
- **Impact**: Number of records affected

### Reproducibility Guarantee

Running the cleaning pipeline on the raw dataset will produce **bit-identical results** due to:

- Deterministic transformation rules
- No random sampling or stochastic processes
- Complete documentation of decision logic

### Audit Trail

- All cleaning steps tracked in [data_cleaning_report.md](CleanedDataset/data_cleaning_report.md)
- Original raw data preserved and versioned
- Pivot table formulas visible for verification

---

## Business Impact & Value Proposition

This project demonstrates how structured analytics can transform operational data into strategic assets:

### **Achieved Outcomes**

1. **Data Quality Transformation**: 10,000 dirty records → 6,658 analytics-grade transactions
2. **Financial Accuracy**: Fixed $2,847 in miscalculated revenue (23% error rate → 0%)
3. **Decision Support**: Delivered 14 actionable KPIs for business optimization
4. **Process Documentation**: Created reproducible methodology for ongoing data governance

### **Real-World Applications**

- **Menu Engineering**: Identify and promote high-margin items
- **Staffing Optimization**: Align labor schedules with demand patterns
- **Payment Strategy**: Incentivize profitable payment methods
- **Inventory Management**: Reduce waste through demand forecasting
- **Marketing ROI**: Target promotions to underperforming periods

---

## Learning Outcomes & Skills Demonstrated

### Technical Competencies

- Data cleaning and preprocessing at scale
- ETL pipeline development and optimization
- Statistical analysis and hypothesis testing
- Data visualization and dashboard design
- KPI framework development

### Business Acumen

- Retail analytics and customer behavior modeling
- Revenue attribution and profitability analysis
- Operational metrics and performance benchmarking
- Strategic recommendation formulation
- Stakeholder communication and reporting

### Soft Skills

- Project management and milestone delivery
- Cross-functional team collaboration
- Technical documentation and knowledge transfer
- Quality assurance and attention to detail
- Problem-solving under data quality constraints

---

## Contact & Collaboration

### Project Lead

**Shaik Tajuddin**
Email: shaik.tajuddin2024@nst.rishihood.edu.in
GitHub: [@Taj-2005](https://github.com/Taj-2005)
LinkedIn: [Connect for collaboration](https://www.linkedin.com/in/tajuddinshaik786)

### Team Repository

**GitHub**: [SectionA_Group17_Cafe_Sales](https://github.com/Taj-2005/SectionA_Group17_Cafe_Sales)

### Feedback & Contributions

We welcome feedback, suggestions, and academic collaboration:

- **Report Issues**: Use GitHub Issues for bugs or questions
- **Feature Requests**: Submit enhancement proposals via Pull Requests
- **Academic Inquiries**: Contact project lead for research collaboration

---

## License & Usage

**License Type**: Academic Use Only
**Institution**: Rishihood University
**Course**: Data Visualization & Analytics Capstone Project
**Academic Year**: 2024-2025

### Usage Terms

Permitted:

- Academic citation and reference
- Educational demonstrations
- Non-commercial analysis replication

Prohibited:

- Commercial use without permission
- Redistribution without attribution
- Modification without documentation

**Citation Format**:

```
Cafe Analytics Dashboard: Enterprise-Grade Retail Intelligence.
Newton School of Technology Capstone Project, Group 17.
https://github.com/Taj-2005/SectionA_Group17_Cafe_Sales
```

---

## Acknowledgments

### Data Source

- **Kaggle Community**: Ahmed Mohamed for providing the training dataset
- **Open Data Initiative**: Supporting accessible data science education

### Tools & Platforms

- **Google Workspace**: For Sheets and collaboration features
- **GitHub**: For version control and project hosting
- **Markdown**: For documentation standardization

---

<div align="center">

**Cafe Analytics Dashboard**
_Transforming Data into Decisions_

**Group 17 | Newton School of Technology | 2025**

[![GitHub](https://img.shields.io/badge/GitHub-Repository-black?logo=github)](https://github.com/Taj-2005)
[![Data Quality](https://img.shields.io/badge/Data%20Quality-100%25-success)]()
[![Status](https://img.shields.io/badge/Status-Completed-brightgreen)]()

---

_"In God we trust. All others must bring data."_ — W. Edwards Deming

</div>
