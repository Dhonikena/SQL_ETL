# SQL_ETL

# Customer Sales Data Cleaning & Analysis (SQL)

## 📌 Overview
This project cleans a messy retail customer dataset (`dirty_data`) using **MySQL** and answers key revenue-related business questions. It demonstrates end-to-end SQL data cleaning — standardization, type correction, missing-value handling — followed by aggregation-based analysis.

## 🗂 Dataset
**Table:** `dirty_data`
**Key columns:**
- `Gender` — inconsistent casing (e.g., MALE, female, Male)
- `AmountSpent` — stored as text with `$` symbols
- `JoinDate`, `LastPurchaseDate` — inconsistent date formats
- `Phone`, `City` — missing/blank values
- `State`, `ProductCategory` — used for revenue analysis

## 🧹 Data Cleaning Steps
1. **Standardized Gender** — converted to uppercase, then formatted to proper case (`Male`, `Female`)
2. **Cleaned AmountSpent** — removed `$` symbol and cast column to `DECIMAL(10,2)`
3. **Fixed data types** — converted `JoinDate` and `LastPurchaseDate` to `DATE`
4. **Handled missing values:**
   - `Phone` → `"Unknown"`
   - `Gender` → `"Unknown"`
   - `City` → `"Unknown"`
   - `AmountSpent` → filled with dataset average (₹13,834.14)

## 📊 Business Questions Answered
- **Total Revenue by State** — ranked highest to lowest
- **Total Revenue from Books** category
- **Total Revenue from Electronics**, broken down by State

## 🛠 Tools Used
- MySQL (DDL, DML, aggregate functions, string functions)

## ▶️ How to Run
```sql
CREATE DATABASE data_extraction;
USE data_extraction;
-- Import dirty_data table here
-- Run cleaning_analysis.sql sequentially
```

## 📁 Repository Structure
```
├── cleaning_analysis.sql   -- Full cleaning + analysis script
└── README.md
```

## 🔑 Key Learnings
- Practical use of `UPDATE`, `REPLACE`, `SUBSTRING`, `CONCAT` for text standardization
- Safe handling of `sql_safe_updates` for bulk updates
- Type casting with `ALTER TABLE ... MODIFY COLUMN`
- Business-driven aggregation using `GROUP BY` and `ORDER BY`

## 👤 Author
**Rajasri**
Data Analyst | SQL · Python · Power BI · Tableau
