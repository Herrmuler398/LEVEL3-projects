# Part 1: Fundamentals

This part covers the foundational concepts and skills essential for data engineering such as the integration of Apache Spark with Azure.


## Outline

1. [Azure Databricks](#azure-databricks)
1. [Mermaid Code for Modelling Data and Visualizing](#mermaid-code-for-modelling-data-and-visualizing)
1. [Get familiar with Data - LH OpenAPI](#get-familiar-with-data---lh-openapi)
1. [Exercise](#exercise)

## Azure Databricks

Setup a databricks workspace using the [Databricks Free Edition]((https://docs.databricks.com/en/getting-started/community-edition.html)) and research the following topics:

### Platform Basics & UI
- Databricks UI and workspace navigation - [Source](https://docs.databricks.com/en/workspace/index.html)

### Compute & Development environment
- Compute clusters (creation, configuration, autoscaling, and cluster policies) - [Source](https://docs.databricks.com/en/compute/index.html)
- Notebooks fundamentals (cells, magic commands, visualizations) - [Source](https://docs.databricks.com/en/notebooks/index.html)
- Git folders and version control integration - [Source](https://docs.databricks.com/en/repos/index.html)

### Data Management & Storage
- Unity Catalog - [Source](https://docs.databricks.com/en/data-governance/unity-catalog/index.html)
- Databricks volumes - [Source](https://docs.databricks.com/en/volumes/index.html)
- Delta Lake fundamentals - [Source](https://docs.databricks.com/en/delta/index.html)
### Pipelines, Orchestration & Security
- Data ingestion patterns (batch vs streaming) - [Source](https://docs.databricks.com/en/ingestion/index.html)
- Lakeflow Spark Declarative Pipelines (SDPs) - [Source](https://docs.databricks.com/en/dlt/index.html)
- Lakeflow Jobs - [Source](https://docs.databricks.com/en/jobs/index.html)
- Secret scopes - [Source](https://docs.databricks.com/en/security/secrets/secret-scopes.html)


## Mermaid Code for Modelling Data and Visualizing
Mermaid code can be used in a variety of contexts, including software development, project management, and more. It is particularly useful for creating diagrams and flowcharts in documentation, as it allows developers and other technical professionals to quickly and easily create visual representations of complex concepts and processes.

We want to get familiar with Mermaid code in order to create entity relationship models for our data. This will enable us to represent complex relationships and dependencies in a clear and understandable way.

## Get familiar with Data - LH OpenAPI
In this DE track, you will work with LH OpenAPI data source, which provides real-time flight information, including flight paths, positions, and flight status. 

In the upcoming tasks, you will ingest the data, transform them and load them in the Delta Lake. Before starting these tasks, you need to get familiar with the data sets that will be needed.

For the purpose of this track, you need to look into the following data set APIs:
- Reference Data (Countries, Cities, Airports, Airlines, Aircraft) - https://developer.lufthansa.com/docs/read/api_details/Reference_Data
- Flight Status by Route - https://developer.lufthansa.com/docs/read/api_details/operations/Flight_Status_by_City_Pair


If you want to explore more data on your own, you can look at the vast APIs that LH OpenAPI offers.

Sources : 

- https://developer.lufthansa.com/docs
- https://developer.lufthansa.com/page

## Exercise

Create an ER (Entity-Relationship) model for the Lufthansa Open API using the Mermaid modeling language, so that one can visualize and understand the structure and relationships of the data while preparing for future use.

Create an overview of the entities, relationship between the entities and constraints.

**Deliverables**

An ER model that:

- Accurately represents all relevant entities, attributes, and relationships for the following entities: flight status, aircraft, airport, airlines, cities, and countries
- Is easily understandable, with clear entity names, attribute labels, and relationship annotations
- Includes cardinality indicators for relationships, providing clarity on the associations between entities


## Advanced Challenge (Optional)

Decide the data modelling technique to be used. Consider the pros and cons of each technique, and requirements to arrive at your decision. There is no ONE right answer here, so please compliment your decision with the reasoning. Feel free to make assumptions and document them, when certain things are not clear in the requirement. A good starting point for this process could be [this Databricks blog](https://www.databricks.com/blog/2022/06/24/data-warehousing-modeling-techniques-and-their-implementation-on-the-databricks-lakehouse-platform.html).
