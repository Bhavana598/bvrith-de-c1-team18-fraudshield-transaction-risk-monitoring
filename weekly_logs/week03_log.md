# Week 03 Log — Data Exploration and Validation

**Week:** 3  
**Date range:**  25/7/2026 - 30/7/2026
**Team:** Team 18  
**Project:** Fraud Shield: Transaction Risk Monitoring

---

## 1. Sprint Goal

The goal of Week 3 was to explore the Fraud Shield source datasets in Databricks using PySpark and Spark SQL. We focused on understanding the schemas, validating data quality, checking relationships between datasets, and preparing the data for the next stage of the data engineering pipeline.

---

## 2. Work Completed

| Task                                                               | Owner   | Status | Evidence                              |
| ------------------------------------------------------------------ | ------- | ------ | ------------------------------------- |
| Created the required Databricks schema                             | Keerthana Satuluri | Done   | Schema creation screenshot |     
| Uploaded project source files to Databricks Volume                 | Keerthana Satuluri | Done   | Data loaded screenshot     |
| Loaded and explored the transaction Parquet dataset                | Keerthana Satuluri | Done   | Transaction Output screenshot|
| Created temporary SQL views for data exploration                   | Keerthana Satuluri | Done   | Databricks notebook        |
| Performed Spark SQL exploration on transaction data                | Keerthana Satuluri | Done   | SQL output screenshot      |
| Checked missing/null values in important transaction fields        | Keerthana Satuluri | Done   | Missing-values screenshot  |
| Validated relationships between transaction and reference datasets | Keerthana Satuluri | Done   | Relationship-check screenshot  |
| Updated the Week-3 data exploration notebook                       | Keerthana Satuluri | Done  | `notebooks/01_data_exploration.ipynb` |


---

## 3. Key Decisions

- Used Spark SQL as the primary method for data exploration while using simple PySpark for loading files, creating DataFrames, inspecting schemas, and creating temporary views.
- Kept Week-3 work focused on exploration and validation without implementing the complete Bronze, Silver, or Gold layers.


---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Original transaction Parquet contained an unsupported nanosecond timestamp type | Transaction data could not initially be loaded in Databricks | Converted/replaced the file with a Databricks-compatible Parquet file |
| Databricks session variables may reset between executions | Previously created DataFrames/views may need to be recreated | Rerun initialization and DataFrame creation cells when the session restarts |


---

## 5. Evidence Added to GitHub

- `notebooks/01_data_exploration.ipynb`
- Screenshot of Databricks schema creation
- Screenshot of source files uploaded to the Volume
- Screenshot of transaction Parquet successfully loaded
- Screenshot of Spark SQL exploration output
- Screenshot of missing-value/data-quality validation
- Screenshot of relationship validation

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI was used for guidance on structuring the Week-3 exploration notebook, understanding Databricks errors, and suggesting appropriate Spark SQL data-quality and relationship checks. |
| What we changed after AI suggestion | We adapted the suggested queries and notebook steps to the actual Fraud Shield datasets, Databricks Volume paths, schemas, and available columns. |
| What we verified manually | We manually verified that source files were uploaded correctly, DataFrames loaded successfully, schemas matched the datasets, SQL queries executed, and validation results were generated in Databricks. |
| What we can explain without AI | We can explain the project datasets, DataFrame creation, schema inspection, temporary SQL views, SQL exploration, missing-value checks, business-key checks, and relationship validation performed during Week 3. |


---

## 7. Next Week Preparation

- Prepare for Week 4 Bronze-layer ingestion using the findings from Week-3 exploration.
- Review identified data-quality and relationship issues before implementing ingestion logic.
- Keep Week-3 exploration evidence and results available for validation during Week 4.
