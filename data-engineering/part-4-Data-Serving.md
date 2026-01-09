# Part 4: Data Serving

In the context of data engineering, serving refers to making data available for use by applications, users, or other systems. It involves providing access to data in a format and location that is suitable for the intended use case, while ensuring the data is accurate, up-to-date, and secure.

Serving is important in data engineering because it enables organizations to leverage their data assets in a variety of ways. For example, serving may involve providing access to data for use in reporting or analytics, enabling real-time data processing and streaming, or providing data for use in machine learning models.

When serving data, it is important to ensure that it is in a format that is usable by the intended consumers. This may involve transforming or preprocessing data to remove duplicates, standardize formats, or aggregate data into more manageable chunks.

In addition, serving data requires consideration of performance and scalability. As data volumes grow and the number of consumers accessing the data increases, it may be necessary to optimize data storage and retrieval mechanisms, use caching to improve performance, or distribute data across multiple nodes or clusters to enable parallel processing.

Finally, serving data requires careful attention to security and privacy. This may involve using access controls and authentication mechanisms to restrict who can access the data, encrypting data in transit and at rest, and implementing monitoring and auditing mechanisms to detect and respond to unauthorized access or misuse of data.

In summary, serving is a critical step in the data engineering process, as it enables organizations to leverage their data assets in a variety of ways. By ensuring data is in a usable format, optimizing performance and scalability, and ensuring data security and privacy, organizations can derive maximum value from their data while minimizing risk and ensuring compliance.


## Dashboard of data analysis for LH OpenAPI data
As a data engineer, in this task you have to build a dashboard in Databricks SQL Warehouse on the data transformed through the medallion architecture.

The granularity of the data analysis should be at hourly level, since data have been ingested each day into the data lake and therefore into the DLT pipelines as well.

Please refer to this documentation to get familiar with Data warehousing and Dashboards with Databricks:
- https://docs.databricks.com/en/sql/index.html
- https://docs.databricks.com/en/sql/get-started/index.html
- https://docs.databricks.com/en/sql/user/sql-editor/index.html
- https://docs.databricks.com/en/sql/get-started/sample-dashboards.html
- https://learn.microsoft.com/en-us/azure/databricks/dashboards/tutorials/
