# Synthetic Data Assumptions

**Week:** 2  
**Purpose:** Document how educational data is created.

---

## 1. Synthetic Data Boundary

This project uses synthetic educational data only. It must not be presented as real company, customer, citizen, player, patient, government, or platform data.

---

## 2. Domain Assumptions

| Area | Assumption |
|---|---|
| Geography / scope | Synthetic transactions across multiple cities in India |
| Time period | January 2026 to June 2026 |
| Source systems | Transaction system, Customer database, Merchant database, Device database, Fraud monitoring system |
| Event types | Transaction, Login, Payment, Fraud Alert |
| Reference data | Customers, Merchants, Devices, Fraud Cases |

---

## 3. Data Volume Assumptions

| File | Approximate Rows | Reason |
|---|---:|---|
| transactions.csv | 50,000 | Large transaction dataset for analytics |
| customers.csv | 10,000 | Customer master data |
| merchants.csv | 2,000 | Merchant reference data |
| devices.csv | 8,000 | Device information |
| fraud_cases.csv | 1,000 | Fraud investigation records |
| streaming_events.json | 20,000 | Simulated real-time transaction events |

---

## 4. Controlled Data Quality Issues

| Issue Type | Approx. Share | Why Include It |
|---|---:|---|
| Duplicate IDs | 0.3% | Test duplicate detection |
| Missing Values | 2% | Test data completeness |
| Invalid Reference Keys | 0.5% | Test referential integrity |
| Invalid Transaction Amounts | 0.2% | Test validation rules |
| Timestamp Inconsistencies | 0.2% | Test chronological validation |

---

## 5. Manual Verification

Before using generated data, the team must check:

- Row counts are reasonable.
- Key fields exist.
- Dates and numeric values look realistic.
- Controlled defects exist but do not dominate the dataset.
- Source files are different enough to require real standardization.
