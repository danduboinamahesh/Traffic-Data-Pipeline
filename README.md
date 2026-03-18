#   Real-Time Traffic Data Monitoring Pipeline (Databricks + PySpark)

##   Project Overview

This project implements an **end-to-end real-time data pipeline** for traffic monitoring using **AWS, Databricks, PySpark, and Delta Lake**.

The pipeline processes **streaming traffic sensor data** and transforms it into analytics-ready datasets using the **Medallion Architecture (Bronze → Silver → Gold)**.

The final output enables **real-time traffic monitoring and smart city analytics** by generating key insights such as:

- Traffic congestion patterns  
- Peak traffic hours  
- Incident monitoring metrics  
- Signal performance insights  
- Traffic delay trends  

---

##   Dataset

### Dataset Source  
Simulated Traffic Sensor Data (Streaming via Amazon Kinesis)

The dataset represents real-time traffic data collected from sensors across city roads.

---

### Datasets Used

- Traffic Readings → Vehicle count, speed, congestion  
- Vehicle Metrics → Flow rate, density, delay  
- Speed Monitoring → Speed violations and variance  
- Incident Events → Accidents and disruptions  
- Signal Performance → Traffic signal efficiency  

These datasets simulate a **real-world smart city traffic system**.

---

##   Project Architecture

The pipeline integrates **AWS streaming services, Databricks processing, and Delta Lake analytics modeling**.

### End-to-End System Architecture

Traffic Sensors / Dataset  
│  
▼  
Amazon Kinesis Data Streams  
│  
▼  
Databricks Structured Streaming  
│  
▼  
Amazon S3 / Delta Lake  
│  
▼  
Medallion Architecture (Bronze → Silver → Gold)  
│  
▼  
Databricks SQL Warehouse  
│  
▼  
Dashboards & Analytics  

---

##   Medallion Architecture Layers

###   Bronze Layer (Raw Data)

#### Purpose
- Store raw streaming data exactly as received  
- Preserve data lineage  
- Enable traceability of raw ingestion  

#### Tables
- `traffic_catalog.raw.traffic_readings`  
- `traffic_catalog.raw.traffic_vehicle_metrics`  
- `traffic_catalog.raw.traffic_speed_monitoring`  
- `traffic_catalog.raw.traffic_incident_events`  
- `traffic_catalog.raw.traffic_signal_performance`  

#### Operations
- Streaming ingestion from Amazon Kinesis  
- JSON parsing  
- Schema validation  
- Raw storage in Delta Lake  

---

###   Silver Layer (Cleaned Data)

#### Purpose
- Clean and standardize datasets  
- Apply data quality rules  
- Integrate multiple datasets  

#### Transformations
- Remove duplicate records  
- Handle missing values  
- Filter invalid speed values  
- Standardize timestamps  
- Cast data types  
- Trim and clean data  

#### Derived Features
- Speed variance  
- Traffic flow rate  
- Congestion flag  

#### Output Tables
- `traffic_catalog.processed.valid_readings`  
- `traffic_catalog.processed.vehicle_metrics`  
- `traffic_catalog.processed.speed_metrics`  
- `traffic_catalog.processed.incident_metrics`  
- `traffic_catalog.processed.signal_metrics`  

---

###   Gold Layer (Analytics Data)

#### Purpose
Generate business-ready datasets for analytics and reporting.

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

*(Dashboard tool will be added here)*

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

##   Technologies Used

- Python  
- PySpark  
- Databricks  
- Delta Lake  
- AWS S3  
- Amazon Kinesis  
- Databricks SQL  
- Git & GitHub  

---

