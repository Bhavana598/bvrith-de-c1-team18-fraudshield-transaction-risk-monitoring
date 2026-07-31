# Week 04 Log — Bronze Ingestion

**Week:** 4  
**Date range:** 31/7/2026  
**Team:** 18 
**Project:** TRANSACTION RISK MONITORING

---

## 1. Sprint Goal

Implement the Bronze layer of the data pipeline by loading raw source files into Databricks, creating Bronze Delta tables, adding ingestion metadata, and validating the data using record count reconciliation.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|------|-------|--------|----------|
| Loaded source files into Databricks Volume | Manthena Bhavana, Satuluri Keerthana | Done | 02_bronze_ingestion.ipynb |
| Created Bronze tables for all source files | Manthena Bhavana, Satuluri Keerthana | Done | 02_bronze_ingestion.ipynb |
| Added ingestion metadata columns | Manthena Bhavana, Satuluri Keerthana | Done | Bronze tables |
| Verified source and Bronze record counts | Manthena Bhavana, Satuluri Keerthana | Done | week04_bronze_counts.png |
| Captured Bronze table screenshots | Manthena Bhavana | Done | week04_bronze_table_created.png |

---

## 3. Key Decisions

- Used Delta tables as the Bronze storage layer.
- Preserved raw source data without applying transformations, while adding ingestion metadata.

---

## 4. Blockers / Risks


| Blocker | Impact | Help Needed |
|----------|--------|-------------|
| Parquet timestamp compatibility issue in `transactions.parquet` | Original file could not be read in Databricks | Used the Databricks-compatible Parquet file to complete Bronze ingestion |

---

## 5. Evidence Added to GitHub

- File updated
- Screenshot added
- Notebook updated

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | Assisted with Spark SQL, Databricks notebook creation, debugging errors, and understanding Bronze ingestion. |
| What we changed after AI suggestion | Replaced unsupported functions, and corrected SQL/Python notebook issues. |
| What we verified manually | Verified Bronze tables, metadata columns, and source/Bronze record counts in Databricks. |
| What we can explain without AI | Bronze layer concepts, Delta table creation, metadata columns, ingestion workflow, and reconciliation process. |

---

## 7. Next Week Preparation

- Begin implementing the Silver layer with data cleaning and transformations.
- Prepare notebooks and validation steps for Silver data processing.
