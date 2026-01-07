# Part 6: ELT Pipelines

1. Develop ELT pipelines to load raw, silver and gold layers.
1. Design automated unit testing for the business logic in the pipelines.
1. Package (if applicable) python libraries and manage their dependencies.



## Outline
- [Create tables in all layers](#create-tables-in-all-layers)
- [Code organising and Python environment](#code-organising-and-python-environment)
- [Ingest to Bronze Layer](#ingest-to-bronze-layer)
- [Ingest to Silver Layer](#ingest-to-silver-layer)
- [Ingest to Gold Layer](#ingest-to-gold-layer)

## Create tables in all layers

Create tables in silver and gold layer as per the DDL scripts created in Datamodelling feature.

**Deliverables**

Tables created in Unity catalogue for silver and gold layers.

## Code organising and Python environment

1. Decide on a strategy to organize code, such that, the business logic is modular and unit testable to the possible extent. One way to make this possible is to, have the business logic outside the notebooks as python scripts, which can then be unit tested and also these functions could be invoked from a orchetrating notebook. But you can be creative and choose any strategy, which meets this requirement.
1. The automated unit testing should be possible from any environment with the required version of python installed (for example from an Azure DevOps pipeline, or from your colleagues laptop). To make this possible, it should be possible to create a python virtual environment and install all dependencies required for unit testing. One could make use of tools like [python-poetry](https://python-poetry.org/docs/) for this.

**Deliverables**

1. Documented the decision as a markdown file.
1. Created a scaffolding folder structure, which includes the folders to place different components (for example, notebooks,python scripts, unit test scripts etc) along with required configuration files (for example .toml file and poetry.lock files if you are using poetry).
1. Instructions to use the tool of your choice to manage virtual environments and dependencies as a README.md file.


## Ingest to Bronze Layer

1. Ingest data from in-scope source[s] to the bronze layer.
1. Schedule the ingestion pipeline to incrementally load bronze layer.


**Deliverables**

1. Pipeline to ingest data to bronze layer developed and tested.
1. Scheduled ingestion pipeline to ingest incremental data every 24 hours.
1. Pipelines scheduled to run on 'Job clusters' and not 'All-purpose' clusters.
1. Data to be ingested in delta format unless there is a valid reasoning to do otherwise.

## Ingest to Silver Layer
1. Ingest data from bronze to silver layer.
1. Schedule the ingestion pipeline to incrementally load silver layer.
1. Develop re-usable functions to load similar tyes of tables (like dimensions, hubs or links etc)

**Deliverables**

1. Pipeline to ingest data to silver layer developed and tested.
1. Scheduled ingestion pipeline to ingest incremental data every 24 hours.
1. Pipelines scheduled to run on 'Job clusters' and not 'All-purpose' clusters.
1. Data to be ingested in delta format only.
1. Good to have - usage of re-usable functions to accelerate development for future use cases.

## Ingest to Gold Layer

1. Ingest data from silver to gold layer.
1. Automate unit testing for the business logic in the pipelines.
1. Package (if applicable) python libraries and manage their dependencies.