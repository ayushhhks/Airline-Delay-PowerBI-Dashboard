# ✈️ Airline Delay Power BI Dashboard

An interactive minimalistic Power BI dashboard analyzing airline delay trends, delay causes, and carrier performance using MySQL and DAX.

## 📊 Dashboard Preview

![Dashboard Preview](dashboard-preview/dashboard1.png)

## 📊 Features
- Total Flights, Delayed Flights, Delay %
- Monthly delay trend analysis
- Delay cause distribution (Carrier, Weather, NAS, Security, Late Aircraft)
- Carrier performance comparison
- Dynamic filters (Carrier & Month)

## 📂 Dataset

**Source:** U.S. Bureau of Transportation Statistics (BTS)  
Website: https://www.transtats.bts.gov/OT_Delay/OT_DelayCause1.asp  

**Dataset Name:** Airline On-Time Performance – Delay Causes  
**Year Used:** 2024  
**Rows:** 22,609  
**Columns:** 21  

The dataset contains monthly airline arrival delay statistics categorized by:

- Carrier delays  
- Weather delays  
- NAS (National Airspace System) delays  
- Security delays  
- Late aircraft delays  

## 🛠 Data Import – MySQL

1. Downloaded the dataset as CSV from BTS.
2. Installed MySQL Server and MySQL Workbench.
3. Created a new database:
```sql
CREATE DATABASE airline_project;
USE airline_project;
```
4. Created the table airline_delay_cause with appropriate data types.
5. Used LOAD DATA INFILE to import the CSV file:
LOAD DATA INFILE 
'C:/ProgramData/MySQL/MySQL Server 8.0/Uploads/Airline_Delay_Cause.csv'
INTO TABLE airline_delay_cause
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS;
6. Cleaned empty values using NULLIF and TRIM functions during import

# 📊 How I Connected MySQL to Power BI
## 📊 Data Modeling & Visualization – Power BI

1. Opened Power BI Desktop.
2. Selected **Get Data → MySQL Database**.
3. Entered:
   - Server: localhost
   - Database: airline_project
4. Imported table `airline_delay_cause`.
5. Created DAX measures for KPIs:

- Total Flights  
- Total Delayed Flights  
- Delay %  
- Total Delay Minutes  

6. Built interactive dashboard with:

- Monthly Delay % Trend
- Carrier Delay Comparison
- Delay Cause Distribution
- Slicers for Carrier and Month

## 📈 Key Insights

- Late aircraft delay is the largest contributor to total delay minutes.
- Delay % peaks during mid-year months.
- Some carriers show consistently higher delay percentages.
- Weather contributes significantly but is not the dominant factor overall.

## 🧰 Tools Used

- MySQL 8.0
- MySQL Workbench
- Power BI Desktop
- DAX
- GitHub
---

Developed by Ayush Kumar Singh
