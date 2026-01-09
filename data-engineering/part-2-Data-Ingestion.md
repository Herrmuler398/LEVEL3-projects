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

1. Decide on a strategy to organize code, such that, the business logic is modular and unit testable to the possible extent. One way to make this possible is to, have the business logic outside the notebooks as python scripts, which can then be unit tested and also these functions could be invoked from a orchestrating file. But you can be creative and choose any strategy, which meets this requirement.

1. The automated unit testing should be possible from any environment with the required version of python installed (for example from an Azure DevOps pipeline, or from your colleagues laptop). To make this possible, it should be possible to create a python virtual environment and install all dependencies required for unit testing. One could make use of tools like [uv package manager](https://docs.astral.sh/uv/#installation) for this.

1. Implement a mechanism to handle changes in reference data (e.g., Airports, Airlines). Since this data can change over time, you need to decide on a strategy (SCD Type 1 for overwriting or SCD Type 2 for tracking history) and implement it. Your ingestion process should be able to identify new, updated, or deleted records and apply the changes to your target tables effectively.

**Deliverables**

- Documented the decision as a markdown file.
- Created a scaffolding folder structure, which includes the folders to place different components (for example, notebooks, python scripts, unit test scripts etc) along with required configuration files (for example .toml file and uv.lock files if you are using uv).
- Re-usable functions to accelerate development for future use cases.
- Instructions to use the tool of your choice to manage virtual environments and dependencies as a README.md file.
- Implementation and demonstration of SCD logic (Type 1 or Type 2) for at least one reference data entity.

<!-- ## Outline
- [Ingest Flights Data](#ingest-flights-data)
- [Ingest State Vectors Data](#ingest-state-vectors-data)
- [Ingest Metadata](#ingest-metadata)
- [Deliverables](#deliverables)

## Ingest Flights Data

The following operational data from the OpenSky API should be extracted:
- Flights in time - https://openskynetwork.github.io/opensky-api/rest.html#flights-in-time-interval

This API call retrieves flights for a certain time interval [begin, end]. If no flights are found for the given time period, HTTP status 404 - Not found is returned with an empty response body.

**Destination**: Unity Catalog volume path: `/Volumes/track/incoming/<name>/opensky/flights`

**Schedule**: Every 2 hours

## Ingest State Vectors data
The following operational data from the OpenSky API should be extracted:
- All State Vectors - https://openskynetwork.github.io/opensky-api/rest.html#all-state-vectors

**Destination**: Unity Catalog volume path: `/Volumes/track/incoming/<name>/opensky/state_vectors`

**Schedule**: Every 2 hours



## Ingest Metadata
[The OpenSky aircraft database](https://opensky-network.org/datasets/#metadata/) is a comprehensive collection of information about various aircraft that are part of the data collected by the OpenSky network of sensors. This database contains a wealth of information such as the aircraft's type, manufacturer, registration, operator, and physical characteristics including dimensions, weight, and performance capabilities. It is continually updated as new aircraft are detected by the OpenSky sensors, and as new information becomes available. This database is accessible through the OpenSky Network API, and it is widely used by researchers, developers, and other interested parties for a variety of purposes including flight tracking, air traffic control, and monitoring aircraft performance.

The aircraft metadata is updated monthly and you can find it here:
- Metadata - https://opensky-network.org/datasets/#metadata/

**Destination**: Unity Catalog volume path: `/Volumes/track/incoming/<name>/opensky/metadata`

**Schedule**: Monthly

## Deliverables:
1. The raw data is successfully retrieved from the OpenSky API, ensuring all required data fields are included.
1. The retrieved data is stored in Unity Catalog volumes using the appropriate data model, organized, and formatted correctly.
1. The ingested data is validated to ensure accuracy and up-to-date information.
1. A scheduled data ingestion process is implemented that regularly retrieves the data according to the specified schedules.
1. The data ingestion process is monitored to ensure smooth and reliable operation. -->