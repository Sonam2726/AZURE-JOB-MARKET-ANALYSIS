## Project Overview

This project demonstrates an end-to-end Azure Data Engineering pipeline built using Azure cloud services. The pipeline ingests a Job Market dataset, processes it through Bronze, Silver, and Gold layers using Azure Databricks, and creates an interactive Power BI dashboard for business insights.


## Project Architecture

Job Market CSV Dataset
          │
          ▼
Azure Data Lake Storage Gen2 (Raw Data)
          │
          ▼
Azure Data Factory (Pipeline)
          │
          ▼
Azure Databricks (PySpark)
          │
 ┌────────┼────────┐
 ▼        ▼        ▼
Bronze  Silver   Gold
(Raw)   (Clean) (Business Analytics)
          │
          ▼
Parquet Files
          │
          ▼
Power BI Dashboard


## Technologies Used

- Microsoft Azure
- Azure Data Lake Storage Gen2
- Azure Data Factory
- Azure Databricks
- PySpark
- Delta Lake
- Parquet
- Power BI Desktop
- GitHub



## Dataset

The project uses a Job Market dataset containing information such as:

- Job ID
- Company Name
- Job Title
- Salary
- Location
- Experience Level
- Work Type
- Posting Date
- Currency
- Application Details



## ETL Process

### Bronze Layer
- Reads CSV data from ADLS Gen2
- Splits the dataset into six Delta tables:
  - Jobs
  - Company
  - Salary
  - Location
  - Experience
  - Posting
- Stores raw data in Delta format



### Silver Layer
- Reads Delta tables from Bronze
- Cleans the data
- Handles missing values
- Converts data types
- Removes duplicate records where required
- Saves cleaned data as Delta tables



### Gold Layer
Creates business-ready analytical datasets including:

- Company Analysis
- Salary Analysis
- Location Analysis
- Experience Analysis
- Monthly Analysis
- Posting Domain Analysis

Additional optimizations:
- Delta OPTIMIZE
- VACUUM
- Export to Parquet for Power BI



## Azure Data Factory Pipeline

The pipeline orchestrates the complete ETL process.

Execution Flow:

Bronze Notebook
↓

Silver Notebook
↓

Gold Notebook

Pipeline Trigger:
- Manual Trigger



## Power BI Dashboard

The dashboard provides insights such as:

- Total Companies
- Total Job Postings
- Average Salary
- Jobs by Company
- Jobs by Location
- Experience Level Distribution
- Monthly Job Posting Trend
- Posting Domain Analysis

Interactive slicers include:

- Company Name
- Location
- Experience Level
- Work Type
- Remote Allowed



## Folder Structure


Azure-Job-Market-Analytics
│
├── Bronze_Notebook
├── Silver_Notebook
├── Gold_Notebook
├── ADF_Pipeline
├── PowerBI
├── Screenshots
├── Dataset
└── README.md


## Key Features

- End-to-End Azure Data Pipeline
- Layered Architecture (Bronze, Silver, Gold)
- Delta Lake Storage
- Data Cleaning using PySpark
- Business Analytics
- Power BI Dashboard
- Manual Pipeline Execution
- Optimized Storage using Delta Lake
- Parquet Export for Reporting



## Future Enhancements

- Incremental Data Loading
- Automated Pipeline Scheduling
- CI/CD Integration
- Azure Monitor Integration
- Real-Time Data Streaming



## Author

**Sonam Bhurani**

Azure Data Engineering Project
