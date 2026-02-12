# End-to-End-Azure-Data-Pipeline

The primary focus of this project is **data ingestion, transformation, orchestration, and architecture design**, following modern data engineering best practices.

## Architecture

**Source → Ingestion → Storage → Transformation → Analytics**

**- Source:** On-premises SQL Server (AdventureWorks)

**- Ingestion:** Azure Data Factory with Self-Hosted Integration Runtime

**- Storage:** Azure Data Lake Storage Gen2 (Bronze, Silver, Gold layers)

**- Transformation:** Azure Databricks (Apache Spark)

**- Analytics Layer:** Azure Synapse Analytics (SQL views on curated data)

**- Security:** Azure Key Vault

**- Orchestration:** Azure Data Factory pipelines and triggers

## Data Flow

**1. Ingestion (Bronze Layer)**
- Extracted data from on-premises SQL Server using Azure Data Factory and Self-Hosted Integration Runtime.
- Stored raw datasets in the **Bronze** layer of Azure Data Lake Storage Gen2.

**2. Transformation (Silver Layer)**
- Used Databricks notebooks to clean, standardize, and validate raw data.
- Stored refined datasets in the **Silver** layer.

**3. Curation (Gold Layer)**
- Applied business transformations and aggregations in Databricks.
- Stored analytics-ready datasets in the **Gold** layer.

**4. Analytics & Consumption**
- Created SQL views in Azure Synapse over the Gold layer to support BI and analytical workloads.

**5. Orchestration & Automation**
- Orchestrated all ingestion and transformation steps using Azure Data Factory pipelines.
- Implemented triggers and scheduling for reliable, repeatable execution.

## Security & Governance
- Managed secrets and credentials using **Azure Key Vault**.
- Applied secure access patterns between Azure services.
- Designed the platform with separation of concerns and data governance in mind.

## Technology Stack
- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure Databricks (Apache Spark / PySpark)
- Azure Synapse Analytics
- Azure Key Vault
- SQL Server (On-Premises)
