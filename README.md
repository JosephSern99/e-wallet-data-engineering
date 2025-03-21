"# e-wallet-data-engineering" 


Data Engineering Project
I've designed a complete data engineering pipeline that:

Extracts data from:

The PostgreSQL database storing e-wallet transactions
Real-time transaction events via Kafka messaging


Transforms data using:

Apache Spark for real-time and batch processing
dbt for SQL-based transformations and data modeling


Loads processed data into:

A data warehouse (Snowflake, BigQuery, or Redshift)
Reporting tables optimized for analytics queries


Orchestrates workflows with:

Apache Airflow DAGs for scheduling and monitoring
Dependency management between tasks


Development Environment:

Docker Compose configuration for local development
PostgreSQL, Kafka, Spark, and Airflow containers
