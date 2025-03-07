# ETL Pipeline: Data Ingestion from RDS to Redshift

## 📌 Project Overview
This project implements an **end-to-end ETL (Extract, Transform, Load) pipeline** to ingest, process, and analyse **ATM transaction data**. The pipeline extracts data from **AWS RDS**, transforms it using **PySpark**, and loads it into **Amazon Redshift** for analytics.

## 🚀 Tech Stack
- **Data Sources:** AWS RDS (PostgreSQL)
- **Data Extraction:** Apache Sqoop
- **Data Processing:** Apache Spark (PySpark)
- **Data Storage:** Amazon S3
- **Data Warehousing:** Amazon Redshift
- **Scripting & Querying:** Python, SQL

## 🔄 ETL Workflow
1. **Extract:**
   - Used **Apache Sqoop** to ingest **2.46M+ ATM transaction records** from **AWS RDS** into **HDFS**.
   - Achieved a transfer rate of **11.28 MB/sec**.

2. **Transform:**
   - Processed raw data using **PySpark**.
   - Created **fact and dimension tables** with primary and foreign key constraints.
   - Optimised data using **partitioning and compression** to reduce processing time by **30%**.

3. **Load:**
   - Stored transformed data in **Amazon S3**.
   - Loaded structured data into **Amazon Redshift**.

## 📊 Data Model
### Fact Table
- **FACT_ATM_TRANS**: Stores transactional data with references to dimension tables.

### Dimension Tables
- **DIM_LOCATION**: ATM locations with latitude and longitude.
- **DIM_DATE**: Transaction dates.
- **DIM_CARD_TYPE**: Types of cards used.
- **DIM_ATM**: ATM machine details.

## 🛠 Key Features
- **Automated ETL pipeline** using **PySpark**.
- **Optimised queries in Amazon Redshift** to analyse:
  - **Top 10 ATMs with inactive status**.
  - **Top 10 active ATMs** based on transaction volume.
- **Efficient Data Storage**: Leveraged **Amazon S3** for scalable and cost-effective data warehousing.

## 📂 Project Structure
```
├── scripts
│   ├── extract_data.sh         # Sqoop script for data extraction
│   ├── transform_data.py       # PySpark script for data transformation
│   ├── load_data.sql           # SQL queries for Redshift loading
│
├── queries
│   ├── analytics_queries.sql   # Redshift analytical queries
│
├── data
│   ├── raw_data/               # Extracted data from RDS
│   ├── transformed_data/       # Processed data stored in S3
│
├── README.md
```

## 🏆 Outcomes
- Reduced data processing time by **30%** through **partitioning and optimised compression**.
- Enabled **real-time ATM analytics** using **Amazon Redshift**, improving operational efficiency.
- Successfully processed **2.46M+ records** for detailed transactional insights.

## 📌 How to Run
### 1️⃣ Setup Environment
- Configure AWS credentials.
- Install required dependencies (`pip install pyspark boto3 psycopg2`).

### 2️⃣ Run Extraction
```bash
bash scripts/extract_data.sh
```

### 3️⃣ Run Transformation
```bash
python scripts/transform_data.py
```

### 4️⃣ Load Data into Redshift
Execute SQL scripts in `queries/load_data.sql`.

### 5️⃣ Run Analytical Queries
Execute `queries/analytics_queries.sql` in Amazon Redshift.

## 📬 Contact
For queries, reach out to **Rutvik Tidke** at [rutviktidke@gmail.com](mailto:rutviktidke@gmail.com).


