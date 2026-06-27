# Maven Market Global Sales Performance Dashboard

<img width="1229" height="664" alt="image" src="https://github.com/user-attachments/assets/8ba611fe-18af-49a1-8893-7381376182ad" />



An end-to-end business intelligence solution engineered in Power BI Desktop to analyze global retail operations. This project transforms raw transaction, return, and regional data into an executive-level interactive dashboard tracking $1.76M in total revenue and monitoring operational profit margins across global locations. 

## 📊 Business Context & Insights
Maven Market operates an international retail network with complex supply chain and sales funnels. This analytics solution was designed to bridge raw data with executive decision-making, delivering clarity on top-performing product brands, regional growth trends, and return vulnerabilities.

### Key Business Dimensions Analyzed:
* **Topline Performance:** Tracks global sales across 269,720 transactions, securing a high-performing overall profit margin of 59.67%.
* **Operational Control:** Monitors product return health (8,289 items returned) with an overall Return Rate of 0.99%, successfully identifying localized anomalies.
* **Geospatial & Trend Analysis:** Breaks down weekly revenue trajectories throughout 1998, enabling regional managers to pinpoint specific market milestones (e.g., Portland hitting 1,000 sales in December).
* **Growth Tracking:** Establishes dynamic monthly Revenue Targets based on a 5% baseline lift over previous-month performance to evaluate current market expansion.

---

## 🛠️ Technical Workflow & Architecture

### 1. Extract, Transform, Load (ETL) & Power Query
* **Data Integration:** Connected, cleaned, and promoted schema headers across 7 distinct files, including an automated directory ingestion strategy to append multiple historical transaction years.
* **Feature Engineering:** Merged text strings to construct custom attributes, isolated conditional logic flags to segment demographic variables, and processed string extractions while handling structural missing data.

### 2. Relational Data Modeling
* **Schema Design:** Implemented a robust **Snowflake Schema** optimization by structural grouping: lookup tables positioned symmetrically above data fact tables.
* **Relationship Integrity:** Maintained explicit **1-to-Many (*)** cardinality with unidirectional filter flow downstream from dimensions to facts to eliminate ambiguity.
* **Advanced Integrity:** Formulated active/inactive path architectures between the `Transaction_Data` and `Calendar` tables to smoothly process dual temporal anchors.

### 3. DAX Calculations & Metrics
* **Calculated Columns:** Engineered complex row-level contexts including current demographic age ranges, weekend flags, and text extractions utilizing string searching algorithms.
* **Calculated Measures:** Authored a robust metric matrix, utilizing **Iterators (`SUMX`)** for dynamic row-by-row computations and **Time Intelligence** for Year-to-Date (YTD) Revenue, 60-day rolling averages, and Month-over-Month (MoM) calculations.

### 4. Interactive Data Visualization
* **Topline Matrix:** Constructed an interactive matrix prioritizing the top 30 product brands, utilizing multi-tier conditional formatting.
* **Strategic KPI Blocks:** Designed high-visibility KPI indicator blocks tracking Monthly Volume, Net Profit, and Returns directly against shifting trailing targets.
* **Geospatial & Drill-Downs:** Created geographic distribution tracking connected directly to hierarchical Treemaps, unlocking flawless parent-child drill navigation from Country -> State -> City.
* **User Experience Engineering:** Programmed customized visual isolation switches alongside interactive button bookmarks linking deep-dive localized analytical notes back to executive summaries.
