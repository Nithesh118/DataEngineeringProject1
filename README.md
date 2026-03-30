🚀 Azure Data Engineering End-to-End Pipeline
📌 Overview

This project demonstrates an end-to-end data engineering pipeline built using Azure services. It covers data ingestion, transformation, storage, and visualization using a Medallion Architecture (Bronze, Silver, Gold) approach.

<img width="1536" height="1024" alt="ChatGPT Image Mar 30, 2026, 10_50_49 PM" src="https://github.com/user-attachments/assets/0fd0cef6-74d3-4cd0-b326-d006b2f19b72" />
<img width="1908" height="866" alt="Screenshot 2026-03-30 223024" src="https://github.com/user-attachments/assets/8f57c5a9-27f8-43b8-867e-5e58ca5dc42b" />
<img width="1917" height="863" alt="Screenshot 2026-03-30 223125" src="https://github.com/user-attachments/assets/338de82f-08d5-4631-a418-79e73541cf5e" />
<img width="1918" height="876" alt="Screenshot 2026-03-30 223158" src="https://github.com/user-attachments/assets/d8aaa916-85a8-44b9-9837-0775c978d397" />

🏗️ Architecture
Source: Data fetched dynamically from GitHub using JSON configuration
Ingestion: Azure Data Factory (ADF)
Storage: Azure Data Lake Storage Gen2 (ADLS)
Processing: Azure Databricks (PySpark)
Serving Layer: Azure Synapse Analytics (Serverless SQL)
Visualization: Power BI
🔄 Data Pipeline Flow
Dynamic Ingestion
JSON-driven configuration to control file ingestion
ADF pipeline uses:
Lookup activity
ForEach loop
Copy activity
Data is ingested from GitHub into Bronze layer (ADLS)
Data Transformation (Silver Layer)
Azure Databricks used for:
Data cleaning
Data transformation
Schema handling
Output stored in Silver container
Data Serving (Gold Layer)
Azure Synapse Serverless SQL used with OPENROWSET
Views created for structured querying
Fact and Dimension tables designed for analytics
Visualization
Power BI connected to Synapse
Dashboards created for insights
⚙️ Key Features
✅ Metadata-driven pipeline using JSON configuration
✅ Parameterized ADF pipelines (dynamic & reusable)
✅ Medallion Architecture (Bronze → Silver → Gold)
✅ PySpark-based transformations in Databricks
✅ Serverless querying using Synapse (OPENROWSET)
✅ End-to-end integration with Power BI
🛠️ Tech Stack
Azure Data Factory
Azure Databricks (PySpark)
Azure Data Lake Gen2
Azure Synapse Analytics
Power BI
Python / SQL
📂 Project Structure
├── adf/
│   ├── pipeline.json
│   ├── linkedServices.json
│
├── databricks/
│   ├── transformation_notebook.py
│
├── synapse/
│   ├── openrowset_queries.sql
│   ├── views.sql
│
├── dataset/
│   ├── sample_input_files/
│   ├── json_config/
│
└── README.md
🚀 How to Run
Create Azure resources:
ADLS Gen2
Azure Data Factory
Azure Databricks
Azure Synapse Analytics
Upload JSON config and source data to storage
Configure ADF pipeline:
Set parameters
Connect GitHub source
Trigger pipeline:
Data lands in Bronze
Run Databricks notebook:
Process data → Silver
Query using Synapse:
Create views → Gold layer
Connect Power BI:
Build dashboard
📊 Sample Use Case

This pipeline can be used for:

Sales data processing
Log data ingestion
Analytics reporting pipelines
📈 Future Improvements
Implement incremental loading (High Watermark)
Add Delta Lake optimizations
Automate Databricks execution via ADF trigger
CI/CD integration
👤 Author

Nithesh R

LinkedIn: https://linkedin.com/in/nitheshr118
GitHub: https://github.com/Nithesh118
