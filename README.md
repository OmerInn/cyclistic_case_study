# 🚲 **Cyclistic Case Study: How Does a Bike-Share Navigate Speedy Success?**

## 📌 **Project Introduction**

This project is a comprehensive end-to-end data analysis case study focused on understanding **user behavior** in a bike-sharing system and supporting **data-driven decision making** for business growth.

The subject of analysis is **Cyclistic**, a fictional bike-share company based in Chicago that offers bike rentals through two customer types:  
- **Casual riders** (single-use or occasional users)  
- **Annual members** (subscribed users)

The main objective is to identify how ride patterns differ between these two groups and to uncover opportunities to **convert casual riders into annual members** — thereby increasing customer retention and long-term revenue.

To answer the central business question, I analyzed **12 months of trip data** (over 5 million records) using:
- **Google Sheets** for early-stage data exploration
- **SQL (BigQuery)** for large-scale data cleaning and summarization
- **R (RStudio)** for in-depth analysis, visualization, and reporting

This study applies the full **six-step data analysis process** defined in the *Google Data Analytics Certificate*, including defining the business task, preparing and cleaning the data, conducting exploratory and descriptive analysis, visualizing key trends, and formulating strategic recommendations.

The project showcases how a well-structured analytical workflow using multiple tools can help businesses make informed, actionable decisions.


---

## 🔍 **Case Methodology (Google Data Analytics Process)**

This project follows the **6-step Google Data Analytics process**:

| Phase      | Description                                                      | Folder                  |
| ---------- | ---------------------------------------------------------------- | ----------------------- |
| 🔍 **Ask**     | Define business objective and identify stakeholders              | [`/ask`](./ask)         |
| 📦 **Prepare** | Locate, assess, and verify data sources and integrity            | [`/prepare`](./prepare) |
| 🧹 **Process** | Clean, format, and transform data for analysis                   | [`/process`](./process) |
| 📊 **Analyze** | Conduct descriptive analysis and identify trends and differences | [`/analyze`](./analyze) |
| 🔣 **Share**   | Present key findings with visualizations for stakeholders        | [`/share`](./share)     |
| ✅ **Act**      | Recommend data-informed business strategies                      | [`/act`](./act)         |

---
## 📁 Phase-by-Phase Folder Details

### 🔍 `/ask`
> Defines the business task and key questions guiding the analysis.

📄 `business_task.md` – Clearly states the problem and goal of the project  
📄 `stakeholders.md` – Identifies who will benefit from the analysis  
📄 `guiding_questions.md` – Lists the key questions that shape the analytical approach

### 📦 Prepare
> Describes the source, structure, and integrity of the dataset used.

📄 `data_overview.md` – Explains where the data came from and how it’s structured  
📄 `integrity_check.md` – Validates data quality, privacy, and ROCCC compliance  
📁 `raw_data/` – Contains downloaded original CSV files

### 🧹 Process
> Cleans and prepares the dataset for accurate analysis and visualization.

- 📄 `data_cleaning_google_sheets.md` – Step-by-step documentation of cleaning and transformation tasks done in Google Sheets, including formulas used and screenshots of the process.  
- 📁 `screenshots/` – Contains visual references for calculated columns like `ride_length` and `day_of_week`.


## 🧰 **Tools Used**

- **Google Sheets** – Initial data cleaning and calculations  
- **SQL (BigQuery)** – Filtering, grouping, and transforming data  
- **R / RStudio** – Advanced analysis and data visualizations (with `ggplot2`)  
- **GitHub** – Version control and documentation  

---

## 📁 **Folder Structure**

```plaintext
cyclistic_case_study/
├── ask/
    ├── business_task.md
    ├── stakeholders.md
    └── guiding_questions.md
├── prepare/
├── raw_data/
│   ├── Divvy_Trips_2019_Q1.csv
│   └── Divvy_Trips_2020_Q1.csv
├── data_overview.md
└── integrity_check.md
├── process/
    ├── data_cleaning_google_sheets.md
    └── screenshots/
        ├── ride_length_2019.png
        ├── ride_length_2020.png
        ├── day_of_week_2019.png
        └── day_of_week_2020.png
├── analyze/
│   ├── visualizations/
│   ├── summary_stats.csv
├── share/
│   ├── final_report.pdf
│   └── slides/
├── act/
│   ├── recommendations.md
│   ├── business_actions.md
│   └── final_conclusion.md
└── README.md
