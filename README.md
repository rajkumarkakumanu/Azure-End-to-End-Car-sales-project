# Azure-End-to-End-Car-sales-project
![architecture](https://github.com/user-attachments/assets/c07d1bbf-1b00-49d1-ae0d-59ac9a62a66b)
# 🚗 Car Sales Data Engineering Pipeline (Medallion Architecture)

This project is a modern data engineering solution for processing and analyzing **car sales data**, built using **Azure services** and **Apache Spark** in **Databricks**. It follows the **Medallion Architecture** pattern—**Bronze, Silver, and Gold layers**—to ensure scalable, modular, and high-quality data pipelines.

The pipeline supports both **direct (full)** and **incremental** data ingestion using a **watermark table** to track changes efficiently.

---

## 🔧 Technologies Used

- **Azure Data Lake Storage Gen2 (ADLS Gen2)** – Storage for raw, curated, and analytics data
- **Azure Data Factory (ADF)** – Orchestration of data movement and scheduling
- **Azure SQL Database** – Final data warehouse for serving BI/reporting
- **Azure Databricks** – Transformation and data modeling using PySpark
- **PySpark** – Distributed data processing
- **Medallion Architecture** – Layered data pipeline design (Bronze → Silver → Gold)

---

## 🧱 Architecture Overview

### ✅ Medallion Architecture Layers

- **🟫 Bronze Layer** (Raw):
  - Ingest raw car sales data from source
  - Store unprocessed records for auditing and traceability

- **⬜ Silver Layer** (Cleaned/Transformed):
  - Clean and validate data using PySpark
  - Join reference data
  - Handle schema evolution and null checks

- **🟨 Gold Layer** (Analytics/Model):
  - Create star schema models for reporting
  - Build and maintain:
    - 🧮 `Fact_Sales`
    - 🚘 `Dim_Model`
    - 🧑‍💼 `Dim_Dealer`
    - 📆 `Dim_Date`
    - 🏬 `Dim_Branch`

---

## 🔁 Incremental Load with Watermark Table

- A **watermark table** is maintained in **Azure SQL Database** to track the latest processed timestamp for each data source.
- During each run, only records **newer than the last watermark** are processed (CDC-style).
- After successful processing, the watermark is updated to ensure accurate future loads.
- Supports **idempotent transformations** and **upserts** to target tables.

---

## 📁 Directory Structure




