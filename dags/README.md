## **DAG Structure**

### **1. Parent DAG**
- Orchestrates the execution of all child DAGs  
- Ensures dependencies between ingestion, processing, and analytics tasks  
- Provides monitoring and failure handling at the top level  

---

### **2. Ingestion DAG**
- Collects raw data from multiple sources:
  - ESPN API (live game stats)  
  - The Odds API (real-time betting odds)  
  - OpenWeather API (venue weather conditions)  
- Publishes data into Kafka topics or S3 raw buckets  
- Implements retries and error handling for API calls  

---

### **3. Processing DAG**
- Transforms and enriches ingested data:
  - Cleans and validates raw JSON  
  - Applies schema enforcement  
  - Performs aggregations for streaming or batch analytics  
- Writes processed data to:
  - Apache Druid (real-time analytics)  
  - S3 / Snowflake (historical analysis)  

---

### **4. Task Groups**
- Modularizes DAG tasks for better readability and maintainability  
- Examples:
  - `extract_tasks`: API ingestion and raw data storage  
  - `transform_tasks`: Cleaning, validation, enrichment  
  - `load_tasks`: Writing to target storage (Druid, Snowflake, S3)  
  - `monitoring_tasks`: Alerts, logging, and notifications  
