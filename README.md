Chicago Traffic Crash Analysis
ALY6110 | Data Management and Big Data
Group Beta:
Sanchi Gupta: gupta.sanch@northeastern.edu
Sankalp Biswal: biswal.s@northeastern.edu
Siddhant Viswanath: viswanath.si@northeastern.edu
Rhea John Thoppil: thoppil.r@northeastern.edu
Krutikkumar Patel: patel.krutikk@northeastern.edu
Project Overview
This project focuses on analyzing traffic crash data from the City of Chicago. The goal is to identify patterns and trends in crashes, provide insights into safety and congestion, and ultimately support decision-making for traffic authorities.

Dataset
1. Traffic Crash Data:
Source: City of Chicago Open Data Portal
Details: Traffic crash records reported within Chicago from September 2017 onwards.
Records: 837K+
2. People Involved in Crashes:
Source: City of Chicago Open Data Portal
Details: Demographic information and injury severity for individuals involved in crashes.
Records: 1M+
Combined Dataset:
Total Rows: 1.8M+
Columns: 48
Objectives
Analyze Traffic Crash Data: Identify key factors (e.g., weather, lighting) contributing to crashes.
Examine People Involved in Crashes: Understand demographics and injury severity.
Generate Insights: Help improve traffic safety measures.
Create a Dashboard: Visualize trends and insights.
Tools & Technologies
Databricks for data processing and analysis.
Azure Storage for data hosting.
Delta Lake for ACID transactions and efficient queries.
Apache Spark for distributed data processing.
SQL for querying large datasets.
Power BI for interactive dashboards.
Process
Step 1: Data Ingestion
Created an Azure Storage Account and uploaded crash data.
Ingested the data into Databricks for processing.
Step 2: Data Cleaning
Removed redundant columns and duplicates.
Converted data types for analysis.
Step 3: Data Integration
Merged traffic crash data and people involved using CRASH_ID.
Step 4: Delta Lake and Layers
Converted data into Delta format for batch and serving layers.
Step 5: Analysis
Conducted SQL-based analysis to:
Count crashes by traffic control device.
Analyze crashes under different weather conditions.
Identify patterns by lighting conditions, month, day of week, and more.
Key Insights
Traffic Control Devices: Areas with no traffic controls have the highest crash rates.
Weather: Most crashes occur under clear weather conditions, with significant risks in rain and snow.
Lighting Conditions: Daylight and lighted roads at night are where most crashes occur.
Primary Causes: Failure to yield right-of-way and tailgating are common causes.
Crash Severity: Most crashes result in no injuries, though a small portion leads to severe injuries or fatalities.
Crash Hotspots: Certain locations in Chicago have a higher concentration of crashes.
Dashboard
An interactive dashboard was created to visualize key findings, including crash patterns, injury severity, weather effects, and geographical hotspots.

Access the Dashboard here

Conclusion
This project successfully identified key insights into traffic safety in Chicago using big data tools like Databricks and Delta Lake. The interactive dashboard makes the data accessible for decision-makers and the public, aiding in the improvement of road safety.

References
City of Chicago Data Portal: Traffic Crashes
City of Chicago Data Portal: People Involved in Crashes
Codebasics: Cricket Data Analytics Project
Ymericson GitHub: Big Data Streets
