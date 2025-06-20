# 📋 Cyclistic SQL Insights – 2019 & 2020 Summary Findings

This document summarizes the key findings from the SQL analysis of Cyclistic bike-share data from Q1 2019 and Q1 2020. These insights will help guide strategic business decisions focused on converting casual riders into annual members.

---

## 📍 1. Dataset Overview

| Year  | Total Rides | Unique Ride IDs | First Ride           | Last Ride            |
|-------|-------------|------------------|----------------------|----------------------|
| 2019  | 365,069     | 365,069          | 2019-01-01 00:04:37  | 2019-06-17 16:04:35  |
| 2020  | 426,884     | 426,884          | 2020-01-01 00:04:44  | 2020-05-19 20:10:34  |

📌 *Both datasets are complete and consistently structured for comparison.*

---

## ⏱ 2. Ride Duration Summary

| Year  | Minimum Duration | Maximum Duration | Average Duration (sec) | Approx. Average (min) |
|-------|------------------|------------------|--------------------------|------------------------|
| 2019  | 00:00:35         | 23:57:54         | 786.9 seconds            | ~13.1 minutes          |
| 2020  | 00:00:01         | 23:59:59         | 912.4 seconds            | ~15.2 minutes          |

📝 *Zero-duration rides were excluded from the 2020 dataset to ensure accurate averages.*

---

## 📊 3. Weekly Ride Patterns by User Type

### 🗓 2019 Observations:
- **Casual Riders:** Longer ride durations on weekends (~2,000–2,400 sec).
- **Members:** Short, consistent ride durations across weekdays (~660–790 sec).

### 🗓 2020 Observations:
- **Casual Riders:** Ride durations increased further (~2,100–3,100 sec), peaking on Thursdays.
- **Members:** Continued steady behavior (~660–820 sec) regardless of the day.

📌 *Casual users exhibit leisure-based usage patterns. Members show signs of regular commuting.*

---

## 🧠 Insights

- There is a **clear behavioral difference** between casual and member riders.
- Casual riders tend to use the service **on weekends or for longer, less frequent trips**.
- Annual members consistently ride **on weekdays with shorter durations**, suggesting daily use (e.g., commuting).

---

## 📈 Business Implications

1. **🛍 Offer promotions** targeting casual riders on weekends to encourage conversion to membership.
2. **📢 Emphasize time-saving and convenience** in marketing campaigns for commuters.
3. **🎯 Segment campaigns** based on ride behavior (e.g., long weekend rides vs. short weekday rides).
4. **📊 Continue monitoring usage trends** over seasons to identify further optimization opportunities.

---

## 📂 Source Files & References

- [2019_summary.md](../2019_summary.md)  
- [2020_summary.md](../2020_summary.md)  
- SQL Tables:
  - `cyclistic_case.divvy_trips_2019_Q1`
  - `cyclistic_case.divvy_trips_2020_Q1`
  - `cyclistic_case.ride_trends_2019`
  - `cyclistic_case.ride_trends_2020`

---

📌 *This summary connects directly with the original business question:  
“How do annual members and casual riders use Cyclistic bikes differently?”*

🎯 These findings support targeted marketing strategies and product design decisions aimed at increasing membership conversions.
