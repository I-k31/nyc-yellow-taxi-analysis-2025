# NYC Yellow Taxi Trip Analysis (2025)

Exploratory data analysis of New York City's 2025 Yellow Taxi trip data using **Databricks, PySpark, and Spark SQL**.

---

## Project Overview

This project analyzes approximately **48.2 million NYC Yellow Taxi trips** to explore demand patterns, identify peak travel periods, and determine the most frequently travelled pickup-to-drop-off routes.

Using Databricks and Apache Spark, the project demonstrates large-scale data processing, SQL-based data cleaning, and exploratory data analysis.

## Technologies

| Technology | Purpose |
|---|---|
| Databricks | Cloud-based data processing and analysis environment |
| PySpark | Loading datasets and registering temporary views |
| Spark SQL | Data cleaning, validation, aggregation, and table joins |
| Python | Supporting data loading and integration |

## Data Preparation

The original dataset was filtered to include trips from 2025.

Data cleaning was performed using Spark SQL:
- Removed records with missing pickup or drop-off timestamps.
- Excluded trips where the drop-off timestamp was earlier than or equal to the pickup timestamp.
- Validated pickup and drop-off location IDs for missing values.

**Final dataset:** 48,176,269 trips.

NYC Taxi Zone lookup data was incorporated to translate location IDs into recognizable neighbourhood and borough names.

## Analysis

The project focuses on four key areas:

### 1. Monthly Trip Distribution
Analyzes monthly trip volumes to identify changes in demand throughout 2025.

### 2. Trips by Day of the Week
Compares trip volumes across the seven days of the week to identify differences in weekday and weekend activity.

### 3. Hourly Trip Distribution
Examines pickup activity across all 24 hours to identify the busiest and least busy pickup periods.

### 4. Three Busiest Taxi Routes
Identifies the three most frequently travelled pickup-to-drop-off routes using location IDs, with SQL joins to retrieve corresponding neighbourhood and borough names.

## Repository Contents

```text
nyc-yellow-taxi-analysis-2025/
│
├── nyc_yellow_taxi_analysis_2025.ipynb
└── README.md
```

## Data Sources

- **NYC Yellow Taxi Trip Records:** [NYC Taxi & Limousine Commission](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
- **Taxi Zone Lookup:** [NYC Taxi Zone Lookup](https://github.com/sebavasquezvillarroel/taxi_zone_lookup)

## Key Takeaways

This project demonstrates the use of distributed data processing and SQL to analyze a large real-world dataset. The findings provide insight into NYC taxi demand patterns across months, weekdays, and hours, as well as the city's most frequently travelled routes.
