# Part 3: Data Transformation

Data transformation is the process of converting data from one format or structure to another, while preserving its original meaning. It involves manipulating and reshaping data to make it more suitable for analysis or for use in a particular system or application.




Data transformation is important for several reasons. Firstly, it can help to clean and standardize data, which is often collected from various sources in different formats. By transforming data into a consistent format, it becomes easier to compare and analyze. Secondly, data transformation can help to create new variables or features from existing data, which can be used to improve the accuracy of predictive models. Finally, data transformation can help to improve data privacy and security, by removing sensitive information or encrypting data during the transformation process.

We will use the Medallion architecture to transform the data in Databricks Lakehouse, where data are organised in three different layers:


- Bronze layer - raw data as they come from the source
- Silver layer - cleaned and consolidated data
- Gold Layer - enriched and aggregated data for analysis


![image](./Medallion-Architecture.png)



Medallion architecture reference:
- https://learn.microsoft.com/en-us/azure/databricks/lakehouse/medallion
- https://www.databricks.com/glossary/medallion-architecture


Resource for SDP:

- https://learn.microsoft.com/en-us/azure/databricks/ldp/transform

## Outline
- [Bronze Layer](#bronze-layer)
- [Silver Layer](#silver-layer)
- [Gold Layer](#gold-layer)
- [Deliverables](#deliverables)
- [Advanced Challenge (Optional)](#advanced-challenge-optional)


## Bronze Layer

The first layer on the Medallion architecture is Bronze layer, where we land all the data from external source systems. The table structures in this layer correspond to the source system table structures "as-is," along with any additional metadata columns that capture the load date/time, process ID, etc.

Lakeflow Spark Declarative Pipelines (SDP) makes it easy to build and manage reliable batch and streaming data pipelines that deliver high-quality data on the Databricks Lakehouse Platform. SDP helps data engineering teams simplify [ETL](https://www.databricks.com/discover/etl) development and management with declarative pipeline development, automatic data testing, and deep visibility for monitoring and recovery.


## Silver Layer
Upon ingestion into the silver layer, data is filtered, cleaned and augmented. This could mean the data is deduplicated, missing data is handled, incorrect data is removed or corrupted data is fixed.

## Gold Layer
Going into the gold layer the data is transformed for specific use cases and Business level aggregation is applied. At this level business rules are applied and data from different source files or systems may also be joined together.




## Deliverables:
Create a Databricks notebook that implements the Medallion architecture:
1. Ingest raw data into Bronze layer using Auto Loader.
1. Transform and clean data into Silver layer.
1. Create aggregated Gold layer tables.
1. Document your transformation logic and data quality checks.


## Advanced Challenge (Optional)

1. Implement a mechanism to handle changes in reference data (e.g., Airports, Airlines). Since this data can change over time, you need to decide on a strategy (SCD Type 1 for overwriting or SCD Type 2 for tracking history) and implement it. Your ingestion process should be able to identify new, updated, or deleted records and apply the changes to your target tables effectively - [Source](https://medium.com/@naveen140882/understanding-scd-type-1-vs-scd-type-2-with-an-example-e188373d5304)

1. Add data quality expectations and constraints to your pipeline (e.g., null checks, range validations, referential integrity) - [Source](https://docs.databricks.com/en/delta-live-tables/expectations.html) 

1. Implement data lineage tracking to trace data flow from source to gold layer (e.g. custom metadata columns) - [Source](https://learn.microsoft.com/en-us/azure/databricks/data-governance/unity-catalog/data-lineage)

1. Add schema evolution handling to manage changes in source data structure.

1. Create data quality metrics dashboard or reports showing validation results.

1. Implement error handling and quarantine tables for records that fail validation.


**Deliverables**

- Implement appropriate merge logic for target tables (e.g., SCD Type 1/2 for dimension tables, append/upsert for fact tables).
- Document data quality rules and validation logic.
- Implement quality checks in each layer of the medallion architecture.
- Create a report or visualization showing data quality metrics.
