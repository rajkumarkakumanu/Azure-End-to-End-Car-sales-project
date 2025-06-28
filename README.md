# Azure-End-to-End-Car-sales-project
![architecture](https://github.com/user-attachments/assets/c07d1bbf-1b00-49d1-ae0d-59ac9a62a66b)
# 🚗 Car Sales Data Engineering Pipeline

This project is a modern data engineering solution for processing and analyzing **car sales data**, leveraging **Azure Data Services** and **Apache Spark**. It demonstrates both **direct** and **incremental data ingestion**, followed by transformations to build a **star schema** data model for business analytics.

---

## 🔧 Technologies Used

- **Azure Data Lake Storage Gen2 (ADLS Gen2)** – Raw and curated data storage
- **Azure Data Factory (ADF)** – Orchestration of data movement and pipeline scheduling
- **Azure SQL Database** – Final data warehouse for reporting and BI tools
- **Azure Databricks** – Processing and transformation layer using PySpark
- **PySpark** – For scalable data transformations and model creation

---

## 📊 Project Architecture

### 1. **Data Ingestion**
- Raw car sales data is fetched from the source and stored in **ADLS Gen2**.
- Two data ingestion strategies are used:
  - **Direct Load**: Initial full load of historical car sales data
  - **Incremental Load**: Fetches only new or updated records based on a  **watermark table**

### 2. **Transformation (Curated Layer)**
- Data is cleaned, validated, and transformed using **Databricks notebooks** with **PySpark**
- Business logic is applied to prepare the data for analytical modeling

### 3. **Data Modeling (Star Schema)**
- Transformed data is organized into:
  - 🧮 **Fact_Sales**
  - 🚘 **Dim_Model**
  - 🏬 **Dim_Branch**
  - 📆 **Dim_Date**
  - 🧑‍💼 **Dim_Dealer**

### 4. **Incremental Data Handling**
- After the initial pipeline run, the system supports **incremental updates**:
  - Uses a watermark table to detect and load only new or changed records
  - Supports **upserts** to the dimension and fact tables
  - Maintains data freshness without reprocessing the full dataset

### 5. **Data Loading**
- Transformed and modeled data is written to **Azure SQL Database**
- Loaded data is ready for analysis and visualization through BI tools

---

## 📁 Directory Structure



