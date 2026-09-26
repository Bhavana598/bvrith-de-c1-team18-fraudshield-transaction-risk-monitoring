# Dashboard Insights

**Week:** 9  
**Purpose:** Explain the Power BI dashboard findings, validation results, and key insights from the approved Gold outputs.

---

## 1. Dashboard Page

| Page | Purpose | Main Visuals |
|---|---|---|
| Page 1: Fraud & Transaction Risk Overview | Provide a high-level view of transaction activity and fraud risk | KPI cards, daily transaction trend, merchant risk-tier comparison, daily fraud trend, transaction-date slicer |

---

## 2. Key Insights

1. The dashboard reports a total of **278,000 transactions** across the available reporting period.

2. The total transaction amount is approximately **₹2.54 billion**.

3. The dashboard reports **653 high-risk transactions** across the reporting period.

4. The Gold fraud summary contains **4,117 total fraud cases**, which matches the Total Fraud Cases KPI in Power BI.

5. Merchant risk-tier analysis shows that **LOW-risk merchants account for 198,301 transactions**, followed by **MEDIUM-risk merchants with 65,725** and **HIGH-risk merchants with 13,974**.

6. The LOW-risk merchant tier represents approximately **71.3%** of total transactions, while MEDIUM-risk and HIGH-risk tiers represent approximately **23.6%** and **5.0%**, respectively.

7. The Daily Transaction Trend shows variation in transaction volume across the available transaction dates, with daily transaction counts generally around the 1.5K range.

8. The Daily Fraud Cases visual shows variation in fraud cases across case dates. For example, the Gold data records **8 fraud cases on 01 January 2026, 25 on 02 January, 29 on 03 January, and 30 on 04 January**.

---

## 3. How the Dashboard Uses Gold Tables

| Dashboard Page | Gold Table Used | Important Fields |
|---|---|---|
| Fraud & Transaction Risk Overview | `gold_daily_transaction_summary` | `transaction_date`, `total_transactions`, `total_amount_reporting_inr`, `high_risk_transactions` |
| Fraud & Transaction Risk Overview | `gold_daily_fraud_summary` | `case_date`, `total_fraud_cases`, `linked_transaction_cases`, `avg_resolution_hours` |
| Fraud & Transaction Risk Overview | `gold_merchant_risk_tier_summary` | `merchant_risk_tier`, `total_transactions`, `high_risk_transactions`, `avg_risk_score` |
| Fraud & Transaction Risk Overview | `fraud_summary` | Overall fraud-related summary fields |

---

## 4. Date Filtering and Power BI Validation

- [x] Dashboard connects to Gold outputs only.
- [x] Shared `DateTable` was created for date filtering.
- [x] `DateTable` is related to the daily transaction and daily fraud Gold tables.
- [x] Transaction Date slicer uses `DateTable[Date]`.
- [x] Transaction Date slicer changes the KPI cards and dashboard visuals.
- [x] Total Transactions changes according to the selected date.
- [x] Total Transaction Amount changes according to the selected date.
- [x] High-Risk Transactions changes according to the selected date.
- [x] Total Fraud Cases changes according to the selected date.
- [x] Daily Transaction Trend responds to the date filter.
- [x] Daily Fraud Cases responds to the date filter.
- [x] Merchant Risk Tier visual responds to the date filter.

---

## 5. Gold-to-Power BI Reconciliation

| KPI | Gold Value | Power BI Value | Status |
|---|---:|---:|---|
| Total Transactions | 278,000 | 278K | Reconciled |
| Total Transaction Amount | Approximately ₹2.54B | 2.54B | Reconciled |
| High-Risk Transactions | 653 | 653 | Reconciled |
| Total Fraud Cases | 4,117 | 4.117K | Reconciled |

The dashboard KPI values were checked against the corresponding Gold outputs after the complete CSV exports were regenerated.

---

## 6. Gold Export Validation

The Power BI export queries were updated to remove the temporary `LIMIT 10` restriction.

The final export process uses the complete Gold table outputs so that the Power BI dashboard represents the full available dataset rather than a 10-row preview.

---

## 7. Week 9 Scope

Week 9 focused on refining, validating, and explaining the existing Gold-traceable Power BI dashboard.

The work included:

- Completing the Gold-to-Power BI exports.
- Validating the complete transaction and fraud data.
- Creating a shared DateTable for date filtering.
- Validating relationships and slicer interactions.
- Reconciling dashboard KPIs with Gold outputs.
- Validating daily transaction and fraud trends.
- Reviewing merchant risk-tier distribution.
- Developing evidence-backed dashboard insights.

The dashboard is now validated for date filtering, Gold reconciliation, and presentation of transaction and fraud-risk information.
