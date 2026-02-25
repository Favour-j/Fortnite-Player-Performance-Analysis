# Fortnite Player Performance Analysis

[![Tableau](https://img.shields.io/badge/Tableau-Public-orange?style=flat&logo=tableau)](https://public.tableau.com/app/profile/favour.jokparose/viz/FortnitePlayersPerformance/Dashboard1?publish=yes)
[![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat&logo=python)](./Fortnite%20python%20script.ipynb)

## 📌 Project Overview
This project provides a deep dive into Fortnite player telemetry to understand the drivers behind player retention and gaming performance. By leveraging a **Python** cleaning pipeline and an interactive **Tableau** dashboard, this analysis identifies trends across different platforms, regions, and game modes.

> [!IMPORTANT]
> **Data Disclaimer:** The dataset used in this project is **AI-generated** for analytical and demonstration purposes. It simulates real-world gaming telemetry but does not represent actual player data from Epic Games.

## 📊 Dashboard Preview
![Fortnite Dashboard Preview](./dashboard_preview.png)
*View the interactive dashboard here: [Fortnite Performance Dashboard](https://public.tableau.com/app/profile/favour.jokparose/viz/FortnitePlayersPerformance/Dashboard1?publish=yes)*

## 🛠️ Tech Stack
* **Data Cleaning:** Python (Pandas, NumPy)
* **Visualization:** Tableau Public
* **Environment:** Jupyter Notebook

## 🧹 Data Cleaning & Engineering
The raw data (`fortnite_100.csv`) contained significant noise and formatting inconsistencies. The cleaning process in the [Jupyter Notebook](./Fortnite%20python%20script.ipynb) included:

* **Platform Standardization:** Unified varied entries (e.g., "pc", "PLAYSTATION", "Mobile") into a single standardized Title Case format.
* **Boolean Normalization:** Resolved the `Retention` columns which contained mixed inputs like "T/F", "True/False", and whitespace into consistent boolean values.
* **Metric Engineering:** Created a custom **Win Rate (%)** feature to measure player skill accurately:
  $$Win\ Rate = \left( \frac{Lifetime\ Wins}{Total\ Matches} \right) \times 100$$
* **Handling Missing Values:** Imputed missing `Lifetime_Wins` using the median and converted `Avg_Session_Duration_Min` to numeric to handle empty logs.

## 📈 Business Insights Summary
This analysis translates technical data into actionable insights for game management:

* **Retention Churn Points:** Identified a significant drop-off between 7-day and 30-day retention, highlighting a critical window for re-engagement strategies like daily login rewards.
* **Platform Engagement:** Discovered variances in session duration across Mobile vs. PC, helping prioritize performance patches for the most engaged platforms.
* **Regional Hotspots:** Mapped regional activity (NA-East, EU) to assist in server load distribution and regional marketing focus.
* **Economy Health:** Analyzed the correlation between **In-Game Currency** holdings and win rates to identify the spending potential of different player tiers.

## 📂 Repository Structure
```bash
├── data/
│   ├── fortnite_100.csv            # Raw AI-generated dataset
│   └── fortnite_100_cleaned.csv    # Final dataset used for visualization
├── Fortnite python script.ipynb    # Python cleaning pipeline (Pandas)
├── dashboard_preview.png           # Dashboard screenshot
└── README.md                       # Project documentation
