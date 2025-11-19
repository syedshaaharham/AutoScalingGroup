# Real-Time Stock Data Pipeline on AWS

Build a cloud-native system for live stock market analytics, leveraging Apache Kafka, EC2, S3, AWS Glue, and Athena. This project demonstrates modern streaming, cloud data lakes, and instant SQL for financial data.

## Architecture Overview

- EC2 instance generates synthetic tick data in real time and streams it into Kafka topics.
- Consumers pull data from Kafka, writing ticks to Amazon S3 for scalable, durable lake storage.
- AWS Glue Crawlers scan S3 paths and update the Data Catalog automatically as new files land.
- Athena queries let you explore the most current stock data with interactive SQL.
- Dashboards built on Athena provide instant insight, anomaly detection, and visual analytics.

## Features

- **Live Streaming:** Ticks are produced and ingested continuously, simulating an actual market feed.
- **Cloud Data Lake:** Raw records are stored in S3, instantly accessible across tools and workflows.
- **Automated Discovery:** Glue Crawler keeps metadata fresh, supporting flexible schema evolution.
- **Instant Queries:** Athena exposes the latest data for rapid insights—no batch ETL delays.
- **Modular Design:** Easily extend to other domains (IoT, ML, finance) thanks to loosely coupled AWS services.

## Usage Instructions

1. Provision Kafka clusters and EC2 on AWS.
2. Deploy sample producers to stream random tick data into Kafka topics.
3. Run consumers to land data into S3 (formats: CSV, JSON, or Parquet).
4. Set up a Glue Crawler to auto-catalog data as your models evolve.
5. Run queries in Athena for analytics, reporting, and dashboards.

## Applications

- Real-time financial engineering and trading studies.
- Live market intelligence dashboards.
- IoT/streaming schema-on-read prototyping.
- Proof-of-concept for automated cloud data pipeline.

## Getting Started

- Launch all relevant AWS services (EC2, S3, Glue, Athena).
- Configure Kafka and test message streaming.
- Use provided utility scripts or adapt for your target symbols and tick intervals.
- Monitor Athena and Glue for live data ingestion and schema updates.

