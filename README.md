# Data Engineering Pipeline Project

This project outlines a complete data engineering pipeline designed to process e-wallet transactions from both a PostgreSQL database and real-time Kafka streams, transform them, and load them into a data warehouse for analytical purposes.

## Data Extraction

* **PostgreSQL Database:**
    * Extracts historical e-wallet transaction data from a PostgreSQL database.
* **Kafka Messaging:**
    * Captures real-time transaction events via a Kafka messaging system.

## Data Transformation

* **Apache Spark:**
    * Utilizes Apache Spark for both real-time stream processing and batch data transformations.
* **dbt (data build tool):**
    * Employs dbt for SQL-based data transformations and data modeling, ensuring data consistency and quality.

## Data Loading

* **Data Warehouse:**
    * Loads the processed and transformed data into a cloud-based data warehouse, with support for:
        * Snowflake
        * Google BigQuery
        * Amazon Redshift
* **Reporting Tables:**
    * Creates optimized reporting tables within the data warehouse to facilitate efficient analytics queries.

## Workflow Orchestration

* **Apache Airflow:**
    * Orchestrates the entire data pipeline using Apache Airflow DAGs (Directed Acyclic Graphs).
    * Provides scheduling and monitoring capabilities for all pipeline tasks.
    * Manages dependencies between tasks to ensure proper execution order.

## Development Environment

* **Docker Compose:**
    * Configures a local development environment using Docker Compose.
    * Includes containers for:
        * PostgreSQL
        * Kafka
        * Apache Spark
        * Apache Airflow
    * This allows for easy local testing and development of the entire pipeline.
