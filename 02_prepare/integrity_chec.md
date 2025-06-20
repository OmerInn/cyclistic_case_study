# ✅ Data Integrity Check – Prepare Phase

Before proceeding with cleaning and analysis, basic integrity checks were performed on the raw data files.

## 🔍 Checks Performed

- ✅ **Header Consistency**: Confirmed presence of expected columns in both files.
- ✅ **Row Count Check**: No unexpected truncation or structural errors detected.
- ✅ **Encoding Check**: CSV files opened cleanly in both Google Sheets and RStudio.
- ✅ **Null & Missing Values**:
  - Minimal missing values in station fields (e.g., `start_station_name`)
  - No personal or sensitive information present (anonymized)

## 🚫 Issues Noted

- Different column naming conventions between 2019 and 2020 (resolved in Process phase)
- Some rows had `NULL` or empty `start_station_name` (flagged for removal)
- Negative durations found in raw data (to be handled in cleaning)

## 🔐 Privacy & Licensing

- ✅ No personal identifiers included
- ✅ Data licensed for public use by Motivate International Inc.
