# Vendor-Recommendation-System
The Vendor Recommendation System is a data-driven solution designed to optimize vendor selection by leveraging predictive modeling and big data technologies.This project predicts the most suitable vendor ID based on input parameters such as material codes, descriptions, and partner details. The system features a user-friendly web interface built with Streamlit, backed by a robust data processing pipeline using PySpark, Hadoop, and Apache Airflow for efficient workflow orchestration.
# Features
- Predictive Modeling: Utilizes machine learning algorithms (Logistic Regression, Random Forest, Naive Bayes, Decision Trees, and Multilayer Perceptron) to recommend vendor IDs.
- Web Interface: Streamlit-based portal for users to input parameters and receive real-time vendor recommendations.
- Data Pipeline: Handles large-scale data with PySpark for processing, Hadoop for distributed storage, and Airflow for workflow automation.
- Data Preprocessing: Includes handling missing values, duplicates, label encoding, hashing, feature scaling, and vectorization.
- Model Evaluation: Assesses model performance using accuracy metrics on test data.
- Scalability: Designed to process large datasets efficiently using distributed computing.
# Technologies Used
- Programming Language: Python
- Big Data Frameworks: PySpark, Apache Hadoop
- Workflow Orchestration: Apache Airflow
- Web Framework: Streamlit
- IDE: Visual Studio Code
- Machine Learning: Spark MLlib, scikit-learn (KNN)
- Data Storage: HDFS (Hadoop Distributed File System)
- Libraries: pandas, StringIndexer, VectorAssembler, StandardScaler, MinMaxScaler
# Prerequisites
To set up and run the project, ensure you have the following:
- Python 3.8 or higher
- Apache Spark (PySpark) installed
- Hadoop 3.x configured with HDFS
- Apache Airflow for workflow orchestration
- Streamlit for the web interface
- Visual Studio Code or any preferred IDE
- Java (for Hadoop and Spark compatibility)
- A machine with at least 8GB RAM, 4 CPU cores, and 50GB disk space
- Basic knowledge of Python, machine learning, and big data concepts
# Installation Instructions
- Set Up Hadoop and Spark:
  - Install and configure Hadoop (HDFS and YARN) following the official documentation.
  - Install Apache Spark and configure it to work with Hadoop. Download from spark.apache.org.
  - Set environment variables (HADOOP_HOME, SPARK_HOME, JAVA_HOME).
- Install Apache Airflow:
  - Install Airflow using pip install apache-airflow.
  - Initialize the Airflow database and configure DAGs for the project (refer to dags/ folder).
- Install Python Dependencies:
  - pip install streamlit pyspark pandas scikit-learn
  - Ensure the MSSQL JDBC driver (mssql-jdbc-12.2.0.jre8.jar) is available for Spark.
- Prepare Data:
  - Place the input CSV files (Steel.csv, Cement.csv) in the /TEST/ directory on HDFS.
  - Update file paths in Vendor_Recommendation_Steel_Data.py and Vendor_Recommendation_Cement_Data.py if necessary.
- Run the Streamlit Application:
  - streamlit run Vendor_Portal.py
  - Access the web interface at http://localhost:8501.
- Execute Airflow DAGs:
Start the Airflow scheduler and webserver:
  - airflow scheduler
  - airflow webserver -p 8080
  - Trigger the Vendor_Recommendation_Steel_Data and Vendor_Recommendation_Cement_Data DAGs via the Airflow UI.
# Usage
- Web Portal:
  - Open the Streamlit app in your browser.
  - Enter required fields (e.g., HPO_BA_CODE, DPO_Material_Code, MMAT_Material_Description, etc.).
  - Click "Predict MG_Partner_Id" to view the recommended vendor ID.
- Data Processing:
  - Run Vendor_Recommendation_Steel_Data.py or Vendor_Recommendation_Cement_Data.py to process data and train models.
  - Monitor workflows via the Airflow UI.
- Model Evaluation:
Check model accuracy printed in the console
# License
This project is licensed under the MIT License.
