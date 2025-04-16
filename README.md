🔐 AI-Based Intrusion Detection System (IDS)
🧩 Problem Statement
In today’s digital era, safeguarding network infrastructure is paramount. Organizations are under constant threat from malicious activities such as unauthorized access, DDoS attacks, brute-force attempts, and data breaches. The core challenge is to analyze massive volumes of network traffic logs in near real-time to detect anomalies and known attack patterns efficiently.

📊 Dataset Overview
The project utilizes a rich and structured network traffic dataset with the following fields:

Source Port

Destination Port

Packet Length

Malware Indicators

Anomaly Scores

Attack Type

Action Taken

This dataset offers a multidimensional view of network traffic, combining basic packet metadata with security analytics features, making it highly suitable for real-time threat detection.

🎯 Project Goals
Classification

Label each network request as normal or suspicious.

Leverage Malware Indicators and Anomaly Scores for rule-based or ML-based classification.

Risk Identification

Identify high-risk IP addresses by aggregating suspicious activity.

Filter and report IPs crossing predefined risk thresholds.

Scalable Storage

Store flagged IPs and threat metadata in a scalable database (e.g., HBase) for further forensic analysis and rapid response.

⚙️ Proposed Solution
1. 🔄 Data Ingestion
Source: Logs ingested from a distributed file system (e.g., HDFS).

Preprocessing: Cleaning, type conversion (e.g., numeric parsing for Packet Length, Anomaly Scores).

2. 🚀 Data Processing
🔍 Classification
Rule-Based Detection:
E.g., If Malware Indicator ≠ null or Anomaly Score > threshold, mark as suspicious.

Optional ML Models:
Use features like Protocol, Packet Type, Traffic Type to train classification models for enhanced detection.

📊 Aggregation
Group records by Source IP Address.

Count suspicious events per IP.

Apply a threshold filter to isolate high-risk IPs.

3. 💾 Output & Storage
Generate a detailed report of high-risk IPs and their associated threat metadata.

Store the results in HBase for:

Historical audits

Real-time threat dashboards

Integration with incident response tools

⚡ Execution Time Comparison

Framework	Dataset Size	Execution Time	Notes
Hadoop (MapReduce)	1 GB	~10 minutes	Disk-based, best for batch processing
Apache Spark	1 GB	~2 minutes	In-memory processing, ideal for real-time detection
✅ Conclusion
Hadoop (MapReduce)
✓ Reliable for large-scale batch processing
✗ Slower, not ideal for real-time scenarios

Apache Spark
✓ Efficient for real-time threat detection
✓ Supports iterative ML and streaming analytics
✓ Optimized for interactive security monitoring

🛠️ Technologies Used
Apache Hadoop (MapReduce)

Apache Spark

HDFS

HBase

Python / PySpark

Pandas, NumPy, Matplotlib

Jupyter / Google Colab / VS Code

📌 Future Enhancements
Integrate real-time stream processing (e.g., Spark Streaming / Kafka)

Implement deep learning models (LSTM, Autoencoders) for anomaly detection

Add a visualization dashboard (e.g., with Streamlit or Power BI)

Enable automated alerts and incident ticket creation
