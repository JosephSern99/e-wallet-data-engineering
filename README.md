# Data Engineering Flow for E-Wallet Transaction Analysis

This document outlines the data engineering flow for analyzing e-wallet transaction data, from the source PostgreSQL database to visualization in Metabase.

## Components

1.  **Data Source (Existing PostgreSQL Database):**
    * Contains e-wallet transaction data.
    * Serves as the initial source for the data pipeline.

2.  **Data Extraction (Airbyte):**
    * Uses Airbyte, an open-source data integration platform.
    * Extracts data from the PostgreSQL database.
    * Supports scheduled extractions (e.g., daily, hourly).

3.  **Data Processing (Kafka):**
    * Leverages Kafka for real-time processing of transaction events.
    * Utilizes Kafka topics for different data streams (e.g., "transactions", "user-activity").

4.  **Data Transformation (dbt):**
    * Employs dbt (data build tool) for transforming raw data into analytics models.
    * Creates models representing business concepts (e.g., daily transaction summaries, user spending patterns).

5.  **Data Storage (Data Warehouse):**
    * Utilizes a separate PostgreSQL instance as the data warehouse.
    * Structured to optimize for analytical queries.

6.  **Data Visualization (Metabase):**
    * Provides dashboards using Metabase.
    * Creates visualizations of transaction patterns, user behavior, etc.

## Data Flow

1.  **Extraction:** Airbyte extracts data from the source PostgreSQL database based on a defined schedule.
2.  **Streaming:** Extracted data is streamed into Kafka topics for real-time processing.
3.  **Transformation:** dbt transforms the raw data from Kafka or the raw data warehouse tables, creating analytics-ready models within the data warehouse.
4.  **Storage:** Transformed data is stored in the data warehouse (PostgreSQL) optimized for analytical queries.
5.  **Visualization:** Metabase connects to the data warehouse and creates dashboards and visualizations for analysis.

## Diagram

```mermaid
graph TD
    A[PostgreSQL (Data Source)] --> B(Airbyte);
    B --> C(Kafka);
    C --> D(dbt);
    A --> D;
    D --> E[PostgreSQL (Data Warehouse)];
    E --> F(Metabase);
