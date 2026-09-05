# Week 07 Log — Gold Metrics

**Week:** 7  
**Date range:**  4/9/2026 - 11/9/2026 
**Team:** 18  
**Project:**  FraudSheild - Transaction risk monitoring

---

## 1. Sprint Goal

Gold Metrics Dashboard-ready KPI tables created.
The goal of this sprint was to create and validate Gold-layer summary tables using Spark SQL. These tables provide aggregated transaction, customer, merchant, and fraud metrics that can be used for dashboarding and analysis.

---

## 2. Work Completed

| Task                                            | Owner            | Status | Evidence                                             |
| ----------------------------------------------- | ---------------- | ------ | ---------------------------------------------------- |
| Created daily transaction summary Gold table    | Manthena Bhavana | Done   | `week07_Gold_Table_Daily_Transaction_Summary.png`    |
| Created customer transaction summary Gold table | Manthena Bhavana | Done   | `week07_Gold_Table_Customer_Transaction_Summary.png` |
| Created fraud summary Gold table                | Manthena Bhavana | Done   | `week07_Gold_Table_Fraud_Summary.png`                |
| Created daily fraud cases summary               | Manthena Bhavana | Done   | `week07_Gold_Table_Fraud_Cases_by_Day.png`           |
| Created merchant risk tier summary              | Manthena Bhavana | Done   | `week07_Gold_Table_Merchant_Risk_Tier_Summary.png`   |
| Created merchant country summary                | Manthena Bhavana | Done   | `week07_Gold_Table_Merchant_Country_Summary.png`     |
| Created merchant status summary                 | Manthena Bhavana | Done   | `week07_Gold_Table_Merchant_Status_Summary.png`      |
| Validated Gold tables and checked row counts    | Manthena Bhavana | Done   | `week07_Gold_Table_Validation.png`                   |

---


## 3. Key Decisions

- Used Spark SQL to create the Gold-layer aggregation tables.
- Created separate summary tables for transactions, customers, fraud cases, and merchants to make the data dashboard-ready.
- Added merchant-level summaries based on risk tier, country, and merchant status.
---

## 4. Blockers / Risks
| Blocker                                                                                        | Impact                              | Help Needed                                                     |
| ---------------------------------------------------------------------------------------------- | ----------------------------------- | --------------------------------------------------------------- |
| Initial merchant summary used column names that were not present in the trusted merchant table | Gold merchant table creation failed | Corrected the SQL using the available merchant schema           |
| Validation query initially contained unwanted text/parameter `$0`                              | SQL parsing error during validation | Removed the extra text and executed the clean `UNION ALL` query |

---

## 5. Evidence Added to GitHub

- week07_Gold_Table_Customer_Transaction_Summary.png
- week07_Gold_Table_Daily_Transaction_Summary.png
- week07_Gold_Table_Fraud_Cases_by_Day.png
- week07_Gold_Table_Fraud_Summary.png
- week07_Gold_Table_Merchant_Country_Summary.png
- week07_Gold_Table_Merchant_Risk_Tier_Summary.png
- week07_Gold_Table_Merchant_Status_Summary.png
- week07_Gold_Table_Validation.png
- Gold-layer Spark SQL notebook updated with the Gold table creation and validation queries.

---

## 6. AI Transparency Note

| Question                                | Response                                                                                                                                                                                                                                                                                                                       |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Where AI helped**                     | AI helped in writing and simplifying Spark SQL queries for creating Gold-layer summary tables and validation queries.                                                                                                                                                                                                          |
| **What we changed after AI suggestion** | We modified the merchant summary query to match the actual `trusted_merchants` schema. For example, incorrect fields such as `merchant_name`, `category`, `city`, `state`, and `country` were replaced with available fields such as `merchant_label`, `merchant_category`, `merchant_country_code`, and `merchant_risk_tier`. |
| **What we verified manually**           | We manually checked the trusted table schema, corrected column names, executed the SQL queries in Databricks, and verified the Gold tables using row-count validation.                                                                                                                                                         |
| **What we can explain without AI**      | We can explain the purpose of the Gold layer, SQL aggregation functions such as `COUNT`, `SUM`, and `AVG`, `GROUP BY`, joins between trusted tables, and how the Gold tables support dashboard-ready KPI analysis.                                                                                                             |

---

## 7. Next Week Preparation

- Review the Gold-layer KPI tables and ensure the metrics are correct.
- Prepare the Gold data for dashboard/visualization development.
