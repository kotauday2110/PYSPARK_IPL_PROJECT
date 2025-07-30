
#  IPL Data Engineering and Analysis using PySpark

This project performs end-to-end data engineering and analytical processing on Indian Premier League (IPL) cricket datasets using **Apache Spark (PySpark)**. It demonstrates data loading, transformation, aggregation, and deriving meaningful cricket insights using distributed computing in Databricks.

---

##  Project Overview

This project explores IPL match data using **PySpark's DataFrame API and SQL capabilities**. We process raw CSV data into structured formats, perform transformations, and run analytical queries to answer performance-related questions for teams, players, and venues.

---

##  Technologies Used

* Apache Spark (PySpark)
* Databricks Community Edition
* Python
* Spark SQL
* Jupyter/Databricks Notebooks

---

##  Dataset Description

The project uses **5 CSV datasets**, each containing different dimensions of IPL data:

| Dataset Name       | Description                                                       |
| ------------------ | ----------------------------------------------------------------- |
| `match.csv`        | Match-level data (season, date, teams, winner, toss, venue, etc.) |
| `ball_by_ball.csv` | Delivery-level data for each ball of every match                  |
| `player.csv`       | Player metadata including player IDs and names                    |
| `team.csv`         | Team metadata including team IDs and names                        |
| `venue.csv`        | Stadium and venue-related metadata                                |

Each dataset is read into a Spark DataFrame using an explicitly defined schema to ensure type safety and performance.

---

## Key Analysis & Transformations

### Data Engineering Steps

* Created Spark session
* Defined custom schema for each CSV to avoid schema inference issues
* Handled nulls and missing values
* Created views to run Spark SQL queries
* Joined datasets on appropriate keys (e.g., match\_id, player\_id)

### Analysis Performed

#### 1. Match-Level Insights

* Number of matches per season
* Matches per city
* Toss winner vs match winner
* Most successful teams

#### 2. Batsman Performance

* Top batsmen by total runs
* Strike rate = (Total Runs / Balls Faced) × 100
* Consistency across seasons

#### 3. Bowler Performance

* Most wickets taken
* Economy Rate = (Runs Conceded / Overs Bowled)
* Best performing bowlers at death overs

#### 4. Team Analysis

* Win percentage
* Toss decision trends
* Team vs Team win matrix

#### 5. Venue Impact

* Venues with most matches played
* Teams with best win record at specific venues

---

## 🛠️ How to Run the Project

1. Upload all 5 CSV datasets to your Databricks file system or local Spark environment.
2. Open the notebook `IPL_DATA_ANALYSIS_SPARK.ipynb`.
3. Update the file paths if needed, for example:

   ```python
   spark.read.option("header", True).schema(ball_by_ball_schema).csv("/dbfs/FileStore/ball_by_ball.csv")
   ```
4. Run all cells to perform the analysis.

---

## Folder Structure

```
 IPL_Data_Analysis_Spark/
├── IPL_DATA_ANALYSIS_SPARK.ipynb     # Main notebook
├── match.csv                         # Match data
├── ball_by_ball.csv                  # Ball-by-ball data
├── player.csv                        # Player info
├── team.csv                          # Team info
├── venue.csv                         # Venue info
├── README.md                         # Project documentation

```
