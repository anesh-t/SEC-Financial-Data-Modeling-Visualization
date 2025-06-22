# 📊 SEC Financial Data Warehouse & Visualization Project

This project demonstrates an end-to-end pipeline for building a scalable, query-optimized financial data warehouse using PostgreSQL on AWS EC2, based on publicly available U.S. SEC filings. The system supports multi-table joins, ratio analysis, and visual storytelling through interactive Tableau dashboards.

---

## 🧩 Project Summary

- **Domain:** Financial Data Engineering & Reporting  
- **Database Engine:** PostgreSQL on AWS EC2  
- **Data Source:** SEC EDGAR datasets  
- **Tables Used:** 8+ (e.g., `sub`, `num`, `dim`, `tag`, etc.)  
- **Rows Processed:** 480,000+  
- **Dashboard Tool:** Tableau (Interactive .twbx dashboards)

---

## 📚 About the 8 SEC Tables

| Table | Description |
|-------|-------------|
| `sub` | Submission metadata – includes basic details like company name, CIK, form type, and filing dates. |
| `num` | Numeric facts reported in the filing, such as total revenue, net income, assets, etc. |
| `dim` | Dimensional data that describes the context of numeric facts (e.g., segments, geographic area). |
| `tag` | Defines what each numeric fact means (e.g., “AssetsCurrent” = current assets). |
| `pre` | Presentation linkbase – describes how tags are grouped in the presentation of the financial statements. |
| `cal` | Calculation linkbase – shows how tags mathematically relate (e.g., total assets = liabilities + equity). |
| `lab` | Label linkbase – provides human-readable labels for tags, often in different languages or roles. |
| `ren` | Reference linkbase – includes authoritative literature references (e.g., GAAP, IFRS) linked to tags. |

---

## 🛠️ Project Workflow

### 1️⃣ Schema Design & Relational Modeling  
- Created **relational schema** with **primary and foreign key** constraints for all 8+ SEC tables.  
- Designed and documented **ER diagrams** for cross-table analysis.  
- Ensured data consistency and referential integrity across all entity relationships.

### 2️⃣ Data Cleaning & Preprocessing  
- Cleaned and standardized raw SEC data using **PostgreSQL** queries.  
- Normalized key metrics for compatibility across tables.  
- Resolved schema mismatches, missing values, and column naming inconsistencies.

### 3️⃣ Data Analysis & Insights  
- Wrote complex SQL queries for:
  - **Filing frequency**
  - **Financial ratio trends**
  - **Disclosure delays across firms and years**  
- Enabled multi-dimensional analysis across different filing entities and timeframes.

### 4️⃣ Interactive Dashboard in Tableau  
- Built dynamic Tableau dashboards to:
  - Visualize filing patterns
  - Track ratio performance by firm/year
  - Analyze the timing and content of disclosures  
- Enhanced user experience with filters, drilldowns, and tooltips.

---

## ☁️ Tech Stack

| Layer           | Tools Used                  |
|------------------|-----------------------------|
| Cloud Hosting    | AWS EC2 (Ubuntu)            |
| Database Engine  | PostgreSQL                  |
| Query Language   | SQL                         |
| Data Viz         | Tableau (Public / Desktop)  |
| Documentation    | ER Diagrams, Metadata Docs  |

---


---

## 🚀 How to Use

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/sec-financial-data-warehouse.git
   cd sec-financial-data-warehouse
Set up PostgreSQL on AWS EC2
Launch an EC2 instance, install PostgreSQL, and execute the schema and data load scripts:

bash
Copy
Edit
psql -U postgres -d sec_finance -f sql/create_schema_with_keys.sql
psql -U postgres -d sec_finance -f sql/load_cleaned_data.sql
Explore Tableau Dashboards
Open the .twbx files in Tableau Desktop or Tableau Public to interact with the dashboards.

Anesh Thangaraj
MS in Business Analytics | George Washington University
📫 Email
🌐 LinkedIn
