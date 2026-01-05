# Part 1: Fundamentals

This part covers the foundational concepts and skills essential for data engineering such as foundation for mastering the integration of Apache Spark with Azure.


## Outline

1. [Azure Databricks](#azure-databricks)
1. [Azure Data Factory (Optional)](#azure-data-factory-optional)
1. [Mermaid Code for Modelling Data and Visualizing](#mermaid-code-for-modelling-data-and-visualizing)
1. [Get familiar with Data - OpenSky](#get-familiar-with-data---opensky)
1. [Exercise](#exercise)

## Azure Databricks

Using the Databricks Workspace and research the following topics:

### Core Platform Fundamentals
- Databricks UI and workspace navigation
- Compute clusters (creation, configuration, autoscaling, and cluster policies)
- Notebooks fundamentals (cells, magic commands, visualizations)
- Git folders and version control integration
- Databricks volumes
- Unity Catalog basics (data governance and security)

### Data Processing & Storage
- Delta Lake fundamentals (ACID transactions, time travel, optimization)
- Delta Lake file format and architecture
- Data ingestion patterns (batch vs streaming)
- Lakeflow Spark Declarative Pipelines (SDP)


## Azure Data Factory (Optional)
> **Note**: Azure Data Factory is optional for this track. You can complete all exercises using Azure Databricks alone. However, learning ADF provides valuable experience with enterprise data orchestration tools and may be beneficial for production environments.

In this task you are going to get familiar with the Azure Data Factory, which will be used later in the Data Ingestion feature.  

We advise the following resources for you:
- https://learn.microsoft.com/en-us/azure/data-factory/introduction
- https://learn.microsoft.com/en-us/azure/data-factory/concepts-pipelines-activities?tabs=data-factory
- https://learn.microsoft.com/en-us/azure/data-factory/concepts-parameters-variables
- https://learn.microsoft.com/en-us/azure/data-factory/concepts-nested-activities
- https://learn.microsoft.com/en-us/azure/data-factory/concepts-linked-services?tabs=data-factory
- https://learn.microsoft.com/en-us/azure/data-factory/concepts-datasets-linked-services?tabs=data-factory
- https://learn.microsoft.com/en-us/azure/data-factory/concepts-pipeline-execution-triggers
- https://learn.microsoft.com/en-us/training/modules/intro-to-azure-data-factory/

## Mermaid Code for Modelling Data and Visualizing
Mermaid code can be used in a variety of contexts, including software development, project management, and more. It is particularly useful for creating diagrams and flowcharts in documentation, as it allows developers and other technical professionals to quickly and easily create visual representations of complex concepts and processes.

We want to get familiar with Mermaid code in order to create ERD models for our data. This will enable us to represent complex relationships and dependencies in a clear and understandable way.

## Get familiar with Data - OpenSky
In this DE track, you will work with OpenSky data source, which provides real-time flight information, including flight paths, positions, and flight status. 

In the upcoming Features, you will ingest the data, transform them and load them in the Delta Lake. Before starting these tasks, you need to get familiar with the data sets that will be needed.

For the purpose of this track, you need to look into the following data set APIs:
- All State Vectors - https://openskynetwork.github.io/opensky-api/rest.html#all-state-vectors
- Flights in time - https://openskynetwork.github.io/opensky-api/rest.html#flights-in-time-interval
- Metadata - https://opensky-network.org/datasets/#metadata/

If you want to explore more data on your own, you can look at the vast APIs that OpenSky offers.

You can also install the OpenSky library directly on your local machine, using the following command:

pip install -e "git+https://github.com/openskynetwork/opensky-api.git#egg=opensky-api&subdirectory=python"

Also, you can use Postman or any other tool that you are familiar with.

Sources : 

- https://openskynetwork.github.io/opensky-api/index.html
- https://opensky-network.org/

## Exercise

Now that you've explored the OpenSky data sources and learned about Mermaid for data modeling, it's time to put your knowledge into practice.

### Task: Model the OpenSky Data with Mermaid

Create an Entity Relationship Diagram (ERD) using Mermaid code that models the OpenSky data you'll be working with throughout this data engineering track. Your diagram should represent the relationships between the different data sources you explored.
#### Requirements:

- Identify the key entities from each data source
- Define the attributes (fields) for each entity
- Show the relationships between entities (one-to-one, one-to-many, many-to-many)
- Use proper Mermaid ERD syntax
- Consider which fields would serve as primary keys and foreign keys

#### Deliverables:

Create a Mermaid diagram that clearly shows:
- Entity names
- Key attributes for each entity
- Relationships with cardinality indicators
- Any constraints or special relationships

This model will serve as the foundation for understanding the data pipeline you'll build in subsequent parts of this track. A well-designed data model will help you make better decisions during data ingestion, transformation, and storage phases.

**Tip**: Start by examining the API responses from OpenSky to identify the actual fields returned by each endpoint. Think about how these different data sources connect to each other in a real-world aviation data context.
