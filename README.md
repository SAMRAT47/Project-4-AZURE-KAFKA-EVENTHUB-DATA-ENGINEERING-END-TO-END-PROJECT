
# **UBER REAL-TIME DATA ENGINEERING PROJECT**

=======
# AZURE-KAFKA-EVENTHUB-DATA-ENGINEERING-END-TO-END-PROJECT
End-To-End Data Engineering Project built using Databricks, Azure Data Factory, Azure Event Hubs, PySpark, Spark Structured Streaming, and Spark Declarative Pipelines.

This project demonstrates a production-grade, end-to-end real-time streaming data pipeline for a ride-sharing service like Uber. It utilizes a modern Medallion Architecture to process high-velocity event data from a web application and merge it with historical bulk data to create a comprehensive analytical data model.

![Project Image](https://github.com/SAMRAT47/Project-4-AZURE-KAFKA-EVENTHUB-DATA-ENGINEERING-END-TO-END-PROJECT/blob/main/thumbnail.png)

🏗️ Architecture Overview
The pipeline follows the Medallion Architecture (Bronze, Silver, Gold layers) and is entirely metadata-driven.

Ingestion Layer: A Fast-API web application simulates ride bookings, sending real-time events to Azure Event Hubs.

Bronze Layer:

Real-time: Spark Structured Streaming ingests events from Event Hubs.

Batch: Azure Data Factory (ADF) orchestrates the ingestion of mapping data and historical bulk rides from GitHub/HTTP sources.

Silver Layer: Uses Spark Declarative Pipelines (SDP) and Jinja Templating to perform metadata-driven joins, creating "One Big Table" (OBT) from streaming and batch sources.

Gold Layer: Transforms the OBT into a Star Schema (Fact and Dimension tables), implementing SCD Type 2 for location tracking.

![Project Architecture](https://github.com/anshlambagit/Uber_Data_Engineer_Project/blob/main/architecture.png)

🌟 Project Specialties
Databricks-Centric: Developed entirely within the Databricks ecosystem using Unity Catalog for governance.

Spark Declarative Pipelines (SDP): Leverages the latest upgrade in Apache Spark for declarative, automated pipeline orchestration.

Spark Structured Streaming: Handles real-time event processing with watermarking for late-arrival data.

Metadata-Driven Design: Uses Jinja2 templates to generate SQL queries dynamically, allowing the pipeline to scale to new tables without code changes.

Advanced SCD Handling: Implements Slowly Changing Dimensions (Type 2) to maintain historical accuracy of dimensional data.

🛠️ Tech Stack
Platform: Azure, Databricks (Unity Catalog)

Orchestration: Azure Data Factory (ADF)

Streaming: Azure Event Hubs (Kafka Interface), Spark Structured Streaming

Processing: PySpark, Spark Declarative Pipelines (SDP)

Languages: Python, SQL, Jinja2 (Templating)
