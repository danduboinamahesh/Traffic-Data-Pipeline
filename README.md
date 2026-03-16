# 🚦 Real-Time Traffic Data Monitoring Pipeline

A scalable **real-time traffic analytics pipeline** built using **AWS, Databricks, and Apache Spark** to ingest, process, and analyze streaming traffic data using **Medallion Architecture (Bronze, Silver, Gold)**.

---

## 🏗 Architecture

Traffic Sensors / Dataset
│
▼
Kinesis Data Streams
│
▼
Kinesis Firehose
│
▼
Amazon S3
│
▼
Databricks (Streaming + Batch Processing)
│
▼
Medallion Architecture

* **Bronze Layer** → Raw traffic data
* **Silver Layer** → Cleaned & validated data
* **Gold Layer** → Star schema for analytics

  ```
    │  
    ▼  
  ```

Databricks SQL Warehouse
│
▼
Dashboards & Alerts

---

## ⚙️ Tech Stack

* AWS S3
* AWS Kinesis Data Streams
* AWS Kinesis Firehose
* AWS Glue
* Databricks
* Apache Spark
* Delta Lake
* Apache Airflow
* PyTest
* GitHub

---

## 📊 Data Layers

### Bronze Layer

Stores raw streaming data.

Tables:

* traffic_readings
* vehicle_metrics
* speed_monitoring
* incident_events
* signal_performance

### Silver Layer

Cleaned and validated data.

Features:

* Deduplication
* Schema validation
* Data quality checks
* Derived metrics

### Gold Layer

Analytics-ready **Star Schema**.

Dimension Tables:

* dim_sensor
* dim_location
* dim_lane
* dim_time
* dim_weather

Fact Table:

* fact_traffic_stats

---

## 🔁 Pipelines

### Batch Pipeline

```
S3 → Glue → S3 → Databricks
```

### Streaming Pipeline

```
S3 → Kinesis Streams → Firehose → S3 → Databricks
```

---

## 🚨 Data Quality

Rules applied in Silver & Gold layers:

* Remove duplicate events
* Reject null sensor_id
* Remove invalid speeds
* Clean lane_id values
* Standardize timestamps

Errors are logged in **anomaly_log table**.

---

## ⏰ Orchestration

Pipelines are orchestrated using **Apache Airflow DAGs**.

Features:

* Scheduling
* Monitoring
* Retry handling
* Failure alerts

---

## 📊 Dashboards

Built using **Databricks SQL**:

* Congestion Hotspots
* Peak Traffic Hours
* Incident Monitoring
* Traffic Signal Optimization
* Traffic Delay Trends

---

## 🧪 Testing

Testing implemented using **PyTest** for:

* Data transformation validation
* Schema checks
* Data quality rules
