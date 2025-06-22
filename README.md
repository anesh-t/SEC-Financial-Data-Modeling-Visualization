# 📊 SEC Financial Statement & Notes Data Warehouse + Visualization Project

BY Anesh Thangaraj

This project focuses on building a scalable, cloud-hosted data warehouse using PostgreSQL on AWS EC2 to store, clean, and analyze the U.S. Securities and Exchange Commission (SEC)'s Financial Statement and Notes Data Sets. It also includes interactive Tableau dashboards for financial disclosure trend analysis across public companies.

---

## 🔗 Source Dataset

- **Data Publisher:** U.S. Securities and Exchange Commission (SEC)
- **Dataset Name:** Financial Statement and Notes Data Sets
- **Access:** [SEC.gov Official Dataset Page](https://www.sec.gov/dera/data/financial-statement-and-notes-data-set.html)
- **Direct Download Used in This Project:**  
  [2024_01_notes.zip](https://www.sec.gov/files/dera/data/financial-statement-notes-data-sets/2024_01_notes.zip)
- **Date Range Covered:** Data from filings submitted in **January 2024**

---

## 🧩 Project Summary

- **Domain:** Financial Reporting & Data Engineering  
- **Database Engine:** PostgreSQL on AWS EC2  
- **Data Source:** SEC Financial Statement and Notes Data  
- **Tables Used:** 8 standard tab-delimited tables  
- **Records Processed:** 480,000+  
- **Dashboard Tool:** Tableau (Interactive .twbx dashboards)

---

## 📚 About the 8 SEC Tables

| Table | Description |
|-------|-------------|
| `sub` | Submission metadata (e.g., accession number, CIK, filer info) |
| `num` | Numeric financial data, including statement and note-level facts |
| `txt` | Plain-text financial note disclosures |
| `tag` | Metadata about each tag (label, data type, taxonomy) |
| `dim` | Dimensions for contextualizing facts (e.g., segments, geographies) |
| `pre` | Presentation linkbase (defines order of tags in filings) |
| `cal` | Calculation relationships (defines roll-up structures) |
| `ren` | Rendering linkbase (report formatting info) |

---

## 🛠️ Project Workflow

### 1️⃣ Schema Design & Relational Modeling  
- Created **relational schema** with **primary and foreign key** constraints for all 8 tables.  
- Generated **ER diagrams** to map relationships and support query integrity.

### 2️⃣ Data Cleaning & Preprocessing  
- Handled large flat files (~50MB) using PostgreSQL.  
- Cleaned and normalized column values for consistency.  
- Enabled multi-table joins by aligning tag and dimension references.

### 3️⃣ Data Analysis & Insights  
- Wrote SQL queries for:
  - Filing volume by company and industry
  - Most frequent financial tags
  - Temporal patterns in note disclosures
- Linked numeric and text-based facts for context-driven analysis.

### 4️⃣ Interactive Dashboard in Tableau  
- Built Tableau dashboards to:
  - Analyze filing frequency and tag usage
  - Explore common disclosures in plain-text notes
  - Visualize trends across fiscal years and firms

---

## ☁️ Tech Stack

| Layer           | Tools Used                  |
|------------------|-----------------------------|
| Cloud Hosting    | AWS EC2 (Ubuntu)            |
| Database Engine  | PostgreSQL                  |
| Query Language   | SQL                         |
| Data Viz         | Tableau (Public / Desktop)  |
| Documentation    | ER Diagrams, SOPs           |

---

## 🚀 How to Reproduce

1. **Clone the Repository**
```bash
git clone https://github.com/yourusername/sec-notes-data-warehouse.git
cd sec-notes-data-warehouse
Set up PostgreSQL on AWS EC2

bash
Copy
Edit
psql -U postgres -d sec_notes -f sql/create_schema.sql
psql -U postgres -d sec_notes -f sql/load_cleaned_data.sql


