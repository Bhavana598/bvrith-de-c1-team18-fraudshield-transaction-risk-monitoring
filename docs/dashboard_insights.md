# Dashboard Insights

**Week:** 8  
**Purpose:** Explain what the Power BI dashboard shows.

---

## 1. Dashboard Pages

| Page | Purpose | Main Visuals |
|---|---|---|
| Page 1: Fraud & Transaction Risk Overview | Provide a high-level view of transaction activity and fraud risk | KPI cards, daily transaction trend, merchant risk-tier comparison, daily fraud trend, transaction-date slicer |

---

## 2. Key Insights

1. The dashboard reports a total of 278,000 transactions from the approved Gold transaction summary output.

2. The total transaction amount shown in the dashboard is approximately 141.01M.

3. The dashboard reports 54 high-risk transactions.

4. The Gold fraud summary contains 4,117 total fraud cases, displayed as approximately 4K in the Power BI KPI card because of display-unit formatting.

5. The Daily Transaction Trend shows variation in transaction volume across the available transaction dates.

6. Transaction activity is compared across HIGH, LOW, and MEDIUM merchant risk tiers.

7. The Daily Fraud Cases visual shows the fraud-case values across the available case dates.

---

## 3. How the Dashboard Uses Gold Tables

| Dashboard Page | Gold Table Used | Important Fields |
|---|---|---|
| Fraud & Transaction Risk Overview | `gold_daily_transaction_summary` | `transaction_date`, `total_transactions`, `total_amount_reporting_inr`, `high_risk_transactions` |
| Fraud & Transaction Risk Overview | `gold_fraud_summary` | `total_fraud_cases`, `transaction_linked_cases`, `avg_case_resolution_hours` |
| Fraud & Transaction Risk Overview | `gold_daily_fraud_summary` | `case_date`, `total_fraud_cases`, `linked_transaction_cases`, `avg_resolution_hours` |
| Fraud & Transaction Risk Overview | `gold_merchant_risk_tier_summary` | `merchant_risk_tier`, `total_transactions`, `high_risk_transactions`, `avg_risk_score` |

---

## 4. Power BI Validation

- [x] Dashboard connects to Gold outputs only.
- [x] Transaction Date slicer is available.
- [x] KPI totals were checked against Gold table results.
- [x] Total Transactions reconciled: Gold = 278,000; Power BI = 278K display.
- [x] Total Fraud Cases reconciled: Gold = 4,117; Power BI = 4K display.
- [x] Screenshots are saved in `screenshots/`.
- [x] Dashboard visuals are based on approved Gold outputs.
- [x] Dashboard story is explainable from the available Gold data.

---

## 5. Week 8 Scope

This dashboard is the first working Gold-traceable Power BI dashboard.

The dashboard focuses on transaction volume, transaction amount,
high-risk transactions, fraud cases, transaction trends, merchant
risk-tier comparison, and daily fraud trends.

Further dashboard refinement and deeper insight development can be
continued in the subsequent project work.
