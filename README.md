# NYC Yellow Taxi Trip Analysis (2025)

Exploratory data analysis of New York City's 2025 Yellow Taxi trip data using **Databricks and PySpark**.

---

## Project Overview

This project analyzes approximately **48.2 million taxi trips** to identify demand patterns, temporal trends, and frequently travelled routes across New York City.

The analysis uses distributed data processing to work with a large real-world dataset and extract meaningful insights into taxi trip activity.

## Technologies

| Technology | Purpose |
|---|---|
| Databricks | Data processing and analysis environment |
| PySpark | Data cleaning, transformation, and aggregation |
| Python | Supporting data processing |

## Data Preparation

The original dataset was filtered to include trips from 2025. Records with missing pickup or drop-off timestamps, as well as trips with invalid timestamp ordering, were excluded.

**Final dataset:** 48,176,269 trips

NYC Taxi Zone lookup data was incorporated to translate location IDs into recognizable neighbourhood and borough names.

## Analysis

The project focuses on four key areas:

### 1. Monthly Trip Distribution
Examines how taxi trip volume changes throughout the year to identify monthly demand patterns.

### 2. Trips by Day of the Week
Compares trip volumes across the seven days of the week to identify differences in weekday and weekend demand.

### 3. Hourly Trip Distribution
Analyzes pickup activity by hour to identify the busiest and least busy times of day.

### 4. Most Frequent Routes
Identifies the three most frequently travelled pickup-to-drop-off routes, using NYC taxi zone and borough names for
