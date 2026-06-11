# ShopVista-Retail-Intelligence-End-to-End-Data-Pipeline [Data Engineering using Spark & Azure Databricks]


# Project Overview & Scope of Work



Doc : [shopvista_scope_of_work.pdf](https://github.com/user-attachments/files/28826049/shopvista_scope_of_work.pdf)

---




# Business Challenges




---


# Pipeline Architecture 

<img width="8107" height="3420" alt="Image" src="https://github.com/user-attachments/assets/7471c7fd-1432-4dd6-949b-4c95ce535d37" />

Azure-based Medallion Architecture (Bronze → Silver → Gold) built using ADLS Gen2, Unity Catalog, and Azure Databricks. Raw e-commerce data is centralized in Azure Data Lake, transformed through ETL/ELT pipelines, and published as analytics-ready datasets for Power BI reporting.
.
Key Highlights :



---

# Azure Resource 
<img width="1641" height="670" alt="Image" src="https://github.com/user-attachments/assets/82e0b19e-f62c-49a5-bbe0-7fce665bf485" />

Provisioned Azure resources including Storage Accounts, Azure Data Lake Storage Gen2, Databricks Workspace, Unity Catalog, and secure access configurations required for building a scalable cloud-native data platform.

---



# Azure Data Lake 

<img width="637" height="659" alt="Image" src="https://github.com/user-attachments/assets/55ca40cf-0640-41b4-a80d-d15c4bbe424e" />

Centralized enterprise data lake used as the landing zone for raw source files. Implements a structured folder hierarchy supporting Bronze, Silver, and Gold layers for governed data processing and storage.


---

# Storage Account 
<img width="1623" height="903" alt="Image" src="https://github.com/user-attachments/assets/94617bf9-77d5-48f5-80c5-e6b5e880f597" />

Configured Azure Storage Account hosting ADLS Gen2 containers for raw, processed, and curated datasets. Provides scalable storage, secure access control, and seamless integration with Azure Databricks.

--- 

# SQL Warehouse 
<img width="1918" height="850" alt="Image" src="https://github.com/user-attachments/assets/67089996-52ff-4ffe-b22f-b842699cb47c" />


---


# Medallion Architecture - Data Layers [Bronze & Silver]
<img width="6000" height="3375" alt="Image" src="https://github.com/user-attachments/assets/0ae52826-7ef8-4a78-afb0-991bee31ec81" />

Bronze Layer --

Automated ingestion pipelines load raw source datasets into Delta tables while preserving original data quality. Metadata such as ingestion timestamps and source file tracking are captured for auditability and lineage.

Silver Layer --

Applied data cleansing, schema enforcement, standardization, deduplication, anomaly correction, and business transformation rules to create trusted and validated datasets for downstream consumption.


---

# Medallion Architecture - Gold Data Layer

<img width="6000" height="3375" alt="Image" src="https://github.com/user-attachments/assets/48fe2fcb-97b3-4eb8-9bea-929a5326df6e" />

Built business-ready dimensional and fact tables using star-schema modeling. Aggregated KPIs, customer intelligence, product dimensions, and transactional datasets optimized for analytics and reporting workloads.

---

# Job Orchestration & Automation
# Daily Refresh Pipeline

<img width="6000" height="3375" alt="Image" src="https://github.com/user-attachments/assets/3395b324-552c-4533-9639-9e0adb2e1d83" />

Implemented automated pipeline execution using Databricks workflows and structured streaming. Supports incremental processing, checkpointing, change data capture, and reliable end-to-end data movement.

Daily Refresh Pipeline --

Automated daily incremental refresh process that recalculates business KPIs, updates summary tables, and ensures Power BI dashboards always reflect the latest operational data.

---

# Analytics & Report

<img width="4150" height="2400" alt="Image" src="https://github.com/user-attachments/assets/f4ac2c1b-a7d1-4970-8b13-7ccd03231aa4" />

Interactive Power BI dashboard built on Gold-layer datasets delivering insights into sales performance, product trends, customer behavior, revenue growth, discount analysis, and business KPIs through a single source of truth.

---

