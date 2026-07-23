# Data Dictionary

**Week:** 2  
**Purpose:** Define raw, reference, Silver, and streaming fields.

---

## 1. Source File Catalog

| File Name | Grain | Purpose | Approx. Rows | Notes |
|---|---|---|---:|---|
| File Name             | Grain                     |                         
| transactions.csv      | One row per transaction   | Stores all payment transactions |      ~50,000 | Main transaction dataset |
| customers.csv         | One row per customer      |            Customer information |      ~10,000 | Linked by customer_id    |
| merchants.csv         | One row per merchant      |            Merchant information |       ~2,000 | Linked by merchant_id    |
| devices.csv           | One row per device        |                  Device details |       ~8,000 | Linked by device_id      |
| fraud_cases.csv       | One row per fraud case    |     Fraud investigation records |       ~1,000 | Linked by transaction_id |
| streaming_events.json | One event per transaction |      Simulated streaming events |     Variable | JSON event stream        |

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

## 3. Raw File Schema: customers.csv

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| customer_id   | string    | Yes       | CUST101      | Primary key   |
| customer_name | string    | Yes       | Rahul Sharma | Customer name |
| city          | string    | No        | Hyderabad    | Customer city |
| age           | integer   | No        | 28           | Customer age  |


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
silver_transactions
```

| Silver Field       | Data Type | Source Mapping                  | Business Meaning    |
| ------------------ | --------- | ------------------------------- | ------------------- |
| transaction_id     | string    | transactions.transaction_id     | Unique transaction  |
| customer_id        | string    | transactions.customer_id        | Customer identifier |
| merchant_id        | string    | transactions.merchant_id        | Merchant identifier |
| device_id          | string    | transactions.device_id          | Device used         |
| transaction_amount | decimal   | transactions.transaction_amount | Payment amount      |
| transaction_date   | date      | transaction_time                | Analytics date      |
| fraud_label        | integer   | fraud_label                     | Fraud indicator     |


---

## 6. Streaming Event Schema

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| event_id | string | Yes | EVT-0001 | Eevent ID |
| event_timestamp | timestamp | Yes | 2026-07-03T10:15:00+05:30 | Event timestamp |
| transaction_id | string | Yes | TXN000001 | Related transaction |
| event_type | string | Yes | TRANSACTION_CREATED | Event category |
