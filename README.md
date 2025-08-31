# ♟ Chess Games Analysis Dashboard (Power BI)

## 📊 Project Overview
An end-to-end Power BI project analyzing **20,000+ chess games** from [Lichess Chess Dataset on Kaggle](https://www.kaggle.com/datasets/datasnaek/chess?resource=download).  
The goal: demonstrate complete workflow — **ETL, star schema modeling, DAX, and interactive dashboards** — as a fresher/entry-level showcase.

---

## 📂 Dataset
- **Source:** Kaggle — [Chess Game Dataset (Lichess)](https://www.kaggle.com/datasets/datasnaek/chess?resource=download)  
- **Scope:** ~20k games with players, ratings, outcome, turns, opening (ECO/name/ply), time control, rated/unrated, timestamps.

---

## 🔧 ETL & Data Modeling
- **ETL in Power Query**: deduplicated game IDs, standardized datatypes, split datetime into usable fields.  
- **Star Schema Model**:  
  - **FactGames** – game-level facts (id, ratings, turns, outcome, time control, MatchStarted, opening_eco, etc.)  
  - **DimDate** – calendar (date, year, quarter, month, day, hour)  
  - **DimOpening** – ECO code, opening name, ply, ply bucket  
  - **DimPlayers_White / DimPlayers_Black** – player IDs & ratings  
- Organized measures into a dedicated **_Measures table** with folders.  
- Hidden technical keys (IDs, surrogate keys, ECO codes) for a clean field list.  

---

## 📐 DAX Highlights
- Created **22 measures** across different themes (Core, Outcomes, Ratings, Time, Trends, Quality, etc.).  
- Core: `[Games]`, `[White Wins]`, `[Black Wins]`, `[Draws]`, `[Win %]`, `[Avg Turns]`, `[Avg Rating]`  
- Time Intelligence: `[Games MTD]`, `[Games YTD]`, `[Games YoY %]`, `[7-Day Rolling Games]`  
- Tooltip micro-trend: `[Games Last 30 Days]`  

---

## 📊 Report Pages

### 1) **01 – Overview**
- KPI Cards: Games, Win %, Player Overall Win %, Avg Turns  
- **Line & Column Chart**: Games per year vs. 7-day rolling average  
- **Clustered Column**: Outcomes (White / Black / Draws) by month  
- **Metric Selector**: Field Parameters toggle (Win %, Avg Rating Diff, Avg Turns, Games)  
- Left-hand **Slicer Panel**: Date range, Rated/Unrated, Opening Ply Bucket, with a Reset button  

### 2) **TT-Info (Custom Tooltip Page)**
- Canvas sized as Tooltip  
- Compact KPI Cards: Games MTD, Games YTD  
- Designed for hover — shows monthly/yearly context at a glance  
- Attached to charts on Overview  

### 3) **DT – Game Details (Drill-through Page)**
- Drill-through enabled (Keep All Filters = On)  
- KPI Cards: Games, Player Overall Win %, Avg Turns, Avg Rating Diff  
- Detailed **Table**: game id, opening name, time control, rated flag, player ratings, outcome, date parts  
- Back button for navigation  

---

## 🎨 Features Demonstrated
- Custom **tooltips** (TT-Info)  
- **Slicers + Reset** with bookmarks  
- **Metric Selector** (field parameters)  
- **Drill-through navigation** (DT-Game Details)  
- Consistent color theme (White=Blue, Black=Orange, Draw=Gray)  

---

## 🧰 Skills Demonstrated
- Power Query ETL  
- Star schema data modeling  
- DAX (22 measures: aggregations, time intelligence, rolling windows)  
- Power BI interactivity: slicers, bookmarks, drill-through, tooltips, parameters  
- Dashboard storytelling & design polish  

---

## 📸 Screenshots
- Overview Page  
  <img width="1519" height="797" alt="Screenshot 2025-09-01 020802" src="https://github.com/user-attachments/assets/354e43ca-3a05-414a-b95b-4d40b9725e9d" />

- Tooltip Page (TT-Info)  
  <img width="435" height="327" alt="Screenshot 2025-09-01 020817" src="https://github.com/user-attachments/assets/69e8074b-db07-41df-bb8a-347815a6cdd3" />

- Drill-through Page (DT-Game Details)  
  <img width="1491" height="794" alt="Screenshot 2025-09-01 020832" src="https://github.com/user-attachments/assets/1a75477b-17f7-4c3a-8a47-fbc751b50954" />

---

## ▶️ How to Run
1. Open `.pbix` in Power BI Desktop.  
2. Dataset: `games.csv` included (update source path if needed).  

---
