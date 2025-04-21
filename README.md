# 🚦 Chicago Traffic Crash Analysis

This project analyzes over 2 million records of traffic crashes in Chicago using a full modern data pipeline. It involves data ingestion from Azure Blob Storage, preprocessing and transformation with PySpark on Databricks, warehousing in Snowflake, and final data visualization in Tableau.

---

## 📌 Objective

To uncover patterns and key insights from Chicago's traffic crash data, aiding city planners, safety departments, and policymakers in identifying high-risk scenarios and optimizing interventions.
1. **Analyze Traffic Crash Data**: Identify key factors (e.g., weather, lighting) contributing to crashes.
2. **Examine People Involved in Crashes**: Understand demographics and injury severity.
3. **Generate Insights**: Help improve traffic safety measures.
4. **Create a Dashboard**: Visualize trends and insights.

---

## **Dataset**

### 1. **Traffic Crash Data**:
- **Source**: City of Chicago Open Data Portal
- **Details**: Traffic crash records reported within Chicago.
- **Records**: 837K+

### 2. **People Involved in Crashes**:
- **Source**: City of Chicago Open Data Portal
- **Details**: Demographic information and injury severity for individuals involved in crashes.
- **Records**: 1M+

### **Combined Dataset**:
- **Total Rows**: 2M+
- **Columns**: 48
---

## 🧰 Tools & Technologies

- **Azure Blob Storage** – Raw data storage
- **Databricks Community Edition** – Data cleaning and transformation (PySpark)
- **Snowflake** – Cloud data warehouse for scalable querying
- **Tableau** – Interactive dashboards for visual insights
- **SQL & PySpark** – For EDA, data manipulation, and aggregation

---

## 🛠️ Pipeline Overview

![Blank diagram - Page 2 (1)](https://github.com/user-attachments/assets/81fe081c-f379-47ea-b96c-c8f8ca1a9c99)


1. **🔹 Azure Blob Storage**
   - Uploaded raw CSVs: `Traffic_Crashes_-_Crashes.csv` and `Traffic_Crashes_-_People.csv`
   - 📦 Azure Storage Structure
      ```
      Azure Resource Group
      └── Storage Account: chicagotrafficanalysis
          └── Container: traffic-data
              └── Files:
                  ├── Traffic_Crashes_-_Crashes_20240623.csv
                  └── Traffic_Crashes_-_People_20240624.csv
      ```

2. **🔹 Databricks (PySpark)**
   - Connected to Azure Blob via access key
   - Cleaned data: removed duplicates, casted datatypes, handled nulls
   - Lowercased column names, joined datasets on `crash_record_id`
   - Performed column normalization and schema enforcement

3. **🔹 Snowflake**
   - Uploaded the cleaned dataset from Databricks to Snowflake
   - Created a warehouse, database, schema, and target table
   - Queried Snowflake from Databricks using `spark.read.format("snowflake")`

4. **🔹 Tableau**
   - Connected to Snowflake (and extracted data)
   - Built dashboard showing:
     - Crash trends by month, time of day, and lighting conditions
     - Distribution by gender, injury severity, and crash type
     - Primary causes with grouped “Other” category
     - Interactive KPI cards and maps

---

## **Key Insights**
1. **Traffic Control Devices**: Areas with no traffic controls have the highest crash rates.
2. **Weather**: Most crashes occur under clear weather conditions, with significant risks in rain and snow.
3. **Lighting Conditions**: Daylight and lighted roads at night are where most crashes occur.
4. **Primary Causes**: Failure to yield right-of-way and tailgating are common causes.
5. **Crash Severity**: Most crashes result in no injuries, though a small portion leads to severe injuries or fatalities.
6. **Crash Hotspots**: Certain locations in Chicago have a higher concentration of crashes.
7. **69.5%** of crashes resulted in *no injury or drive away*

---

## **Dashboard Preview**

An interactive dashboard was created to visualize key findings, including crash patterns, injury severity, weather effects, and geographical hotspots.

**[Access the Dashboard here](https://public.tableau.com/views/ChicogoTrafficCrashAnalysis/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

---

## 📊 Dashboard Preview

> <img width="993" alt="Screenshot 2025-04-19 at 4 12 52 PM" src="https://github.com/user-attachments/assets/afdd3c05-f91a-4070-9c38-ddbc530db621" />


---

## 🧪 Analysis Performed

- Time-based analysis (hour, day, month)
- Injury classification distribution
- Gender distribution of individuals involved
- Mapping of top crash locations
- Driver behavior patterns (e.g., cellphone use, vision obstruction)

---

## 🛡️ Data Integrity & Governance

- **Schema validation** using `StructType` in PySpark
- **Normalization** of categorical values (e.g., grouping weather types)
- **Explicit type casting** for timestamp, coordinates, and integers
- **Duplicate removal** and null handling
- **Secure access** to Azure Storage via `dbutils.widgets` and Databricks secrets (optional)

---

## **Conclusion**

This project successfully identified key insights into traffic safety in Chicago using big data tools like Databricks and Delta Lake. The interactive dashboard makes the data accessible for decision-makers and the public, aiding in the improvement of road safety.

---

## **References**
- City of Chicago Data Portal: [Traffic Crashes](https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if/about_data)
- City of Chicago Data Portal: [People Involved in Crashes](https://data.cityofchicago.org/Transportation/Traffic-Crashes-People/u6pd-qa9d/about_data)

## 📌 Notes
- Data processing was performed on **Databricks Community Edition**
- Dashboard created using **Tableau Public (Extracted Mode)** so it remains accessible after Snowflake trial expiration


