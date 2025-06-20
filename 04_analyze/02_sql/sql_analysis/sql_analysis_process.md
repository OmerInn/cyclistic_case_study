# 🧠 SQL-Based Analysis Overview – Cyclistic Case Study

In this phase of the Cyclistic bike-share case study, SQL (Google BigQuery) was used to explore, clean, and analyze millions of ride records from Q1 2019 and Q1 2020.

The purpose of this SQL-based analysis is to:
- Understand the structure and size of the dataset.
- Create summary statistics for ride durations.
- Identify usage patterns across weekdays and user types (casual vs. member).
- Prepare unified datasets for cross-year comparison and visualization.

By using SQL, we ensured:
- Scalable processing of large datasets.
- Fast aggregation and transformation operations.
- Clean, queryable data for downstream reporting and business recommendations.

This analysis directly supports the main business question:
> **How do annual members and casual riders use Cyclistic bikes differently?**

All queries, outputs, and visual screenshots used during this phase are documented in this section.



## Step 1 – Explore Your Data

To understand the size and coverage of each dataset, we ran the following query:

```
SELECT 
  COUNT(*) AS total_rows,
  COUNT(DISTINCT ride_id) AS unique_rides,
  MIN(started_at) AS first_ride,
  MAX(ended_at) AS last_ride
FROM `cyclistic_case.divvy_trips_2019_Q1`;
```
![Explore 2019 Dataset](./screenshots/Explore_your_data_2019.png)  
📝 *Total row count, unique ride IDs, and time range for Q1 2019.*
```
SELECT 
  COUNT(*) AS total_rows,
  COUNT(DISTINCT ride_id) AS unique_rides,
  MIN(started_at) AS first_ride,
  MAX(ended_at) AS last_ride
FROM `cyclistic_case.divvy_trips_2020_Q1`;
```
![Explore 2020 Dataset](./screenshots/Explore_your_data_2020.png)  
📝 *Total row count, unique ride IDs, and time range for Q1 2020.*


## Step 2 – Create Summary Statistics
To compute the minimum, maximum, and average ride durations for 2019:
```
SELECT 
  MIN(ride_length) AS min_duration,
  MAX(ride_length) AS max_duration,
  AVG(EXTRACT(HOUR FROM ride_length) * 3600 +
      EXTRACT(MINUTE FROM ride_length) * 60 +
      EXTRACT(SECOND FROM ride_length)) AS avg_duration_seconds
FROM `cyclistic_case.divvy_trips_2019_Q1`;
```
![Summary Statistics 2019](./screenshots/create_summary_statistics_2019.png)  
📝 *Minimum, maximum, and average ride duration for Q1 2019.*

For 2020 (with invalid ride lengths excluded):
```
SELECT 
  MIN(ride_length) AS min_duration,
  MAX(ride_length) AS max_duration,
  AVG(EXTRACT(HOUR FROM ride_length) * 3600 +
      EXTRACT(MINUTE FROM ride_length) * 60 +
      EXTRACT(SECOND FROM ride_length)) AS avg_duration_seconds
FROM `cyclistic_case.divvy_trips_2020_Q1`
WHERE ride_length != TIME '00:00:00';
```
![Summary Statistics 2020](./screenshots/create_summary_statistics_2020.png)  
📝 *Minimum, maximum, and average ride duration for Q1 2020. Records with 0 duration were excluded.*

## Step 3 – Combine Datasets for Cross-Year Analysis
To support comparison across years, both datasets were combined with matching schema using UNION ALL:

```
CREATE OR REPLACE TABLE `cyclistic_case.divvy_2019_2020_combined` AS

SELECT
  CAST(ride_id AS STRING) AS ride_id,
  NULL AS rideable_type,
  started_at,
  ended_at,
  from_station_name AS start_station_name,
  from_station_id AS start_station_id,
  to_station_name AS end_station_name,
  to_station_id AS end_station_id,
  NULL AS start_lat,
  NULL AS start_lng,
  NULL AS end_lat,
  NULL AS end_lng,
  member_casual,
  ride_length,
  day_of_week
FROM `cyclistic_case.divvy_trips_2019_Q1`

UNION ALL

SELECT
  ride_id,
  rideable_type,
  started_at,
  ended_at,
  start_station_name,
  start_station_id,
  end_station_name,
  end_station_id,
  start_lat,
  start_lng,
  end_lat,
  end_lng,
  member_casual,
  ride_length,
  day_of_week
FROM `cyclistic_case.divvy_trips_2020_Q1`;
```
![Join Tables for Combined Analysis](./screenshots/use_join_if_neccessary_2019.png)  
📝 *Combining 2019 and 2020 data using UNION ALL into a single clean schema.*

## Step 4 – Investigate Interesting Trends
To analyze user behavior by day and membership type for 2019:

```
CREATE OR REPLACE TABLE `cyclistic_case.ride_trends_2019` AS
SELECT 
  member_casual,
  day_of_week,
  AVG(EXTRACT(HOUR FROM ride_length) * 3600 +
      EXTRACT(MINUTE FROM ride_length) * 60 +
      EXTRACT(SECOND FROM ride_length)) AS avg_duration_seconds
FROM `cyclistic_case.divvy_trips_2019_Q1`
GROUP BY member_casual, day_of_week;
```
![Create Ride Trends Table (2019)](./screenshots/Investigate_interesting_trends_create_table_2019.png)  
📝 *SQL query to create trend table summarizing average ride duration by day and user type (2019).*

![Ride Trends 2019](./screenshots/Investigate_trends_2019.png)  
📝 *Aggregated ride duration by membership type and day of week (Q1 2019).*


For 2020:

```
CREATE OR REPLACE TABLE `cyclistic_case.ride_trends_2020` AS
SELECT 
  member_casual,
  day_of_week,
  AVG(EXTRACT(HOUR FROM ride_length) * 3600 +
      EXTRACT(MINUTE FROM ride_length) * 60 +
      EXTRACT(SECOND FROM ride_length)) AS avg_duration_seconds
FROM `cyclistic_case.divvy_trips_2020_Q1`
GROUP BY member_casual, day_of_week;
```

![Ride Trends 2020](./screenshots/Investigate_trends_2020.png)  
📝 *Aggregated ride duration by membership type and day of week (Q1 2020).*

