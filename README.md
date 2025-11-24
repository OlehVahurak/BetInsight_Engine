# **Betflow: Real-time Sports Betting Analytics Platform**

Betflow is an end-to-end **data and analytics engineering platform** built to process and analyze **real-time sports data** at scale. It combines modern streaming and batch technologies to deliver sub-second insights, historical analysis, and production-grade data models.

---

## **Disclaimer**
This project **does not promote gambling**.  
Its purpose is to demonstrate real-world **Data Engineering** and **Analytics Engineering** skills using a cloud-native, open-source tech stack.

---

# **Key Features**
- Real-time odds and game event processing  
- Multi-source data ingestion (sports, odds, weather)  
- Sub-second streaming analytics  
- Historical trend and pattern analysis  
- Automated data quality and schema validation  
- Dual pipeline design: **Streaming + Batch**  
- Custom dashboards for insights and monitoring  

---

# **Architecture Overview**

Betflow consists of two pipelines:

### **1. Real-time Pipeline**
- **Sources:** ESPN, Odds API, OpenWeather  
- **Kafka:** Event streaming, KRaft mode  
- **Spark Structured Streaming:** Windowed aggregations, enrichment  
- **Apache Druid:** Sub-second OLAP analytics  
- **Grafana:** Real-time dashboards and alerting  

**Flow:** APIs → Kafka → Spark → Druid → Grafana  
**Highlights:** <1s latency, scalable, fault-tolerant

---

### **2. Batch Pipeline**
- **Storage:** S3 raw → processed zones  
- **ETL:** AWS Glue + Apache Iceberg  
- **Analytics:** Snowflake external tables  
- **dbt:** Bronze/Silver/Gold transformations + DQ checks  

**Flow:** S3 → Glue → Iceberg → Snowflake/dbt  
**Highlights:** Strong modeling, historical analytics, high scalability

---

# **Analytics**
- **Game performance:** scoring trends, home/away splits  
- **Odds analytics:** line movement, market efficiency, bookmaker comparison  
- **Cross-domain:** weather correlations, multi-factor patterns  

Includes SCD, CDC, and time-series growth accounting.

---

# **Why Betflow Is Unique**
- True real-time streaming with Kafka + Spark  
- Batch architecture for historical analytics  
- Advanced multi-domain data modeling  
- Scalable, cloud-native design  
- Supports multiple sports (NFL, NBA, NHL, NCAAF)

---

# **Roadmap (In Progress)**
- dbt Gold layer  
- Batch dashboards  
- CI/CD + testing framework  
- Unified Kafka orchestrator  
- News/sentiment integration  




