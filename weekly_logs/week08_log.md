# Week 08 Log — Power BI Draft

**Week:** 8  
**Date range:** September 11–September 18, 2026  
**Team:** Team18  
**Project:** FraudShield — Transaction Risk Monitoring

---

## 1. Sprint Goal

Validate the approved Gold outputs, export/connect the required Gold
tables to Power BI, build the first working dashboard, reconcile
important dashboard values with the Gold tables, and record review
evidence.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Validate approved Gold tables | Keerthana Satuluri | Done | `notebooks/05_gold_aggregations.ipynb` |
| Prepare Gold-to-Power-BI export | Keerthana Satuluri | Done | `notebooks/06_powerbi_export.ipynb` |
| Export selected Gold tables | Keerthana Satuluri | Done | Gold CSV exports / Unity Catalog Volume |
| Import Gold outputs into Power BI | Keerthana Satuluri | Done | `screenshots/week08_gold_connection.png` |
| Build KPI cards | Keerthana Satuluri | Done | `screenshots/week08_powerbi_draft.png` |
| Build Daily Transaction Trend | Keerthana Satuluri | Done | `screenshots/week08_powerbi_draft.png` |
| Build Merchant Risk Tier comparison | Keerthana Satuluri | Done | `screenshots/week08_powerbi_draft.png` |
| Build Daily Fraud Cases visual | Keerthana Satuluri | Done | `screenshots/week08_powerbi_draft.png` |
| Add Transaction Date slicer | Keerthana Satuluri | Done | `screenshots/week08_powerbi_draft.png` |
| Reconcile Total Transactions | Keerthana Satuluri | Done | Gold result: 278,000; Power BI: 278K |
| Reconcile Total Fraud Cases | Keerthana Satuluri | Done | Gold result: 4,117; Power BI: 4K |
| Prepare dashboard documentation | Keerthana Satuluri | Done | `dashboard/README.md`, `docs/dashboard_insights.md` |

---

## 3. Key Decisions

- Power BI uses approved Gold outputs only.
- The selected Gold tables were kept at their existing grains.
- Unnecessary relationships between independent Gold summary tables
  were not created.
- The first dashboard was designed around transaction and fraud-risk
  business questions rather than creating one visual for every Gold table.
- KPI values were reconciled against their owning Gold tables.
- Week 8 was kept within the first-working-dashboard scope; deeper
  dashboard refinement and insight development are reserved for Week 9.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Public DBFS/FileStore export location was disabled in the Databricks workspace. | The original `/FileStore` export path could not be used. | Unity Catalog Volume was used for the controlled Power BI export. |
| Power BI initially displayed Total Transactions as approximately 15K instead of the Gold total. | KPI reconciliation did not initially match. | The Power BI Gold export/source was checked and corrected; the final Power BI value reconciles to 278,000. |

---

## 5. Evidence Added to GitHub

- `notebooks/06_powerbi_export.ipynb`
- `dashboard/powerbi_dashboard.pbix`
- `dashboard/README.md`
- `docs/dashboard_insights.md`
- `screenshots/week08_gold_connection.png`
- `screenshots/week08_powerbi_draft.png`
- `weekly_logs/week08_log.md`

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI assisted with the Week 8 export notebook structure, SQL export troubleshooting, Power BI dashboard planning, field-to-visual mapping, documentation and troubleshooting. |
| What we changed after AI suggestion | The team adapted the export approach to the Databricks environment, used a Unity Catalog Volume instead of the disabled Public DBFS/FileStore path, selected the required Gold tables, and adjusted the Power BI dashboard based on the actual Gold outputs. |
| What we verified manually | Gold table availability, export results, Power BI Gold tables, dashboard fields, KPI values, Total Transactions reconciliation, Total Fraud Cases reconciliation, dashboard visuals, and screenshots were checked manually. |
| What we can explain without AI | We can explain the Gold-to-Power-BI flow, the purpose and grain of the selected Gold tables, the dashboard visuals, KPI calculations, Power BI source rule, reconciliation process, and the reason separate Gold summary tables were not unnecessarily related. |

---

## 7. Next Week Preparation

- Continue using the same working Power BI model.
- Refine dashboard visual hierarchy, labels, filters and usability.
- Develop clearer insight notes from the validated Gold outputs.
- Reconcile final/filtered dashboard presentations where required.
- Keep the Power BI source connected to the governed Gold hand-off.
