# Azure-data_engineer-Motor-insurance
Motor Insurance Analytics 

This project demonstrates a real-world Azure Data Engineering pipeline built using GitHub, Azure Data Factory, Azure Data Lake, Azure Databricks, and Power BI.

The pipeline ingests motor insurance CSV data from GitHub, processes it through a Bronze → Silver → Gold architecture, and delivers business-ready data for analytics.

## Business Problem
Motor insurance companies receive large volumes of policy and add-on coverage data. This data needs to be:

Ingested from external sources
Cleaned and standardized
Transformed into analytical format
Made available for reporting and decision-making
This project solves that using an Azure-based cloud data pipeline.


## Data Source
This dataset contains:

Policy ID
- Add-on type
- Add-on premium
- Engine protector
- Zero depreciation
- Roadside assistance
- Consumables cover
- Other insurance attributes


## Architecture (Medallion Model)

➡️Azure Data Factory
➡️Bronze Storage (Raw Data)
➡️Azure Databricks
➡️Silver Storage (Cleaned Data)
➡️Power BI
➡️Gold Storage (Analytics-ready Data)


# Azure Services Used

| Service | Purpose |
|---|---|
| Azure Data Factory | Data ingestion and pipeline orchestration |
| Azure Data Lake Gen2 | Storage for Bronze, Silver, Gold layers |
| Azure Databricks | Data cleaning, transformation and business logic |
| GitHub | Source system for CSV data |
| Power BI | Data visualization and reporting |

---

# Pipeline Flow

## 1. Data Ingestion (GitHub → Bronze)

- Azure Data Factory reads CSV from GitHub using HTTP Linked Service
- Raw data is stored in Bronze container

## 2. Data Processing (Bronze → Databricks)

- Databricks reads raw data
- Performs:
  - Null handling
  - Data type conversion
  - Column standardization
  - Business rule validation

## 3. Refined Data (Databricks → Silver)

- Cleaned and validated data written to Silver storage

## 4. Analytics (Silver → Power BI)

- Power BI connects to Silver layer
- Dashboards created for:
  - Premium analysis
  - Add-on usage
  - Policy trends

## 5. Business Layer (Silver → Gold)

- Aggregated and analytics-ready data stored in Gold storage

## key Transformations

- Converted Yes/No values into Boolean
- Removed duplicate policies
- Normalized add-on names
- Calculated premium metrics
- Created business-friendly columns

## Power BI Dashboards
Reports include:

- Total premium by add-on type
- Policy-wise coverage analysis
- Revenue contribution of add-ons
- Trend analysis

## Data Engineering Concepts Implemented
- ETL Pipeline Design
- Medallion Architecture (Bronze, Silver, Gold)
- Cloud Data Orchestration
- Data Lake Storage
- PySpark Transformations
- BI Integration
