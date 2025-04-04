# TickSync : Real-Time Stock Data Ingestion & Analytics Pipeline

TickSync is a real-time data engineering project that simulates a stock market feed using **Apache Kafka**, processes streaming data, and enables SQL-based analysis using **Amazon Athena** over a data lake stored in **Amazon S3**. The project demonstrates best practices in event-driven architecture, cloud-native data storage, and serverless analytics.

## 🚀 Project Overview

This project showcases a scalable data pipeline that:
- Streams stock trading data in real-time using Kafka
- Stores the data in Amazon S3
- Uses AWS Glue for schema discovery and table cataloging
- Enables serverless querying through Amazon Athena

It’s ideal for scenarios requiring low-latency ingestion, transformation, and querying of financial or time-series data.

## 🛠️ Technologies & Skills Demonstrated

### 🔧 Tools & Services
- **Apache Kafka**: Handles real-time data streaming (producer + consumer)
- **AWS EC2**: Hosts Kafka broker, producer, and consumer
- **Amazon S3**: Stores raw and processed streaming data
- **AWS Glue Crawler**: Discovers schema and populates AWS Glue Data Catalog
- **AWS Glue Data Catalog**: Organizes metadata for querying with Athena
- **Amazon Athena**: Enables SQL-based querying directly over S3 data
- **IAM Roles & Policies**: Manages permissions for EC2, Glue, and Athena

### 💡 Skills Applied
- Real-time stream processing
- Cloud-based data lake architecture
- Serverless data analytics with AWS Athena
- AWS SDK usage via `boto3` (for automation and resource access)
- Data cataloging and schema evolution with Glue Crawlers
- Infrastructure configuration via IAM roles and permission boundaries

## 🧩 Architecture

![Architecture](./Architecture.jpg)

**Pipeline Flow:**
1. A Kafka **producer** (running on EC2) streams simulated stock data from a CSV file.
2. A Kafka **consumer** (also on EC2 or any Python environment) ingests the messages and writes them to **Amazon S3** as raw JSON.
3. An **AWS Glue Crawler** scans the S3 bucket to infer the schema and update the **AWS Glue Data Catalog**.
4. **Amazon Athena** queries the S3-backed tables using standard SQL for real-time insights.

## 🔐 IAM Roles & Policies

To ensure secure access between services:

- **EC2 IAM Role**: Allows access to Amazon S3 for writing data
- **AWS Glue Role**: Grants permission to scan S3 and write to the Data Catalog
- **Athena Role/Policy**: Allows read access to S3 and Glue Data Catalog

All IAM roles are configured with the principle of least privilege, ensuring each service has access only to the resources it requires.

## 📈 Example Use Cases

- Track and visualize live stock activity from streaming data
- Run time-based queries (e.g., total trades in last 10 minutes)
- Perform aggregation and filtering (e.g., top traded stocks by volume)

## 🧪 Setup Guide

1. **Launch EC2 Instance**  
   Install and configure Apache Kafka + Python

2. **Run the Kafka Producer**  
   Use `KafkaProducer.py` to stream stock data from CSV to the Kafka topic

3. **Run the Kafka Consumer**  
   Use `KafkaConsumer.py` to consume data from the topic and write to an S3 bucket

4. **Create and Configure AWS Glue**  
   - Set up a Glue Crawler to scan the S3 path
   - Run the crawler to populate the Glue Data Catalog

5. **Query with Athena**  
   - Use SQL in the Athena console to explore and analyze the streamed stock data

## Credits

Followed the YouTube project by **Darshil Parmar (Data Engineer)**  
📺 [Video Link](https://www.youtube.com/embed/KerNf0NANMo)

Architecture diagram created by Darshil Parmar.

---

## 📬 Contact

**Krutik Panchal**  
📧 krutikpanchal44@gmail.com 
🔗 [LinkedIn]((https://www.linkedin.com/in/krutik-panchal4/)) • 🧠 MS in Data Science @ RIT




