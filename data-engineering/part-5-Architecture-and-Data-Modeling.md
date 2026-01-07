# Part 5: Architecture and Data Modelling

1. Create an architecture for the requirement. Include below details in the architecture
    - Method of integration of each source system.
    - Details about batch/streaming.
    - Scheduling and orchestration tools for different data.
    - Storage file format in each layer.
    - Method of integartion with Power BI.

1. Create data models for the bronze (if applicable), silver and gold layer. Include belwo details in the data model.
    - Primary and Foreign Key information.
    - Relationship between tables and their type (one-to-one, one-to-many etc).
    - All attributes.
    - Document the reasoning behind choosing a particular type of modelling technique for each layer.


## Outline
- [Architecture](#architecture)
- [Data Ingestion](#data-ingestion)
- [Datamodel for Bronze Layer](#datamodel-for-bronze-layer)
- [Datamodel for Silver Layer](#datamodel-for-silver-layer)
- [Datamodel for Gold Layer](#datamodel-for-gold-layer)


## Architecture
Create an architecture for the requirement descriped in EPIC. Include below details in the architecture:

1. Method of integration of each source system
Details about batch/streaming.
1. Scheduling and orchestration tools for different data.
1. Tools for data processing.
1. Storage file format in each layer.
1. Method of integration with Power BI.


**Deliverables**

A markdown file which contains the architecture diagram and the reasoning behind the architrectural decisions (like selection of particular tools/technologies).

## Data Ingestion
Dynamic information about the flights Status for Arrivals and Departures.
If you want to know which flights has been departed or arrived on a particular day can be found under 'operations'.

To get this information the following operational data from the Lufthansa Open API should be extracted:

1. all flights departing and arriving at FRA and MUC airports. 
    - [flight status departure](https://developer.lufthansa.com/docs/read/api_details/operations/Departures_Status)
    - [flight status arrival](https://developer.lufthansa.com/docs/read/api_details/operations/Flight_Status_by_Airport).


**Deliverables**

A pipeline to ingest the data from the LH OpenAPI to the Azure Data Lake storage.

## Datamodel for Bronze Layer
1. Decide the data modelling technique to be used for the bronze layer. Consider the pros and cons of each technique, and requirements to arrive at your decision. There is no ONE right answer here, so please compliment your decision with the reasoning. Feel free to make assumptions and document them, when certain things are not clear in the requirement. A good starting point for this process could be [this Databricks blog](https://www.databricks.com/blog/2022/06/24/data-warehousing-modeling-techniques-and-their-implementation-on-the-databricks-lakehouse-platform.html).

1. Create data model for the bronze layer. Include all attributes in the data model.


**Deliverables**

1. Data are loaded incrementally each time a new file is loaded in the data lake.
1. Columns have been renamed appropriately.
1. Data types have been assigned appropriately.


## Datamodel for Silver Layer
1. Decide the data modelling technique to be used for the silver layer. Consider the pros and cons of each technique, and requirements to arrive at your decision. There is no ONE right answer here, so please compliment your decision with the reasoning. Feel free to make assumptions and document them, when certain things are not clear in the requirement. A good starting point for this process could be this Databricks blog.

1. Create data model for the silver layer. Include below details in the data model.
    - Primary and Foreign Key information.
    - Relationship between tables and their type (one-to-one, one-to-many etc).
    - All attributes.
1. Define partitioning and indexing on the tables. Refer the indexing techniques on delta lake like [Z-ordering](https://docs.databricks.com/aws/en/delta/data-skipping), [bloom filter](https://docs.databricks.com/aws/en/optimizations/bloom-filters) and [liquid clustering](https://docs.databricks.com/aws/en/delta/clustering).


**Deliverables**


1. A markdown file which contains the assumptions and reasoning behind using a particular modelling technique and other important aspects of the model.
1. Embed the datamodel diagram in the mardown file, preferably using Mermaid.
1. Mention the partitioning and indexing (if any) that is to be applied on each table.
1. A suitable naming convention for the tables, with which the type of table (like dimension, fact, hub etc) can be easily identified.
1. Produce DDL scripts for creation of the tables as per the model.

## Datamodel for Gold Layer
1. Decide the data modelling technique to be used for the gold layer. Consider the pros and cons of each technique, and requirements to arrive at your decision. There is no ONE right answer here, so please compliment your decision with the reasoning. Feel free to make assumptions and document them, when certain things are not clear in the requirement. A good starting point for this process could be [this Databricks blog](https://www.databricks.com/blog/2022/06/24/data-warehousing-modeling-techniques-and-their-implementation-on-the-databricks-lakehouse-platform.html).
1. Create data model for the silver layer. Include below details in the data model.
    1. Primary and Foreign Key information.
    1. Relationship between tables and their type (one-to-one, one-to-many etc)
    1. All attributes
1. Define partitioning and indexing on the tables. Refer the indexing techniques on delta lake like [Z-ordering](https://docs.databricks.com/en/delta/data-skipping.html), [bloom filter](https://docs.databricks.com/en/optimizations/bloom-filters.html) and [liquid clustering](https://docs.databricks.com/en/delta/clustering.html)

**Deliverables**

1. A markdown file which contains the assumptions and reasoning behind using a particular modelling technique and other important aspects of the model.
1. Embed the datamodel diagram in the mardown file, preferably using Mermaid.
1. Mention the partitioning and indexing (if any) that is to be applied on each table.
1. A suitable naming convention for the tables, with which the type of table (like dimension, fact, hub etc) can be easily identified.
1. Produce DDL scripts for creation of the tables as per the model.