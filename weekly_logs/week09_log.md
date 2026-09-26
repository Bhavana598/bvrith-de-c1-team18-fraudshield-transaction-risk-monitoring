# Week 09 Log — FraudShield Dashboard Refinement

**Week:** 9  
**Date range:** 19/09/26 - 24/09/26  
**Team:** Team 18  
**Project:** FraudShield — Transaction Risk Monitoring

---

## 1. Sprint Goal

Refine and validate the existing Gold-traceable Power BI dashboard and ensure that all dashboard KPIs and visuals reconcile with the approved Gold outputs.

Improve dashboard usability through date filtering, visual validation, and evidence-backed insights, and prepare the required documentation and evidence for the Week 9 submission.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Corrected Gold-to-Power BI export queries by removing `LIMIT 10` | Keerthana Satuluri | Done | `notebooks/06_powerbi_export.ipynb` |
| Regenerated complete Gold CSV exports | Keerthana Satuluri | Done | Gold CSV export files |
| Loaded complete transaction data into Power BI | Keerthana Satuluri | Done | `dashboard/powerbi_dashboard.pbix` |
| Created shared `DateTable` for dashboard filtering | Keerthana Satuluri | Done | Power BI data model |
| Created relationships between `DateTable` and daily Gold tables | Keerthana Satuluri | Done | Power BI model |
| Updated Transaction Date slicer to use `DateTable[Date]` | Keerthana Satuluri | Done | Power BI dashboard |
| Validated date filtering across KPI cards and visuals | Keerthana Satuluri | Done | Week 9 dashboard screenshots |
| Reconciled Total Transactions with Gold | Keerthana Satuluri | Done | Gold query result + Power BI KPI |
| Reconciled Total Transaction Amount with Gold | Keerthana Satuluri | Done | Gold query result + Power BI KPI |
| Reconciled High-Risk Transactions with Gold | Keerthana Satuluri | Done | Gold query result + Power BI KPI |
| Reconciled Total Fraud Cases with Gold | Keerthana Satuluri | Done | Gold query result + Power BI KPI |
| Fixed Daily Fraud Cases visual to display daily values correctly | Keerthana Satuluri | Done | Power BI dashboard |
| Validated merchant risk-tier transaction distribution | Keerthana Satuluri | Done | Gold query result |
| Prepared evidence-backed dashboard insights | Keerthana Satuluri | Done | `docs/dashboard_insights.md` |

---

## 3. Key Decisions

- Removed the temporary `LIMIT 10` restriction from the Power BI Gold export queries so that the complete Gold data is exported.
- Used a shared `DateTable` instead of creating direct relationships between independent Gold summary tables.
- Changed the dashboard date slicer to use `DateTable[Date]` so that all relevant visuals respond consistently to date selection.
- Kept the existing Power BI dashboard structure instead of creating a new dashboard.
- Used Gold outputs as the source of truth for KPI reconciliation.
- Verified the Daily Fraud Cases visual against the daily Gold fraud data before finalizing the dashboard.
- Used actual Gold values for dashboard insights instead of manually estimated or assumed values.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Power BI Gold CSV exports initially contained only 10 rows because the export queries used `LIMIT 10` | Dashboard KPIs did not represent the complete Gold dataset | Identified and removed `LIMIT 10` from the export queries |
| Total Fraud Cases initially did not respond to the transaction-date slicer | Date filtering was inconsistent across visuals | Created a shared `DateTable` and connected it to the daily Gold tables |
| Daily Fraud Cases visual initially displayed an incorrect flat trend | Daily fraud pattern could not be interpreted correctly | Verified the Gold daily fraud data and corrected the Power BI visual configuration |

---

## 5. Evidence Added to GitHub

- `dashboard/powerbi_dashboard.pbix` updated with the final validated dashboard.
- `dashboard/README.md` updated with dashboard and model details.
- `docs/dashboard_insights.md` updated with Week 9 evidence-backed insights.
- `notebooks/06_powerbi_export.ipynb` updated to export complete Gold data without `LIMIT 10`.
- Week 9 dashboard screenshots added to `screenshots/`.
- `weekly_logs/week09_log.md` added with sprint activities and validation results.

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI assisted with Power BI troubleshooting, identifying the cause of incomplete CSV exports, designing the shared DateTable approach, validating dashboard filter behaviour, and structuring the Week 9 documentation and insights. |
| What we changed after AI suggestion | The `LIMIT 10` restriction was removed from the Gold export queries, a shared `DateTable` was created, Power BI relationships and the date slicer were updated, and the Daily Fraud Cases visual was corrected. |
| What we verified manually | Gold totals were queried directly and compared with Power BI KPI values. Date filtering was manually tested using different dates. Daily fraud data and merchant risk-tier values were also checked against the Gold outputs. |
| What we can explain without AI | The team can explain the Gold-to-Power BI data flow, the purpose of the DateTable and relationships, KPI reconciliation, dashboard filter behaviour, merchant risk-tier distribution, and the insights derived from the Gold data. |

---

## 7. Next Week Preparation

- Preserve the final validated Power BI dashboard and Gold-to-Power BI data flow.
- Review the completed dashboard documentation and evidence before the next project phase.
- Ensure the final PBIX, notebook, screenshots, insights, and weekly log are committed to GitHub.
- Prepare for the next project phase involving subsequent data engineering and dashboard work.
