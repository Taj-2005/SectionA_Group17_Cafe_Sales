# Food & Beverage Analytics Dashboard
### Retail Transaction Intelligence | Business Analytics Project

---

## Project Overview
Operational sales data in food & beverage businesses is often exported directly from POS systems and contains inconsistencies such as missing values, incorrect revenue calculations, duplicate transactions, and inconsistent formats.

This project converts a **raw cafe transaction dataset** into an **analytics-grade dataset** and builds a dashboard to uncover business insights related to revenue drivers, customer behavior, and operational performance.

The outcome is a decision-support dashboard enabling data-driven improvements in pricing, menu design, staffing, and payment strategy.

---

## Business Problem
**Which factors most influence cafe revenue, and how do item demand, payment behavior, and time patterns drive peak sales performance?**

---

## Team – Group 17 (Section A)

| Name | Responsibility | GitHub |
|------|------|------|
| Shaik Tajuddin | Project Lead | https://github.com/Taj-2005 |
| Debashish Karan | Data Engineering | https://github.com/DebasishKaran-1 |
| Akshat Chauhan | Data Analysis | https://github.com/acboss1346 |
| Parthraj Singh | Dashboard Development | https://github.com/parthrajsinghbhati |
| Pankaj Baid | Business Strategy | https://github.com/pankajbaid567 |
| Krishna Verma | Quality Assurance & Documentation | https://github.com/krishnaverma09 |

---

## 📂 Dataset

**Source:** Kaggle  
**Dataset:** Cafe Sales – Dirty Data for Cleaning Training  
https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training

| Property | Details |
|------|------|
| Records | ~10,000 |
| Columns | 8 |
| Format | CSV |
| Data Type | Transaction-level POS export |
| Condition | Raw / Uncleaned |

---

## Data Preparation

The raw dataset contained real-world operational issues:

- Missing values
- Incorrect revenue calculations
- Invalid numeric entries
- Duplicate transactions
- Inconsistent date formats
- Categorical inconsistencies

A structured cleaning pipeline was applied:

1. Column standardization
2. Text normalization
3. Missing value handling
4. Financial validation & recalculation
5. Logical filtering
6. Duplicate removal
7. Date normalization

📄 Detailed documentation:  
`CleanedDataset/cleaned.md`

---

## Key Metrics (KPIs)

- Total Revenue
- Revenue Share by Payment Method
- Average Transaction Value (ATV)
- Item Performance Ranking
- Shopping Mode Revenue (Online vs In-Store)
- Monthly Sales Trends

---

## Insights Generated

The dashboard identifies:

- High revenue-contributing products (Pareto behavior)
- Peak demand periods
- Customer payment preferences
- Transaction value patterns by payment type
- Operational demand cycles

---

## 🗂 Repository Structure

Project Root
│
├── RawDataset/
│ └── dataset.csv
│
├── CleanedDataset/
│ ├── cleaned.csv
│ └── cleaned.md
│
├── Calculations_PivotTables/
│ └── calculation.csv
│
├── Dashboard/
│ └── dashboard.pdf
│
├── Presentation/
│ └── presentation.pdf
│
├── Documentation/
│ └── documentation.pdf
│
└── README.md


---

## Tech Stack
- Google Sheets (Data Processing & Pivot Analysis)
- GitHub (Version Control & Collaboration)

---

## Business Value
This project demonstrates how cleaning and structuring operational data enables:

- Revenue optimization
- Menu engineering decisions
- Demand forecasting
- Staffing planning
- Payment strategy optimization

---

## Contact
**Shaik Tajuddin**  
Project Lead  
shaik.tajuddin2024@nst.rishihood.edu.in

---

**Food & Beverage Analytics — Group 17**