# Airline-Data-Ingestion-AWS

## 📌 Project Overview
This project demonstrates an **end-to-end data engineering pipeline** built on AWS to process, transform, and analyze airline flight and airport data. The pipeline is designed to automate data ingestion, enrichment, and loading into a cloud data warehouse for reporting and analytics.

---

## ⚙️ Architecture
1. **Data Ingestion**
   - Raw CSV files (airports, flights) are uploaded to **Amazon S3**.
   - **Amazon EventBridge** triggers downstream workflows whenever a new file arrives.

2. **Data Processing**
   - **AWS Glue (PySpark ETL job)**:
     - Cleans and filters flight data (e.g., delays > 60 minutes).
     - Joins flight data with airport dimension tables.
     - Applies schema mapping and transformations.

3. **Data Storage**
   - Transformed data is loaded into **Amazon Redshift** using a **star schema**:
     - `airports_dim` (dimension table)
     - `daily_flights_fact` (fact table)

4. **Orchestration & Monitoring**
   - **AWS Step Functions** orchestrates the workflow:
     - Starts Glue crawler
     - Runs ETL job
     - Publishes success/failure notifications via **Amazon SNS**

---

## 🗂️ Repository Contents
- `airports.csv` → Airport dimension dataset  
- `flights.csv` → Flight fact dataset  
- `event_bridge_rule.json` → EventBridge rule to trigger pipeline on S3 uploads  
- `glue_job.py` → AWS Glue ETL script (PySpark)  
- `redshift_create_table_commands.txt` → SQL commands for Redshift schema & tables  
- `step_function_code.json` → Step Functions state machine definition  

---

## 🛠️ Tech Stack
- **AWS Services:** S3, Glue (ETL, Crawlers, Catalog), Redshift, EventBridge, Step Functions, SNS  
- **Programming & Tools:** Python (PySpark), SQL, JSON  
- **Data Engineering Concepts:** ETL pipelines, orchestration, star schema design, data warehouse modeling  

---

## 🚀 Key Features
- Automated ingestion from S3 to Redshift  
- Event-driven orchestration using EventBridge + Step Functions  
- Scalable ETL pipeline using Glue and PySpark  
- Schema-based data modeling for analytics  
- Real-time success/failure notifications with SNS  

---

## 📊 Outcome
- Efficient pipeline to process large airline datasets.  
- Automated reporting of flight delays enriched with airport details.  
- Demonstrates practical **data engineering skills on AWS cloud**.  

---

## 📧 Contact
If you found this project useful or want to collaborate, feel free to reach out!  
 

