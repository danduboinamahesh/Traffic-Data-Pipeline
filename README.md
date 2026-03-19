#   Real-Time Traffic Data Monitoring Pipeline (Databricks + PySpark)

## Project Overview 

The Real-Time Traffic Data Monitoring Pipeline is a scalable data engineering solution designed to ingest, process, and analyze streaming traffic data for real-time insights. This project leverages modern Lakehouse architecture using Databricks, PySpark, Delta Lake, and AWS services to build an end-to-end pipeline that handles high-volume traffic sensor data efficiently. Traffic data (vehicle count, speed, timestamps, etc.) is streamed through Amazon Kinesis, processed in near real-time, and stored across Bronze, Silver, and Gold layers in Delta Lake for structured analytics and reporting.

The pipeline ensures:
- Reliable ingestion of streaming data
- Data cleansing and validation
- Real-time computation of traffic metrics
- Scalable storage and optimized querying
---
## Project Objective
- Build a scalable real-time traffic monitoring pipeline to handle continuous data from sensors  
- Process high-volume streaming data using AWS Kinesis for near real-time ingestion  
- Store and transform data in Databricks Delta Lake using Medallion Architecture  
- Generate analytics for congestion detection, traffic patterns, and anomaly identification  
- Provide interactive dashboards to support real-time monitoring and decision-making

---

##   Dataset

### Dataset Source  
Simulated Traffic Sensor Data (Streaming via Amazon Kinesis)

The dataset represents real-time traffic data collected from sensors across city roads.

https://www.kaggle.com/datasets/sonalsadia/traffic-detection-dataset

---

### Datasets Used

- Traffic Readings → Vehicle count, speed, congestion  
- Vehicle Metrics → Flow rate, density, delay  
- Speed Monitoring → Speed violations and variance  
- Incident Events → Accidents and disruptions  
- Signal Performance → Traffic signal efficiency  

These datasets simulate a **real-world smart city traffic system**.

---

## LakeHouse Architecture

<img width="1536" height="1024" alt="ChatGPT Image Mar 18, 2026, 04_27_27 PM (1)" src="https://github.com/user-attachments/assets/ca3d00ce-1635-4521-821a-9efd6ab368aa" />




---

##   Technologies Used

Python – Used for building data processing logic, scripting, and integration tasks across the pipeline

PySpark – Handles large-scale data transformations, cleaning, aggregations, and streaming processing in Databricks

Databricks – Core platform for data engineering; used for implementing Medallion Architecture and managing Delta Lake

AWS S3 – Serves as the data lake for storing raw (Bronze) and processed data in a scalable and cost-effective way

AWS Lambda – Enables serverless event-driven data ingestion and triggers streaming workflows

Amazon Kinesis – Handles real-time streaming ingestion of traffic data with high throughput and low latency

Amazon Firehose – Delivers streaming data from Kinesis to S3 after converting it into optimized formats like Parquet

AWS Glue – Used for metadata management, schema handling, and data cataloging

Apache Airflow – Orchestrates and schedules the pipeline workflows using DAGs and manages dependencies

Slack – Sends real-time alerts and notifications for pipeline failures and monitoring

---

###   Star Schema

#### Dimension Tables
- `dim_sensor`  
- `dim_location`  
- `dim_time`  
- `dim_lane`  
- `dim_weather`  

#### Fact Table
- `fact_traffic_stats`  

---

### Features Generated

- Traffic congestion metrics  
- Average speed trends  
- Vehicle density analysis  
- Incident tracking metrics  
- Signal wait time analysis  
- Travel time index  

---

##   Analytics Dashboards & Artifacts

Refer Dashboards Folder

### Dashboards

####   Congestion Hotspots Dashboard
Analyzes high traffic congestion areas across different locations.

####   Peak Traffic Hours Dashboard
Shows traffic patterns across different hours of the day.

####   Incident Monitoring Dashboard
Tracks accidents and disruptions across roads.

####   Traffic Signal Optimization Dashboard
Analyzes signal wait time and efficiency.

####   Traffic Delay Dashboard
Analyzes travel time trends and delays.

---

##   Business Insights Generated

The pipeline enables several **smart city traffic insights**:

### Traffic Trends
Identify peak hours and daily traffic patterns.

### Congestion Analysis
Detect high congestion zones and bottlenecks.

### Incident Monitoring
Identify accident-prone areas.

### Signal Optimization
Improve signal timings to reduce delays.

### Traffic Delay Analysis
Predict travel delays using historical patterns.

---

##   Data Quality Checks

Implemented checks include:

- Null value validation  
- Duplicate detection  
- Schema validation  
- Invalid data filtering  
- Streaming error handling  

### Monitoring

- Databricks logs  
- Streaming checkpoints  
- Error logging tables  

---

##   Project Folder Structure

```
real-time-traffic-pipeline
│
├── ingestion
│ └── bronze_ingestion.py
│
├── transformations
│ └── silver_transformation.py
│
├── analytics
│ └── gold_layer.py
│
├── utils
│ └── data_quality.py
│
├── workflows
│ └── pipeline_runner.py
│
├── configs
│
├── requirements.txt
└── README.md
```

##   Pipeline Execution Flow

```
bronze_ingestion.py
↓
silver_transformation.py
↓
gold_layer.py
↓
pipeline_runner.py
```


The `pipeline_runner.py` script orchestrates the entire ETL pipeline.

---


Git & GitHub – Used for version control, code management, and collaboration across the project

---

