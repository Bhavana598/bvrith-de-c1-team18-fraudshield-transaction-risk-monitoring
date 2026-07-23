# Week 02 Log — Dataset design + data dictionary

**Week:** 2  
**Date range:**  17/7/2026 -  24/7/2026
**Team:** 18  
**Project:** FraudShield - Transaction Risk Monitoring

---
## 1. Sprint Goal

The goal of this week is to design the project dataset by documenting the source files, data dictionary, primary and foreign keys, and synthetic data assumptions. We also prepared small raw sample files and updated the synthetic data generator to support consistent and reliable data processing for the FraudShield pipeline.

---
## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Updated `docs/data_dictionary.md`  | Manthena Bhavana, Satuluri Keerthana | Done | `docs/data_dictionary.md` |
| Updated `docs/synthetic_data_assumptions.md` | Manthena Bhavana | Done | `docs/synthetic_data_assumptions.md` |
| Updated `src/generate_synthetic_data.py` | Satuluri Keerthana | Done | `src/generate_synthetic_data.py` |
| Added small raw sample files to `data_sample/raw/` | Satuluri Keerthana | Done | `data_sample/raw/` |
| Reviewed dataset design and documented primary/foreign key relationships | Manthena Bhavana, Satuluri Keerthana | Done | `docs/data_dictionary.md` |
| Captured Week 2 evidence screenshots | Manthena Bhavana | Done | `week02_data_dictionary_completed.png`, `week02_raw_sample_files.png` |
---
## 3. Key Decisions

- Chose a standardized data dictionary to clearly define source files, field names, data types, and key relationships.
- Used synthetic sample data instead of real financial data to ensure privacy and support safe educational testing.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Understanding the project-specific dataset structure and field mappings | May delay completion of the data dictionary and generator updates | Review the provided project documentation and data dictionary |
| Sample data files not yet copied into `data_sample/raw/` | Week 2 deliverables remain incomplete | Copy the approved sample files from `github_safe_samples/data_sample/raw/` into the repository |

## 5. Evidence Added to GitHub

- File updated
- Screenshot added

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI assisted in understanding the Week 2 requirements, preparing the data dictionary structure. |
| What we changed after AI suggestion | Updated the documentation to match the FraudShield project, organized the dataset structure, and refined the sample data generator and supporting files. |
| What we verified manually | Verified the project files, folder structure, source file names, documentation, and ensured that all generated content matched the project requirements. |
| What we can explain without AI | We can explain the dataset design, source files, key relationships, synthetic data assumptions, sample data generation process, and the purpose of each project file. |

---

## 7. Next Week Preparation

- Prepare the data ingestion pipeline and perform initial data quality validation.
- Review the raw datasets and begin implementing the Silver layer data transformation pipeline.
