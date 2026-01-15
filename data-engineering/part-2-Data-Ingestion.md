# Part 2: Data Ingestion

Data ingestion is the process of importing, transforming, and loading data from various sources into a storage system, such as a data warehouse, a data lake, or a database. This process involves collecting data from disparate sources, cleaning and validating it, and converting it into a format that can be easily analyzed and processed.

Data ingestion is a critical step in the data pipeline because it sets the foundation for the subsequent data processing and analysis. The ingestion process can be done in real-time or batch mode depending on the nature of the data, the processing requirements, and the business needs.

The data sources for ingestion can include structured data, such as data from a relational database, as well as semi-structured and unstructured data such as text files, logs, social media feeds, and IoT sensors. Data ingestion also involves the application of data governance policies to ensure the accuracy, completeness, and security of the data being ingested.


In this task you need to build a data ingestion process to retrieve raw data from LH OpenAPI and store it in Unity Catalog volumes (/Volumes/`<catalog>`/`<schema>`/`<volume>`/).

## Outline
- [Ingest Operational Data](#ingest-operational-data)
    - [Ingest LH OpenAPI Flight Status by Route](#ingest-lh-openapi-flight-status-by-route)
- [Ingest Reference Data](#ingest-reference-data)
    - [Airports](#airports)
    - [Cities](#cities)
    - [Countries](#countries)
    - [Airlines](#airlines)
    - [Aircrafts](#aircrafts)
- [Deliverables](#deliverables)
- [Advanced Challenge (Optional)](#advanced-challenge-optional)



## Ingest Operational Data
Dynamic information about the state of our flights. If you want to know which flights operate on a particular day or whether a particular flight is on-time, you'll find it under 'operations'.


### Ingest LH OpenAPI Flight Status by Route
To get this information the following operational data from the Lufthansa Open API should be extracted:
Flight Status by Route.

In this part, you need to build a pipeline to ingest the operational data from the LH OpenAPI to the Unity Catalog volumes.

**Schedule**: Daily



## Ingest Reference Data
Reference data provides access to retrieve list or specific record of Aircrafts, Airlines, Airports, Cities and Countries. In this part, you need to build a pipeline to ingest the reference data from the LH OpenAPI to the Unity Catalog volumes.


### Airports:
The purpose of this task is to import reference data about airports from the open Lufthansa API into our system. This data will provide comprehensive information about airports worldwide, including location, airport name, IATA code, and other relevant details.

**Schedule**: Monthly


### Cities:
The purpose of this task is to import reference data about cities from the open Lufthansa API into our system.

**Schedule**: Monthly

### Countries:
The purpose of this task is to import reference data about countries from the open Lufthansa API into our system. This data will provide comprehensive information about country code, language code and other relevant details. 

**Schedule**: Monthly

### Airlines
The purpose of this task is to import reference data about airlines from the open Lufthansa API into our system. This data will provide comprehensive information about airlines and other relevant details.

**Schedule**: Monthly


### Aircrafts
The purpose of this task is to import reference data about aircrafts from the open Lufthansa API into our system. This data will provide comprehensive information about AircraftResource, AircraftSummary, AircraftCode, Name and other relevant details.

**Schedule**: Monthly




## Deliverables:
- Extract operational and reference data from Lufthansa Open API endpoints for flight status 
- Configure pipelines with scheduled triggers for data extraction.
- Validate that the extracted data provides dynamic flight state information, including flight operations and on-time status.



## Advanced Challenge (Optional)

1. Familiarize yourself with [Databricks Asset Bundles](https://docs.databricks.com/en/dev-tools/bundles/index.html) for streamlined deployment and configuration management.

1. Set up the codebase on your system and decide on a strategy to organize code in a modular fashion, ensuring components are logically separated and maintainable.

1. Create a Git repository for your codebase and decide on a branch strategy (GitLab is recommended to be used in this track).

1. Use Databricks Asset Bundles to manage and deploy your code on dev environment in a consistent and reproducible manner.

**Deliverables**
- Git repository created with proper structure and branching strategy
- Initial codebase committed with appropriate .gitignore file
- README documentation with setup and contribution guidelines
- Successfully configure and deploy Databricks resources (notebooks, jobs, pipelines) using Asset Bundles.