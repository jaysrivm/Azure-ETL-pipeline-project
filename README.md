# Azure-ETL-pipeline-project

Introduction
This project details the creation of a complete, scalable, and robust Extract, Transform, Load (ETL) pipeline utilizing core Microsoft Azure services. The goal is to ingest raw data, refine it through multiple processing stages, and deliver a clean, business-ready dataset for advanced reporting and business intelligence.

Technologies Used
Category	              Technology	                                 Purpose

Cloud Platform	        Azure Cloud Services	                       Infrastructure hosting and service orchestration.
Orchestration	          Azure Data Factory (ADF)	                   Pipeline management, scheduling, and data ingestion (Extraction).
Processing	            Azure Databricks	                           High-performance data cleaning, transformation, and enrichment (using PySpark/SQL).
Storage	                Azure Data Lake Storage Gen2 (ADLS Gen2)	   Central, scalable storage organized using the Medallion Architecture.
Reporting	              Power BI	                                   Final data visualization, dashboard creation, and business intelligence delivery.
Data Format	            Delta Lake / Parquet	                       Optimized, columnar storage format supporting ACID transactions.

Data Architecture: Medallion Layers in ADLS Gen2
The project employs the Medallion Architecture for data quality and management:

Bronze Layer (Raw Data):
Content: Unmodified, raw data ingested directly from the source.
Purpose: Provides an immutable history of the source data.

Silver Layer (Cleaned & Enriched):
Content: Data after initial cleaning, handling of null values, duplicate removal, and basic standardization.
Purpose: Suitable for basic exploratory analysis and intermediate data consumption.

Gold Layer (Business-Ready):
Content: Highly curated, aggregated, and transformed data (e.g., feature engineering, derived metrics).
Purpose: Optimized for fast querying by business intelligence tools (Power BI).

ETL Pipeline Summary
Step	             Tool Used	                 Action	                                                            Result

E (Extract)	       ADF (Copy Activity)	       Fetches the raw Amazon Prime dataset (CSV) from GitHub.	          Data loaded into the Bronze Layer of ADLS.
T (Transform 1)	   Azure Databricks	           Executes data cleaning, validation, and schema enforcement.	      Clean data stored in the Silver Layer (e.g., Parquet format).
T (Transform 2)	   Azure Databricks	           Executes advanced transformations (e.g., splitting genres, 
                                               creating year columns, aggregations).	                            Business-ready data stored in the Gold Layer (Delta Lake format).
L (Load)	         Power BI	                   Connects directly to the Databricks SQL endpoint 
                                               for the Gold Layer table.	                                        Interactive Dashboards and Reports generated for business consumption.

![WhatsApp Image 2025-09-27 at 08 26 32_96c9da83](https://github.com/user-attachments/assets/ab9eadcf-1131-46f6-92f5-2fc80351798a)

