# Global Power Plant Capacity & Energy Mix Analysis

An end-to-end data analytics project analyzing ~35,000 power plants worldwide 
to understand global renewable vs. fossil fuel capacity trends, using the 
Global Power Plant Database (World Resources Institute).

## Business Questions
1. Which countries have grown renewable capacity fastest since 2010?
2. What % of each country's total capacity is renewable vs. fossil?
3. Which countries carry the oldest power plant infrastructure by fuel type?

## Tech Stack
- **Python (Pandas)** — data cleaning, feature engineering
- **PostgreSQL / SQL** — aggregation and analysis queries
- **Tableau Public** — interactive dashboard
- **GitHub** — version control & documentation

## Process
1. **Data Cleaning (Python)** — Loaded the raw dataset (36 columns, ~35K rows), 
   trimmed to 8 relevant columns, and engineered a new `fuel_category` field 
   (Renewable / Fossil / Other) via a manual fuel-type mapping. Identified and 
   resolved 2 unmapped fuel categories (Waste, Storage) during cleaning.
2. **SQL Analysis (PostgreSQL)** — Loaded the cleaned data into a PostgreSQL 
   database via SQLAlchemy and wrote aggregation queries to answer each 
   business question (GROUP BY, CASE WHEN, type casting, HAVING filters).
3. **Dashboard (Tableau Public)** — Built an interactive dashboard combining 
   a geographic map (plant location, sized by capacity, colored by fuel type) 
   and a ranked bar chart of the top 15 countries by capacity and fuel mix.

## Key Findings
- The US and China lead global capacity additions since 2010, though plant-count 
  disparities suggest possible underreporting of smaller facilities in some countries' data.
- Paraguay, Switzerland, and Norway operate near-100% renewable grids, largely 
  hydro-driven; France's high renewable share is nuclear-inclusive (classified 
  as low-carbon for this analysis).
- Fossil and renewable infrastructure show a narrower average-age gap (27.9 vs. 
  26.2 years) than commonly assumed — though based on the ~50% of plants with 
  known commissioning years.
- Switzerland and France carry the oldest average infrastructure (73.7 and 68.4 
  years), largely long-lived hydro assets.

## Dashboard
🔗 [View the live interactive dashboard](https://public.tableau.com/app/profile/trupti.kotian/viz/GlobalPowerPlantCapacityEnergyMix/Dashboard1)

## Data Source
[Global Power Plant Database](https://github.com/wri/global-power-plant-database) — World Resources Institute
