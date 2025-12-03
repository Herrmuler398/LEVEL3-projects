# Part 2: Data Ingestion

Data ingestion is the process of importing, transforming, and loading data from various sources into a storage system, such as a data warehouse, a data lake, or a database. This process involves collecting data from disparate sources, cleaning and validating it, and converting it into a format that can be easily analyzed and processed.

Data ingestion is a critical step in the data pipeline because it sets the foundation for the subsequent data processing and analysis. The ingestion process can be done in real-time or batch mode depending on the nature of the data, the processing requirements, and the business needs.

The data sources for ingestion can include structured data, such as data from a relational database, as well as semi-structured and unstructured data such as text files, logs, social media feeds, and IoT sensors. Data ingestion also involves the application of data governance policies to ensure the accuracy, completeness, and security of the data being ingested.

As part of this track, you will be implementing pipelines within Azure Data Factory for a data engineering project. 

In this task you need to build a pipeline to ingest the raw data from OpenSky API to the Azure Data Lake storage.

## Outline
- [Ingest Flights Data](#ingest-flights-data)
- [Ingest State Vectors Data](#ingest-state-vectors-data)
- [Ingest Metadata](#ingest-metadata)
- [Deliverables](#deliverables)

## Ingest Flights Data

The following operational data from the OpenSky API should be extracted:
- Flights in time - https://openskynetwork.github.io/opensky-api/rest.html#flights-in-time-interval

This API call retrieves flights for a certain time interval [begin, end]. If no flights are found for the given time period, HTTP status 404 - Not found is returned with an empty response body.

**Destination path**:  track / incoming / name / opensky / flights

**Trigger frequency**: Every 2 hours

## Ingest State Vectors data
The following operational data from the OpenSky API should be extracted:
- All State Vectors - https://openskynetwork.github.io/opensky-api/rest.html#all-state-vectors

**Destination path**:  track / incoming / name / opensky / state_vectors

**Trigger frequency**: Every 2 hours



## Ingest Metadata
[The OpenSky aircraft database](https://opensky-network.org/datasets/#metadata/) is a comprehensive collection of information about various aircraft that are part of the data collected by the OpenSky network of sensors. This database contains a wealth of information such as the aircraft's type, manufacturer, registration, operator, and physical characteristics including dimensions, weight, and performance capabilities. It is continually updated as new aircraft are detected by the OpenSky sensors, and as new information becomes available. This database is accessible through the OpenSky Network API, and it is widely used by researchers, developers, and other interested parties for a variety of purposes including flight tracking, air traffic control, and monitoring aircraft performance.

The aircraft metadata is updated monthly and you can find it here:
- Metadata - https://opensky-network.org/datasets/#metadata/

**Destination path**:  track / incoming / name / opensky / metadata

**Trigger frequency**: Monthly

## Deliverables:
- The raw data is successfully retrieved from the API, ensuring all required data fields are included.
- The retrieved data is stored in our system using the appropriate data model, organized, and formatted correctly
- The ingested data is validated to ensure accuracy and up-to-date information.
- An Azure Data Factory pipeline is set up with a trigger that regularly retrieves the reference data, considering the infrequent updates for this kind of data.
- The pipeline and data ingestion process are monitored to ensure smooth and reliable operation.