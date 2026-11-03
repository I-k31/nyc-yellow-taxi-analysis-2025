# NYC Yellow Taxi Trip Analysis (2025)

Exploratory analysis of 48,176,269 NYC Yellow Taxi trips from 2025, built with Databricks, PySpark, and Spark SQL.

## Key Findings

- **Busiest month:** May (4,527,572 trips), about 30% higher than January (3,473,183), the quietest.
- **Busiest day of the week:** Saturday (7,456,947 trips), followed closely by Thursday (7,393,379). Monday is the quietest day (5,880,986), about 21% below Saturday.
- **Peak hour:** 6 PM, with 3,432,279 pickups. The quietest hour is 4 AM, with 358,620 pickups, so peak demand is roughly 9.6x the overnight low.
- **Busiest routes (excluding trips within a single zone):**
  1. Upper East Side South → Upper East Side North: 296,255 trips
  2. Upper East Side North → Upper East Side South: 253,994 trips
  3. Midtown Center → Upper East Side South: 140,734 trips

All three of the busiest routes are within Manhattan, and the top two are the same pair of zones in opposite directions.

## Overview

This project analyzes 2025 NYC Yellow Taxi trip data to explore demand patterns, identify peak travel periods, and determine the most frequently travelled pickup-to-drop-off routes. It demonstrates SQL-based data cleaning and aggregation on a dataset of roughly 48 million records, using Databricks and Apache Spark.

## Tech Stack

| Tool | Use |
|---|---|
| Databricks | Cloud-based environment for processing and analysis |
| PySpark | Loading datasets and registering temporary views |
| Spark SQL | Cleaning, validation, aggregation, and table joins |
| Python | Supporting data loading and integration |

## Data

- **Trips:** NYC Taxi & Limousine Commission Yellow Taxi Trip Records, filtered to 2025.
- **Zones:** NYC Taxi Zone Lookup, joined to convert location IDs into neighbourhood and borough names.

## Data Cleaning

Cleaning was performed in Spark SQL:

- Removed records with missing pickup or drop-off timestamps.
- Excluded trips where the drop-off timestamp was earlier than or equal to the pickup timestamp.
- Validated pickup and drop-off location IDs for missing values.

**Final dataset: 48,176,269 trips.**

## Results

### Monthly trip volume

| Month | Trips | Month | Trips |
|---|---|---|---|
| Jan | 3,473,183 | Jul | 3,842,907 |
| Feb | 3,572,378 | Aug | 3,526,247 |
| Mar | 4,122,949 | Sep | 4,193,840 |
| Apr | 3,935,799 | Oct | 4,360,740 |
| May | 4,527,572 | Nov | 4,119,312 |
| Jun | 4,254,366 | Dec | 4,246,976 |

### Trips by day of week

| Day | Trips |
|---|---|
| Sunday | 6,380,236 |
| Monday | 5,880,986 |
| Tuesday | 6,680,291 |
| Wednesday | 7,208,642 |
| Thursday | 7,393,379 |
| Friday | 7,175,788 |
| Saturday | 7,456,947 |

### Hourly pickups

Pickups fall to a low of 358,620 at 4 AM, climb through the morning, and build through the afternoon to a peak of 3,432,279 at 6 PM (hour 18). Volume stays high through the evening, with more than 2.7 million pickups per hour from 8 PM to 10 PM, and drops off after midnight. See the notebook for all 24 hours.

### Three busiest routes

| Pickup zone | Drop-off zone | Trips |
|---|---|---|
| Upper East Side South (Manhattan) | Upper East Side North (Manhattan) | 296,255 |
| Upper East Side North (Manhattan) | Upper East Side South (Manhattan) | 253,994 |
| Midtown Center (Manhattan) | Upper East Side South (Manhattan) | 140,734 |

Routes were ranked by trip count after excluding trips where the pickup and drop-off zone are the same, and joined to the zone lookup for readable names.

## Limitations

- Cleaning covers timestamps and location IDs only. Fare, distance, passenger count, and trip duration outliers were not filtered.
- The analysis is descriptive. It identifies patterns but does not model or explain them.
- Route rankings exclude same-zone trips and are based on trip count only, without accounting for distance or fare.

## Repository Contents

```
nyc-yellow-taxi-analysis-2025/
├── nyc_yellow_taxi_analysis_2025.ipynb
└── README.md
```

## Data Sources

- [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
- NYC Taxi Zone Lookup (TLC)
