# Week 05 Log — [Sprint Name]

**Week:** 5  
**Date range:** 7/8/2026 - 14/8/2026 
**Team:** 18  
**Project:** FraudSheild - Transaction risk monitoring

---

## 1. Sprint Goal

Silver Standardization - Clean standardized Silver tables

---

## 2. Work Completed

| Task                                                                                | Owner   | Status | Evidence                                             |
| ----------------------------------------------------------------------------------- | ------- | ------ | ---------------------------------------------------- |
| Created Silver tables from Bronze tables                                            | Manthena Bhavana | Done   | `03_silver_transformation_all_tables_sparksql.ipynb` |
| Cleaned and standardized Bronze data using Spark SQL                                | Manthena Bhavana | Done   | Silver transformation notebook                       |
| Removed duplicate records using business keys                                       | Manthena Bhavana | Done   | Silver transformation notebook                       |
| Converted date/timestamp and numeric fields to appropriate data types               | Manthena Bhavana | Done   | Silver transformation notebook                       |
| Created separate `silver_customer_accounts` table from nested customer account data | Manthena Bhavana | Done   | Silver transformation notebook                       |
| Performed Silver table validation using row counts and null/duplicate checks        | Manthena Bhavana | Done   | Validation cells in notebook                         |
| Added evidence to Git-hub                                                           | Manthena Bhavana | Done   | Screenshots                                          |

---

## 3. Key Decisions

- Used Bronze tables as the source for all Silver transformations.
- Created separate Silver tables for customers, customer accounts, devices, fraud cases, merchants, and transactions.

---

## 4. Blockers / Risks
| Blocker                                                                          | Impact                                                                | Help Needed                              |
| -------------------------------------------------------------------------------- | --------------------------------------------------------------------- | ---------------------------------------- |
| Some Bronze data may contain duplicate or null business keys                     | Could affect Silver table quality                                     | Validate using duplicate and null checks |
| Nested `accounts` data in customer records                                       | Needed additional transformation before creating a clean Silver table | Flattened using `EXPLODE()`              |
| Silver row counts may differ from Bronze counts after cleaning and deduplication | Need to verify that records were not incorrectly removed              | Compare Bronze and Silver counts         |

---


## 5. Evidence Added to GitHub

- Weekly_logs:week05 updated
- Silver tables Screenshots added
- Silver_transformations.ipynb Notebook updated

---

## 6. AI Transparency Note
| Question                            | Response                                                                                                                                                             |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Where AI helped                     | AI helped in designing the Spark SQL transformations, Silver table structure, cleaning logic, and validation queries.                                                |
| What we changed after AI suggestion | We adapted the SQL to match our existing Bronze table names, project structure, and available columns.                                                               |
| What we verified manually           | We manually checked that the Bronze table names were correct and verified the Silver tables using `SHOW TABLES`, `SELECT`, row counts, and null/duplicate checks.    |
| What we can explain without AI      | We can explain the Bronze-to-Silver process, why cleaning and deduplication are required, how the Silver tables are created, and how we validate them in Databricks. |

---

## 7. Next Week Preparation

- Verify all Silver tables and their row counts in Databricks.
- Perform additional data-quality checks on the Silver layer.
- Start designing and creating the Gold tables using the cleaned Silver data.
