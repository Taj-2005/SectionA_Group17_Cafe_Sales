# ☕ Food & Beverage Analytics Dashboard

## Group 17 – Section A

## 👥 Team Identity

**Sector Chosen:** Food & Beverage Analytics<br>
**Project Lead:** Shaik Tajuddin<br>
**Project Lead Email:** shaik.tajuddin2024@nst.rishihood.edu.in
## Team Members


| Name            | Role               | GitHub ID                             |
| --------------- | ------------------ | ------------------------------------- |
| Shaik Tajuddin  | Project Lead       | https://github.com/Taj-2005           |
| Debashish Karan | Data Lead          | https://github.com/DebasishKaran-1    |
| Akshat Chauhan  | Analysis Lead      | https://github.com/acboss1346         |
| Parthraj Singh  | Dashboard Lead     | https://github.com/parthrajsinghbhati |
| Pankaj Baid     | Strategy Lead      | https://github.com/pankajbaid567      |
| Krishna Verma   | PPT & Quality Lead | https://github.com/krishnaverma09     |
---

## Executive Summary

Cafes generate daily transactional data including item sales, quantities, timestamps, and payment details. However, operational datasets are often messy — containing missing values, inconsistent formats, and data entry errors.

This project focuses on cleaning and analyzing raw cafe sales data to build a performance dashboard that provides actionable insights on:

- Revenue trends
- Item performance
- Customer purchase behavior
- Payment preferences

The final output supports business decisions related to menu optimization, pricing strategy, staffing, and operational planning.

---

## Problem Statement

**How do item performance, payment preferences, and time-based sales trends impact overall cafe revenue, and which factors drive peak sales periods?**

---

## 📂 Dataset Information

**Source Platform:** Kaggle<br>
**Dataset Name:** Cafe Sales – Dirty Data for Cleaning Training<br>
**Direct Link:**
https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training
<br>
**File Format:** CSV<br>
**Rows:** ~10,000<br>
**Columns:** 8

### Dataset Validation

✅ Tabular and row-level data<br>
✅ Opens in Google Sheets<br>
✅ Raw / minimally processed<br>
✅ Contains missing or inconsistent values<br>
✅ Requires cleaning and standardization<br>
✅ Suitable for KPI and dashboard analysis

---

## 🗂 Project Folder Structure

```
Project Root
│
├── RawDataset/
│     └── dataset.csv
│
├── CleanedDataset/
│     ├── cleaned.csv
│     └── cleaned.md
│
├── Calculations_PivotTables/
│     └── calculation.csv
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

## 📊 Analytics Intent

### Key Columns Used

- Transaction Date
- Item
- Quantity
- Total Spent
- Payment Method
- Price Per Unit

---

## 📈 Proposed KPIs

1. Total Revenue (Year-wise)
2. Revenue Share by Payment Method (Year-wise %)
3. Average Transaction Value (ATV)
4. Sales by Item
5. Revenue by Mode of Shopping (Online vs In-store)

---

## 🔍 Expected Insights

- A small number of high-demand items contribute disproportionately to total revenue (Pareto effect).
- Clear time-based sales patterns (monthly or hourly peaks).
- Digital payments may dominate revenue share.
- Certain payment methods may show higher average transaction values.

---

## 🧹 Data Cleaning Process

The dataset contains:

- Missing values
- Inconsistent date formats
- Duplicate records
- Text inconsistencies

Cleaning steps include:

- Handling null values
- Standardizing date formats
- Validating numeric fields
- Removing duplicates
- Normalizing categorical variables

All cleaning steps are documented in `CleanedDataset/cleaned.md`.

---

## 📊 Dashboard Deliverables

The final dashboard includes:

- Revenue Trend Analysis
- Payment Method Distribution
- Top Performing Items
- Monthly/Hourly Sales Patterns
- Customer Purchase Insights

---

## 🛠 Tools & Technologies

- Google Sheets
- GitHub (Version Control)

---

## 🚀 Business Impact

This project demonstrates how raw operational data can be transformed into structured insights that support:

- Revenue optimization
- Menu strategy decisions
- Inventory planning
- Operational efficiency

---

## 📩 Contact

For project-related queries:

Shaik Tajuddin
shaik.tajuddin2024@nst.rishihood.edu.in

---

**Section A – Group 17**
Food & Beverage Analytics
