
# Spotify Azure Data Engineering Project

## 🎯 Overview  
This project demonstrates an end-to-end **Azure Data Engineering pipeline** for ingesting, transforming, and managing Spotify analytics data using Microsoft Azure services.  
It serves as a personal learning project, showcasing modern data platform capabilities including batch and streaming ingestion, metadata-driven pipelines, and a data lakehouse architecture.

## 🧱 Architecture  
The overall architecture is built on the following foundation:

- Raw data ingestion (initial load) from the Spotify source.  
- Storage in **Azure Data Lake Gen2** for raw, staging, and curated zones.  
- Orchestration and ETL using **Azure Data Factory** for batch and incremental pipelines.  
- Transformation and advanced analytics processing using **Azure Databricks** with PySpark.  
- Data modeling using a star schema with slowly changing dimensions where applicable.  
- Streaming ingestion using Databricks Autoloader (if implemented) for near-real-time updates.  
- CI/CD deployment and infrastructure automation via Databricks Asset Bundles & Azure DevOps.  

## 🧰 Components & Features  
### Ingestion & Orchestration  
- Designed incremental ingestion pipelines with **Azure Data Factory**, including backfilling and looping mechanisms.  
- Utilized parameterized / metadata-driven pipelines so that new sources or partitions can be onboarded easily.  
- Incorporated automation with **Azure Logic Apps** to trigger pipelines and notify on failures or completions.

### Storage & Lakehouse  
- Landed raw and processed data into **Azure Data Lake Gen2**, partitioned by date/time for scalability.  
- Employed **Delta Lake** formats in Databricks, enabling data versioning, schema evolution, and time-travel.  
- Built transformation logic in **PySpark** with Jinja2 templating (for dynamic pipeline definitions and reusable components).

### Modeling & Streaming  
- Implemented a star schema design and handled slowly changing dimensions (SCD Type 2) for historic tracking.  
- Created streaming ingestion workflows using Databricks Autoloader to process new Spotify data in near-real time.  
- Utilized **Delta Live Tables** (or similar Databricks orchestration) to simplify data pipeline management and ensure reliability.

### DevOps & CI/CD  
- Set up Databricks Asset Bundles for versioned deployment of notebooks, libraries, and pipeline definitions.  
- Automated deployment via Azure DevOps pipelines to ensure repeatable environments and better code governance.

## 🛠 Tech Stack  
- Azure Data Factory  
- Azure SQL Database (as source/metadata)  
- Azure Data Lake Gen2  
- Azure Databricks (PySpark, Delta Lake, Delta Live Tables)  
- Jinja2 templating  
- Azure Logic Apps  
- Azure DevOps (CI/CD)
