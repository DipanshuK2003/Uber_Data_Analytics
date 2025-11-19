# Uber Data Analytics

## Project Overview
This project demonstrates an end-to-end data engineering and analytics pipeline built using Python (ETL), BigQuery (Data Modeling), and Tableau (BI Dashboard).
Raw Uber trip data is cleaned, transformed, and organized into a STAR schema, then merged into an analytics table (`tbl_analytics`) for BI reporting.
The final Tableau dashboard provides interactive insights into trip volume, revenue, passenger trends, payment behaviors, and vendor performance.

## Tech Stack

- Python: ETL, data cleaning, preprocessing

- BigQuery: Data modeling, SQL transformations, analytics table

- Tableau: Final dashboard and KPIs

- Jupyter Notebook: ETL & modeling scripts

- GitHub: Project versioning

## Architecture

### Data Flow
<img width="800" alt="charts" src="https://github.com/DipanshuK2003/Uber_Data_Analytics/blob/main/assets/Flowchart.png">

### STAR Schema
<img width="800" alt="charts" src="https://github.com/DipanshuK2003/Uber_Data_Analytics/blob/main/assets/schema.png">

## Live Interactive Dashboard
**[View the full interactive dashboard on Tableau Public](https://public.tableau.com/app/profile/dipanshu.kumar1559/viz/UberDataAnalyticsDashboard_17634693643850/Dashboard?publish=yes)**

*Experience the complete functionality with filters, tooltips, and dynamic interactions.*

## Dashboard Preview

### Summary View
<img width="800" alt="charts" src="https://github.com/DipanshuK2003/Uber_Data_Analytics/blob/main/assets/Uber%20%7C%20Summary.png">

## Key KPIs
- **Total Trips**: 100,000 trips
- **Total Revenue**: $1.64 Million
- **Total Passengers**: 192.92K passengers transported
- **Average Fare**: $13.25 per trip
- **Average Trip Distance**: 3.03 miles

## Key Insights
- Credit card is preferred by 2 out of 3 riders, showing strong digital adoption.
- Curb Mobility overwhelmingly dominates the market by having 87.68% of total revenue.
- **Rate Code**:
    1. Standard Rate (Most common with 97,199 trips)
    2. JFK
    3. Negotiated Fare
    4. Newark
    5. Nassau or Westchester
    6. Group Ride (Least common with only 1 trip)
  
## ETL Process Summary

### Cleaning raw data
- Removed nulls / duplicates
- Standardized datetime formats
- Corrected geolocation values

### Creating dimension tables
- `datetime_dim`
- `passenger_count_dim`
- `trip_distance_dim`
- `rate_code_dim`
- `pickup_location_dim`
- `dropoff_location_dim`
- `payment_type_dim`

### Creating fact table
- Joined cleaned IDs & metrics
- Stored numeric transactional values

### BigQuery Modeling
The final analytics table `tbl_analytics` merges fact + all dimensions for BI consumption.

SQL file included here:
`bigquery_modeling.sql`

## How to Use
1. Download the raw CSV files:
Place them inside the same directory as `Uber Data Pipeline.ipynb`.

2. Run the ETL notebook:
Open `Uber Data Pipeline.ipynb` and run all cells.
This will:
    - Clean the raw data
    - Create fact and dimension tables
    - Export them as CSVs (the CSVs will be similar to the one in ETL Pipeline folder)

3. Upload the fact & dimension tables to BigQuery:
Create a BigQuery dataset and upload all the generated tables.

4. Run the BigQuery data modeling script:
Open `bigquery_modeling.sql`
    - Update the project ID, dataset name, and table paths as per your setup
    - Run the entire SQL to generate the final tbl_analytics table.

5. Open Tableau and connect it to BigQuery:
Choose your `tbl_analytics` table as the data source.

6. Load the Tableau Dashboard
Open `Uber Dashboard.twbx` to view the completed dashboard, or create your own using the analytics table.

---
*The Tableau workbook (.twbx) uses a live BigQuery connection, so if you want to run it locally, update the BigQuery project/dataset/table names accordingly.*

## Connect
[[LinkedIn](https://www.linkedin.com/in/dipanshu-kumar-61a21322a/)]
