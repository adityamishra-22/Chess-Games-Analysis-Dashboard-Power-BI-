# ♟ Chess Games Analysis Dashboard (Power BI)

## 📊 Project Overview  
An end-to-end **Power BI analytics project** analyzing **20,000+ chess games** from the **Lichess Chess Dataset** on Kaggle.  

The goal: demonstrate a complete BI workflow — **ETL**, **star schema modeling**, **30+ DAX measures**, and **interactive dashboards** with storytelling polish — as a **fresher/entry-level showcase**.

---

## 📂 Dataset  

- **Source:** [Kaggle – Lichess Chess Dataset](https://www.kaggle.com/)  
- **Scope:** ~20k games with metadata:  
  - Players & ratings  
  - Game outcome (White/Black/Draw)  
  - Turns  
  - Opening (ECO code, name, ply)  
  - Time control  
  - Rated/Unrated  
  - Timestamps  

---

## 🔧 ETL & Data Modeling  

- **ETL in Power Query**  
  - Deduplicated game IDs  
  - Standardized datatypes  
  - Split datetime into usable fields  

- **Star Schema Model**  

  **FactGames** – game-level facts (id, ratings, turns, outcome, time control, MatchStarted, opening_eco, etc.)  
  **DimDate** – calendar (date, year, quarter, month, day, hour)  
  **DimOpening** – ECO code, opening name, ply, ply bucket  
  **DimPlayers_White / DimPlayers_Black** – player IDs & ratings  

- Organized measures into a dedicated **_Measures** table with folders:  
  - Core  
  - Outcomes  
  - Ratings  
  - Time  
  - Trends  
  - Openings  
  - Title  
  - Player Role  
  - Keep  

- Hidden technical keys (IDs, surrogate keys, ECO codes) → **clean field list**

---

## 📐 DAX Highlights  

30+ measures created across different themes:

- **Core**: `[Games]`, `[White Wins]`, `[Black Wins]`, `[Draws]`, `[Win %]`, `[Avg Turns]`  
- **Time Intelligence**: `[Games MTD]`, `[Games YTD]`, `[Games YoY %]`, `[7-Day Rolling Games]`, `[Games Last 30 Days]`  
- **Ratings**: `[Avg White Rating]`, `[Avg Black Rating]`, `[Avg Rating Diff (White – Black)]`  
- **Openings**: `[Most Played Opening Name]`, `[Most Played Opening Games]`, `[Top Opening Win %]`  
- **Dynamic Titles / Summary**: `[Treemap Title]`, `[Bar Title]`, `[Game Details Summary]`  

---

## 📊 Report Pages  

### 1️⃣ Overview  
- **KPI Cards**: Games, Player Overall Win %, White Win %, Black Win %, Avg Turns  
- **Line Chart**: Games per year vs. 7-day rolling average  
- **100% Stacked Column**: White vs Black win % by month  
- **Clustered Column**: Games by TimeControl  
- **Donut**: Games by Rated/Unrated  
- **Left-hand Slicer Panel**: Date range, Rated/Unrated, Opening Ply Bucket  

---

### 2️⃣ Players & Ratings  
- **KPI Cards**: Avg Rating Diff, Games YTD, Games YoY %  
- **Scatter**: Rating Diff vs Win %  
- **Clustered Bar**: Rated vs Unrated Win %  
- **Line (sparkline)**: Games Played (Last 30 Days)  

---

### 3️⃣ Openings Lab  
- **KPI Cards**: Avg Opening Ply, Most Played Opening (name + games)  
- **Treemap**: Top 10 openings by games played (ECO → Name)  
- **Horizontal Bar**: Top 5 openings by Average Turns  
- **Drillthrough Enabled → Game Details**  

---

### 4️⃣ Game Details (Drill-through Page)  
- **Dynamic Summary Banner**:  
  Example →  
  *“Sicilian Defense — 1,284 games | White 47.8% · Black 49.3% · Draws 2.9% | Avg Turns 54 | Rating Δ 7.3 | Rated | Blitz”*  

- **Detailed Table**: game id, opening name, time control, player ratings, winner, date parts  
- **Back button for navigation**  

---

## 🎨 Features Demonstrated  

- Dynamic Titles (Year, Rated flag, Ply Bucket)  
- Drill-through navigation with summary annotation banner  
- Sidebar Navigation (icons + slicers)  
- Consistent color theme (White=Blue, Black=Orange, Draw=Gray)  
- Design polish: ≤4 visuals per page, KPI rows on summary pages, white cards, dark sidebar  

---

## 🧰 Skills Demonstrated  

- Power Query **ETL**  
- **Star schema** data modeling  
- **DAX** (30+ measures: aggregations, time intelligence, dynamic text, rolling windows)  
- Power BI **interactivity**: slicers, bookmarks, drill-through, parameters  
- Dashboard **storytelling & design polish**  

---

## 📸 Screenshots  

### Overview Page  
<img width="1107" height="614" alt="Screenshot 2025-09-07 123627" src="https://github.com/user-attachments/assets/f62f2700-3923-4e33-9a11-123357c90358" />
 

### Players & Ratings Page  
<img width="1132" height="620" alt="Screenshot 2025-09-07 110631" src="https://github.com/user-attachments/assets/05cb52e0-d11e-47b8-bb87-f2e7bfa7849a" />

### Openings Lab Page  
<img width="1132" height="621" alt="Screenshot 2025-09-07 110653" src="https://github.com/user-attachments/assets/b287ab4a-d870-4108-9f60-0653f99aaf41" />
 

### Game Details Page  
<img width="1102" height="631" alt="image" src="https://github.com/user-attachments/assets/abbc340e-19dc-4d7f-b4ce-e5af8fb38376" />


---

## ▶️ How to Run  

1. Open `.pbix` in **Power BI Desktop**  
2. Dataset: `games.csv` included (update source path if needed)  

---
