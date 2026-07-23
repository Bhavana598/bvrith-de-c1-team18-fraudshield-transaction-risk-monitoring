# Data Dictionary

**Week:** 2  
**Purpose:** Define raw, reference, Silver, and streaming fields.

---

## 1. Source File Catalog

| File Name | Grain | Purpose | Approx. Rows | Notes |
|---|---|---|---:|---|
| transactions.csv | One row per transaction | stores all payment transaction | [rows] | [notes] |
| `[source_file_2].csv` | One row per [entity/event] | [Purpose] | [rows] | [notes] |
| `[reference_file].csv` | One row per [reference item] | [Purpose] | [rows] | [notes] |
| `[streaming_events].json` | One row per event | Streaming simulation | [rows] | JSON event files |

---

## 2. Raw File Schema: transaction.csv

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| transaction_id | string | Yes | TXN000001 | Unique transaction ID |
| customer_id | string | Yes | CUST101 | Customer identifier |
| merchant_id | string | Yes | MER205 | Merchant identifier |
| device_id | string | Yes | DEV090 | Device identifier |
| transaction_amount | decimal | Yes | 1520.75 | Transaction amount |
| transaction_time | timestamp | Yes | 2026-07-03 10:30:00 | Transaction time |
| payment_method | string | Yes | UPI` | Payment type |
| fraud_label | integer | Yes | 0 | 0 = Genuine, 1 = Fraud |

---

## 3. Raw File Schema: `[source_file_2].csv`

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| `source_id` | string | Yes | `SRC2-0001` | Unique source record ID |

---

## 4. Reference File Schema

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| merchant_id | string | Yes | MER205 | Merchant ID |
| merchant_name | string | Yes | ABC Store | Merchant name |
| category | string | Yes | Grocery | Merchant category |

---

## 5. Canonical Silver Table Design

Final Silver table name:

```text
silver_[project_specific_table_name]
```

| Silver Field | Data Type | Source Mapping | Business Meaning |
|---|---|---|---|
| `record_id` | string | `[source field]` | Canonical record ID |
| `event_date` | date | `[source field]` | Date used for analytics |
| `[silver_field]` | [type] | [mapping] | [meaning] |

---

## 6. Streaming Event Schema

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| event_id | string | Yes | EVT-0001 | Eevent ID |
| event_timestamp | timestamp | Yes | 2026-07-03T10:15:00+05:30 | Event timestamp |
| transaction_id | string | Yes | TXN000001 | Related transaction |
| event_type | string | Yes | TRANSACTION_CREATED | Event category |
