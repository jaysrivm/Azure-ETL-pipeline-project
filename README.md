# Azure-ETL-pipeline-project

Introduction
This project details the creation of a complete, scalable, and robust Extract, Transform, Load (ETL) pipeline utilizing core Microsoft Azure services. The goal is to ingest raw data, refine it through multiple processing stages, and deliver a clean, business-ready dataset for advanced reporting and business intelligence.

| Category       | Technology                         | Purpose                                            |
| -------------- | ---------------------------------- | -------------------------------------------------- |
| Cloud Platform | **Azure Cloud Services**           | Infrastructure hosting and orchestration           |
| Orchestration  | **Azure Data Factory (ADF)**       | Data ingestion, pipeline scheduling, orchestration |
| Processing     | **Azure Databricks** (PySpark/SQL) | Data cleaning, transformation, enrichment          |
| Storage        | **Azure Data Lake Storage Gen2**   | Central storage, tiered via Medallion Architecture |
| Reporting      | **Power BI**                       | Data visualization and business intelligence       |
| Data Format    | **Delta Lake / Parquet**           | Optimized columnar format with ACID transactions   |


🗂️ Data Architecture: Medallion Layers

Bronze Layer (Raw Data)

Raw CSV data ingested directly from GitHub.

Immutable storage for source preservation.

Silver Layer (Cleaned Data)

Null handling, duplicates removed, schema standardized.

Ready for exploratory analysis.

Gold Layer (Business-Ready Data)

Aggregated, curated, and enriched data.

Optimized for BI tools (Delta Lake/Parquet format).

| Step              | Tool               | Action                                                                                 | Result                                   |
| ----------------- | ------------------ | -------------------------------------------------------------------------------------- | ---------------------------------------- |
| **Extract**       | Azure Data Factory | Copy raw dataset from GitHub                                                           | Data ingested into Bronze Layer          |
| **Transform (1)** | Azure Databricks   | Clean & validate data                                                                  | Stored in Silver Layer                   |
| **Transform (2)** | Azure Databricks   | Apply advanced transformations (splitting genres, creating year columns, aggregations) | Business-ready data stored in Gold Layer |
| **Load**          | Power BI           | Connects to Gold Layer via Databricks SQL endpoint                                     | Interactive Dashboards & Reports         |



📊 Project Outputs

Curated Gold Dataset

Fully processed, query-optimized dataset stored in ADLS (Gold Layer).

Power BI Dashboard

Key insights into Amazon Prime content, including:

📺 Movies vs. TV Shows distribution

🎭 Genre popularity trends

📅 Content release over time

🌍 Country-wise production distribution

⭐ Ratings analysis & KPIs

![WhatsApp Image 2025-09-27 at 08 26 32_96c9da83](https://github.com/user-attachments/assets/ab9eadcf-1131-46f6-92f5-2fc80351798a)

![WhatsApp Image 2025-09-27 at 08 32 53_3bfe1239](https://github.com/user-attachments/assets/02c83240-7536-4b3e-9fcb-d1f94003310d)

![WhatsApp Image 2025-09-27 at 08 31 39_9875dd6b](https://github.com/user-attachments/assets/d6bd5797-1d9d-435e-a5b3-9a802e4b8936)

