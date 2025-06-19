# 🗂 Data Overview – Prepare Phase

This project uses **Cyclistic’s historical trip data**, made publicly available by Motivate International Inc. under an open data license. Although Cyclistic is a fictional company, the data is real and suitable for educational and analytical purposes.

## 📁 Source Format

- Data is downloaded in **CSV format**
- Each file represents a different quarter or year segment
- Sample files used:
  - `Divvy_Trips_2019_Q1.csv`
  - `Divvy_Trips_2020_Q1.csv`

## 🧱 Main Columns

| Column Name        					 | Description                              |
|----------------------------------------|------------------------------------------|
| ride_id / trip_id  					 | Unique ID per trip                       |
| bikeid / rideable_type   			  	 | Bicycle type identifier                  |
| started_at / start_time                | Trip start timestamp                     |
| ended_at / end_time       			 | Trip end timestamp                       |
| from_station_name / start_station_name | Trip start station                       |
| to_station_name / end_station_name     | Trip end station    						|
| member_casual / usertype               | Rider type (casual or member) 			|

## 💡 Note

The 2019 dataset contains `tripduration`, `gender`, and `birthyear`, which are not available in the 2020 dataset. These were excluded from the unified dataset to ensure structural consistency.
