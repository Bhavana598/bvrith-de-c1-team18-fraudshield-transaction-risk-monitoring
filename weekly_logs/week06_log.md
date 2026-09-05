# Week 06 Log — Data Quality Checks

**Week:** 6  
**Date range:** 31/8/2026 - 6/9/2026  
**Team:** 18  
**Project:** FraudSheild - Transaction risk monitoring

---

## 1. Sprint Goal

Data Quality Checks - Validate the Silver layer data and separate valid records from invalid records.

The goal of this week was to implement data quality rules, identify failed records, and route records into Trusted and Quarantine tables for reliable downstream processing.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
| --- | --- | --- | --- |
| Implemented data quality checks on Silver tables | Keerthana Satuluri | Done | `04_week6_data_quality_checks_sparksql.ipynb` |
| Performed required ID and business key null checks | Keerthana Satuluri | Done | Data quality notebook |
| Performed duplicate key checks | Keerthana Satuluri | Done | Data quality notebook |
| Validated customer, account, merchant, device and transaction references | Keerthana Satuluri | Done | Data quality notebook |
| Implemented numeric range validation checks | Keerthana Satuluri | Done | Data quality notebook |
| Implemented timestamp and chronology validation checks | Keerthana Satuluri | Done | Data quality notebook |
| Implemented data lineage checks using source and ingestion metadata | Keerthana Satuluri | Done | Data quality notebook |
| Created Trusted tables for records that passed all quality checks | Keerthana Satuluri | Done | Databricks Trusted tables |
| Created Quarantine tables for records that failed one or more quality checks | Keerthana Satuluri | Done | Databricks Quarantine tables |
| Added failed rule IDs and DQ status to identify failed records | Keerthana Satuluri | Done | Data quality results tables |
| Performed candidate, trusted and quarantine row count reconciliation | Keerthana Satuluri | Done | Reconciliation query in notebook |
| Added Week 6 documentation and evidence to GitHub | Keerthana Satuluri | Done | GitHub files and screenshots |

---

## 3. Key Decisions

- Used the existing Silver tables as the input layer for Week 6 data quality validation.
- Implemented data quality checks before allowing records to move into the Trusted layer.
- Routed records that passed all checks to Trusted tables.
- Routed records that failed one or more checks to Quarantine tables instead of deleting them.
- Added failed rule IDs to make it easier to identify the reason for data quality failures.
- Performed reconciliation to ensure that every candidate record was routed to either Trusted or Quarantine.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
| --- | --- | --- |
| Ambiguous column references during joins | Some data quality queries failed because multiple tables contained columns with the same names | Resolved by using table aliases such as `t.`, `c.`, `a.`, `d.`, `m.` and `f.` |
| Invalid or inconsistent references in Silver data | Records with invalid customer, account, merchant or device references could affect downstream analysis | Failed records were routed to Quarantine tables |
| Invalid timestamps or chronology | Incorrect timestamp order could affect transaction and fraud analysis | Implemented timestamp chronology validation checks |
| Invalid numeric values and risk scores | Incorrect values could affect financial and fraud metrics | Implemented numeric range and risk score checks |
| Large number of transaction quality failures | Transactions had the highest number of quarantined records and could affect downstream dashboards | Excluded failed records from Trusted datasets and preserved them for investigation |

---

## 5. Evidence Added to GitHub

- Weekly_logs: `week06_log.md` updated
- `data_quality_summary.md` added
- `04_week6_data_quality_checks_sparksql.ipynb` notebook updated
- Data Quality Summary screenshot added
- Trusted records screenshot added
- Quarantine records screenshot added
- Reconciliation results screenshot added

---

## 6. AI Transparency Note

| Question | Response |
| --- | --- |
| Where AI helped | AI helped in designing the Spark SQL data quality checks, creating validation logic, identifying ambiguous column reference issues, and structuring Trusted and Quarantine routing. |
| What we changed after AI suggestion | We adapted the SQL queries to match our actual Silver table names, column names, Databricks catalog and schema. We also added table aliases to resolve ambiguous column reference errors during joins. |
| What we verified manually | We manually ran the queries in Databricks, verified the Silver table names and columns, checked Trusted and Quarantine tables, reviewed failed records, and verified that candidate rows equaled Trusted rows plus Quarantine rows. |
| What we can explain without AI | We can explain the purpose of data quality checks, the implemented validation rules, Trusted and Quarantine routing, failed rule IDs, reference validation, timestamp checks, and the reconciliation process used to verify that all records were correctly routed. |

---

## 7. Next Week Preparation

- Use the Trusted datasets as the source for creating Gold layer tables.
- Design business-focused Gold tables for transaction risk monitoring and fraud analysis.
- Create aggregated metrics and KPIs for dashboards and reporting.
- Ensure that Quarantine records are excluded from Gold layer calculations unless corrected and revalidated.
