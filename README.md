# ShopVista-Retail-Intelligence-End-to-End-Data-Pipeline [Data Engineering using Spark & Azure Databricks]


# Project Overview & Scope of Work

The objective of the project was to centralize business data, automate daily processing pipelines, and provide analytics-ready datasets for reporting and decision-making.

Key Objectives

✔ Build a unified data architecture for orders, shipments, returns, and dimension datasets

✔ Automate ingestion, transformation, and aggregation processes

✔ Implement Bronze → Silver → Gold Medallion Architecture

✔ Deliver clean and reliable datasets for analytics

✔ Enable business reporting through interactive Power BI dashboards

✔ Create a scalable foundation for future data growth


Doc : [shopvista_scope_of_work.pdf](https://github.com/user-attachments/files/28826049/shopvista_scope_of_work.pdf)


---



# Business Challenges

Before implementation, business teams faced several operational and reporting issues:

Data was spread across multiple systems and files
Reporting required manual consolidation and reconciliation
Data quality issues impacted trust in reports
Limited visibility into sales and customer performance
Reporting cycles were slow and resource-intensive

These challenges created delays in decision-making and restricted business visibility.


---




# Pipeline Architecture 

<img width="8107" height="3420" alt="Image" src="https://github.com/user-attachments/assets/7471c7fd-1432-4dd6-949b-4c95ce535d37" />

Azure-based Medallion Architecture (Bronze → Silver → Gold) built using ADLS Gen2, Unity Catalog, and Azure Databricks. Raw e-commerce data is centralized in Azure Data Lake, transformed through ETL/ELT pipelines, and published as analytics-ready datasets for Power BI reporting.

The solution follows a modern cloud-native architecture built on Microsoft Azure.

Data Flow

ShopVista Source Systems
⬇
Azure Data Lake Storage Gen2 (Raw Data Storage)
⬇
Azure Databricks + Unity Catalog
⬇
Bronze Layer (Raw Data)
⬇
Silver Layer (Cleaned & Standardized Data)
⬇
Gold Layer (Business Ready Data Models)
⬇
Power BI Reporting Layer

This architecture provides scalability, governance, automation, and high-performance analytics.

---

.
# Project Outcomes

Business Impact --

✔ Eliminated manual data consolidation

✔ Reduced reporting turnaround time

✔ Established a centralized source of truth

✔ Improved reporting accuracy

✔ Enabled faster business decision-making

✔ Built a scalable cloud data platform for future growth

The ShopVista Retail Intelligence Platform demonstrates how modern cloud technologies can transform fragmented operational data into a reliable and scalable analytics ecosystem




---


## Tech Stack

- Azure Data Lake Storage Gen2
- Azure Databricks
- Unity Catalog
- PySpark
- Delta Tables
- Databricks Workflows
- SQL Warehouse
- Power BI Desktop

 
 ---


# Azure Resource 


<img width="1641" height="670" alt="Image" src="https://github.com/user-attachments/assets/82e0b19e-f62c-49a5-bbe0-7fce665bf485" />


All cloud resources required for the project were provisioned and managed within a centralized Azure Resource Group.

The resource group acts as the operational boundary for managing infrastructure components including:

Azure Databricks Workspace
Azure Data Lake Storage Account
Access Connectors
Monitoring Components
Supporting Azure Services



---



# Azure Data Lake (Raw Layer)



<img width="637" height="659" alt="Image" src="https://github.com/user-attachments/assets/55ca40cf-0640-41b4-a80d-d15c4bbe424e" />

Azure Data Lake Storage Gen2 serves as the centralized repository for all incoming source data.

Raw datasets are stored without modification to preserve historical records and maintain data lineage.

Datasets Ingested
Customers
Products
Categories
Brands
Orders
Order Items
Shipments
Returns
Date Dimension

This layer acts as the foundation of the Medallion Architecture




---


# Storage Account 

<img width="1623" height="599" alt="Image" src="https://github.com/user-attachments/assets/9e540a8b-af33-40d0-b881-1ff58ab66fb7" />



The Azure Storage Account provides secure and scalable storage for all project datasets.

Features implemented include:

Hierarchical Namespace
Secure Data Access
Centralized File Management
Data Lake Integration
High Availability Storage

The storage account serves as the persistent storage layer powering the analytics platform.


--- 

# SQL Warehouse 
<img width="1918" height="850" alt="Image" src="https://github.com/user-attachments/assets/67089996-52ff-4ffe-b22f-b842699cb47c" />


A Databricks SQL Warehouse was configured to provide high-performance querying capabilities for analytical workloads.

The warehouse enables:

Interactive SQL Analysis
Data Exploration
Business Queries
Power BI Connectivity
Reporting Layer Optimization

This provides a bridge between engineering workloads and business intelligence consumption.

---


# Medallion Architecture - Data Layers [Bronze & Silver]
<img width="6000" height="3375" alt="Image" src="https://github.com/user-attachments/assets/0ae52826-7ef8-4a78-afb0-991bee31ec81" />


The Bronze and Silver layers form the core data engineering foundation.

Bronze Layer --

The Bronze layer stores raw ingested datasets directly from source systems.

Objectives:

Preserve source data
Maintain ingestion history
Enable auditability
Support replay and recovery
Bronze Tables
brz_customers
brz_products
brz_category
brz_brands
brz_order_items
brz_calendar


Silver Layer --

The Silver layer focuses on data quality and standardization.

Transformations include:

Schema enforcement
Data cleansing
Null handling
Duplicate removal
Standardization
Referential integrity validation
Silver Tables
slv_customers
slv_products
slv_category
slv_brands
slv_order_items
slv_calendar

This layer ensures business-ready consistency across datasets.


---

# Medallion Architecture - Gold Data Layer

<img width="6000" height="3375" alt="Image" src="https://github.com/user-attachments/assets/48fe2fcb-97b3-4eb8-9bea-929a5326df6e" />

The Gold layer contains curated datasets optimized for analytics and reporting.

Business entities are integrated and modeled into analytical structures suitable for consumption by Power BI and business users.

Gold Tables

Dimension Tables

gld_dim_customers
gld_dim_products
gld_dim_date

Fact Tables

gld_fact_order_items
gld_fact_daily_orders_summary

The Gold layer serves as the single source of truth for business reporting and analytics

---

# Job Orchestration & Automation
# Daily Refresh Pipeline

<img width="6000" height="3375" alt="Image" src="https://github.com/user-attachments/assets/3395b324-552c-4533-9639-9e0adb2e1d83" />

Databricks Workflows were implemented to automate end-to-end pipeline execution.

Automated Workflows

Dimension Pipeline

Bronze → Silver → Gold

Fact Pipeline

Bronze → Silver → Gold → Daily Summary

Benefits

✔ Automated daily refresh

✔ Reduced manual intervention

✔ Improved reliability

✔ Consistent reporting datasets

This orchestration framework enables repeatable and production-ready data operation.

---

# Analytics & Report

<img width="4150" height="2400" alt="Image" src="https://github.com/user-attachments/assets/f4ac2c1b-a7d1-4970-8b13-7ccd03231aa4" />

The final reporting layer was developed using Power BI and connected directly to the Gold Layer datasets.

Business KPIs
Total Sales
Units Sold
Total Customers
Repeat Customer Rate
Average Discount
High-Profit Region
Analytical Insights
Customer Distribution by Region
Revenue Trends by Month
Sales Performance by Channel
Brand Performance Analysis
Category Performance Analysis

The dashboard enables stakeholders to monitor business performance and make data-driven decisions through a centralized reporting experience.

---

