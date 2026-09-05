# Data Quality Summary

**Week:** 6  
**Purpose:** Summarize data quality rules, failures and business impact.

---

## 1. Overall Dataset Results

| Dataset | Candidate Rows | Trusted Rows | Quarantine Rows | Status |
|---|---:|---:|---:|---|
| Customers | 18,000 | 18,000 | 0 | PASS |
| Customer Accounts | 22,000 | 21,990 | 10 | PASS |
| Devices | 30,000 | 29,980 | 20 | PASS |
| Fraud Cases | 4,200 | 4,117 | 83 | PASS |
| Merchants | 2,800 | 2,800 | 0 | PASS |
| Transactions | 279,720 | 278,000 | 1,720 | PASS |

All datasets passed reconciliation:

**Candidate Rows = Trusted Rows + Quarantine Rows**

---

## 2. Quality Rules Implemented

The Week 6 data quality framework implemented the following categories of checks:

| Rule Category | Examples | Business Impact |
|---|---|---|
| Required Key Checks | Customer ID, Account ID, Device ID, Transaction ID | Records without valid IDs cannot be reliably identified |
| Duplicate Checks | Duplicate business keys | Duplicate records can distort reporting and metrics |
| Reference Integrity | Customer, Account, Merchant and Device references | Invalid references can cause incorrect joins |
| Numeric Range Checks | Transaction amounts, FX rates and velocity counts | Invalid values can affect financial calculations |
| Risk Score Validation | Risk score range validation | Invalid scores can affect fraud analysis |
| Timestamp Chronology | Event, authorization, settlement and outcome timestamps | Incorrect ordering affects time-based analysis |
| Lineage Checks | Source file and ingestion metadata | Missing lineage reduces traceability |

---

## 3. Failed Record Examples

The following examples were identified in the transaction quarantine dataset:

| Rule ID | Sample Record ID | Failure Reason | Action / Handling |
|---|---|---|---|
| T009 | TXN0000000060 | Invalid timestamp chronology | Quarantined |
| T007 | TXN0000000851 | Invalid numeric range | Quarantined |
| T006 | TXN0000001410 | Invalid device reference | Quarantined |
| T004 | TXN0000001455 | Invalid account reference | Quarantined |
| T003 | TXN0000001618 | Invalid customer reference | Quarantined |
| T005 | TXN0000002101 | Invalid merchant reference | Quarantined |
| T008 | TXN0000002176 | Invalid risk score | Quarantined |

Failed records were not deleted. They were routed to Quarantine tables together with their failed rule IDs for investigation.

---

## 4. What Should Block Gold Metrics?

The following failures should block or flag Gold table generation:

- **Missing or invalid business keys** because records cannot be uniquely identified.
- **Duplicate keys** because duplicates can distort aggregates and dashboard metrics.
- **Invalid customer, account, merchant or device references** because incorrect joins can produce inaccurate reporting.
- **Invalid transaction numeric values** because financial calculations may become incorrect.
- **Invalid timestamp chronology** because time-based metrics and transaction analysis may be unreliable.
- **Invalid risk scores** should be flagged because they can affect fraud-related reporting.

Quarantined records should not be included in Gold metrics unless they are corrected and revalidated.

---

## 5. Quality Summary

The Week 6 data quality pipeline successfully validated six Silver datasets and routed records into Trusted and Quarantine layers.

Customers and Merchants had no quarantined records, indicating that all records passed the implemented quality checks.

Customer Accounts had 10 quarantined records, Devices had 20, and Fraud Cases had 83.

Transactions contained the highest number of quarantined records, with 1,720 records failing one or more data quality checks.

Examples of transaction failures included invalid references, invalid numeric ranges, invalid risk scores and incorrect timestamp chronology.

Bad records were excluded from the Trusted datasets and preserved in Quarantine tables with failed rule IDs for investigation.

All six datasets successfully passed the reconciliation check, confirming that every candidate record was routed exactly into either the Trusted or Quarantine layer.

The mentor should review the transaction quality failures carefully because Transactions contain the largest number of quarantined records and have the greatest potential impact on downstream reporting and analytics.
