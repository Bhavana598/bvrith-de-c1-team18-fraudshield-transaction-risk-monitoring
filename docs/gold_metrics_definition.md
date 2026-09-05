# Gold Metrics Definition

**Week:** 7  
**Purpose:** Define dashboard-ready Gold tables and KPI formulas for FraudSheild - Transaction Risk Monitoring.

---

## 1. Gold Table Catalog

| Gold Table Name | Grain | Source Table(s) | Purpose |
|---|---|---|---|
| `gold_daily_transaction_summary` | One row per transaction date | `trusted_transactions` | Provides daily transaction volume, transaction value, and transaction risk metrics |
| `gold_merchant_summary` | One row per merchant | `trusted_transactions`, `trusted_merchants` | Provides merchant-level transaction activity and risk analysis |
| `gold_customer_summary` | One row per customer | `trusted_transactions`, `trusted_customers` | Provides customer-level transaction activity and risk insights |
| `gold_fraud_summary` | One row per fraud case or fraud category | `trusted_fraud_cases`, `trusted_transactions` | Provides fraud case monitoring and analysis |
| `gold_daily_fraud_summary` | One row per date | `trusted_fraud_cases` | Provides daily fraud case trends and monitoring metrics |
| `gold_merchant_risk_tier_summary` | One row per merchant risk tier | `trusted_transactions`, `trusted_merchants` | Groups merchants by risk level for risk monitoring |
| `gold_merchant_country_summary` | One row per merchant country | `trusted_transactions`, `trusted_merchants` | Provides transaction and risk analysis by merchant country |
| `gold_merchant_status_summary` | One row per merchant status | `trusted_transactions`, `trusted_merchants` | Provides transaction analysis based on merchant status |

---

## 2. KPI Definitions

| KPI Name | Formula | Grain | Dashboard Page | Notes |
|---|---|---|---|---|
| Total Transactions | `COUNT(transaction_id)` | Daily | Overview | Counts trusted transactions only |
| Total Transaction Amount | `SUM(amount_reporting_inr)` | Daily | Overview | Total trusted transaction value in INR |
| Average Transaction Amount | `AVG(amount_reporting_inr)` | Daily | Overview | Average value of trusted transactions |
| Average Risk Score | `AVG(risk_score)` | Daily | Risk Monitoring | Measures the average transaction risk level |
| High Risk Transactions | `COUNT(transaction_id WHERE risk_score >= 70)` | Daily | Risk Monitoring | High-risk threshold is defined as a risk score of 70 or above |
| High Risk Transaction Rate | `(High Risk Transactions / Total Transactions) × 100` | Daily | Risk Monitoring | Percentage of transactions classified as high risk |
| Total Fraud Cases | `COUNT(case_id)` | Daily / Overall | Fraud Monitoring | Counts trusted fraud cases |
| Active Customers | `COUNT(DISTINCT customer_id)` | Daily / Overall | Customer Analysis | Counts customers with trusted transaction activity |
| Active Merchants | `COUNT(DISTINCT merchant_id)` | Daily / Overall | Merchant Analysis | Counts merchants with trusted transaction activity |
| Merchant Transaction Volume | `COUNT(transaction_id)` | Per Merchant | Merchant Analysis | Identifies high-volume merchants |
| Merchant Average Risk Score | `AVG(risk_score)` | Per Merchant | Merchant Analysis | Helps identify merchants with higher transaction risk |
| Customer Transaction Volume | `COUNT(transaction_id)` | Per Customer | Customer Analysis | Shows customer transaction activity |
| Customer Average Risk Score | `AVG(risk_score)` | Per Customer | Customer Analysis | Helps identify customers with higher transaction risk |

---

## 3. KPI Scope and Data Rules

All Gold metrics are calculated using **Trusted datasets only**.

The following records are excluded from Gold metrics:

- Records present in Quarantine tables.
- Records that failed one or more Week 6 data quality checks.
- Records with invalid customer, account, merchant, or device references.
- Records with invalid numeric values.
- Records with invalid risk scores.
- Records with invalid timestamp chronology.

This ensures that dashboard metrics are calculated using validated and trusted data.

---

## 4. Gold Layer Data Flow

```text
Bronze Tables
      ↓
Silver Tables
      ↓
Data Quality Checks
      ↓
Trusted Tables
      ↓
Gold Tables
      ↓
Power BI Dashboard
