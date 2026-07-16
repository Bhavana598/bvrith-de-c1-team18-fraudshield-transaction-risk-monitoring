# Problem Charter

**Week:** 1  
**Owner(s):** Manthena Bhavana, Satuluri Keerthana, E.Shivani
**Project:** Fraud Sheils:Transaction risk monitoring

---

## 1. Problem Context

Banking / finance risk analytics — fully synthetic and educational; no real customer,
account, card, merchant, or bank data

Prompts:

- What real-world process or operation does this project represent?
- What kinds of data are generated?
- Why is raw data not enough?
- Who would use the final dashboard or metrics?

---

## 2. Engineering Problem

FraudShield-Transaction Risk Monitoring:
A fully synthetic transaction-risk data product: transactions, accounts, merchants, risk rules, fraud flags,
authorization decisions, and live transaction events. You will turn controlled financial-risk files into a trusted
lakehouse pipeline and a decision dashboard, then prove every step on GitHub.
The project convert multiple raw source files into trusted Bronze, Silver, Data Quality, Gold, and dashboard-ready outputs using Databricks and Power BI.

## 3. Users / Stakeholders

| User / Stakeholder | What they need from the data |
|---|---|
| Fraud Risk Manager | Identify which fraud rules, payment channels, merchant categories, and risk bands generate the highest number of flagged transactions to optimize fraud detection strategies and reduce false positives. |
| Payments Operations Lead | Monitor approval, decline, and flagged transaction volumes across batch transaction files and live event streams to ensure operational consistency and quickly detect processing issues. |
| Compliance / AML Analyst | Analyze suspicious transaction patterns by merchant category, customer/account segment, geographic region, and transaction amount band to support AML investigations and regulatory compliance. |
| Live Authorization Desk | View a real-time dashboard of approved, declined, and flagged transactions, ensuring duplicate events are removed and authorization decisions are accurately reflected for immediate operational response. |

---

## 4. Scope Inclusions

List what the team will build.

- Raw source files
- Bronze ingestion
- Silver standardization
- Data quality checks
- Gold metrics
- Power BI dashboard
- Streaming simulation
- GitHub evidence

---

## 5. Scope Exclusions

List what the team will not build.

Examples:

- A banking app, payment gateway, or fraud-detection ML
product
- A use of real bank, card, account, customer, or merchant
transaction data
- Charts drawn directly from raw transaction exports
- A big-reveal project that appears in Week 11
- Unexplained AI-generated notebooks
---

## 6. Success Criteria

By the end of 12 weeks, the project is successful if:

- The pipeline can be explained end to end.
- The team can show Bronze, Silver, DQ, Gold, dashboard, and streaming evidence.
- All three students can explain the full project at a high level.
- GitHub contains weekly evidence and final submission files.
