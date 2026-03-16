

🛒 RetailFlux: Walmart Supply & Demand Data Pipeline.

📝 Executive Summary
In the high-volume retail sector, seasonal demand and macroeconomic shifts (like inflation and unemployment) can create multi-million dollar swings in inventory costs. This project implements a robust ETL (Extract, Transform, Load) pipeline designed to ingest fragmented retail and economic data to identify high-revenue performance trends.


The "$10,000 High-Impact" Logic
To ensure the business makes decisions based on statistically significant revenue drivers, I implemented a $10,000 revenue floor for all weekly departmental sales.

The Problem: 
Small "long-tail" departments or fringe weeks with low sales create "noise" that skews monthly averages.

The Solution:
By filtering for weeks where Weekly_Sales > 10000, the pipeline isolates the core revenue engines of the business.

Business Value: 
This allows supply chain managers to focus on high-velocity inventory needs, optimizing stock levels where the financial risk is highest.

🛠️ Tech Stack & Tools
Language:
Python (Pandas, NumPy)

Data Sources: 
PostgreSQL (Transactional Data), Parquet (Macroeconomic & Metadata)

Orchestration:
Modular Python functions for automated processing.

Development: 
DataCamp DataLab & GitHub Copilot for code optimization.

🏗️ The Pipeline Workflow
The pipeline follows a strict three-stage architecture to ensure data integrity and reproducibility.

1. Extraction
Ingested weekly transactional records from a PostgreSQL database.

Merged complementary environmental data (CPI, Fuel Prices, Temperature) from Parquet files to provide context to sales fluctuations.

2. Transformation
Date Engineering: Converted temporal data into monthly buckets to align with standard retail reporting cycles.

Quality Control: Handled missing values (NaNs) in economic indicators to prevent skewed correlations.

Thresholding: Applied the $10,000 revenue filter to isolate primary sales drivers.

3. Loading & Aggregation
Calculated Avg_Sales per month to identify peak demand seasons (e.g., Super Bowl, Labour Day, Christmas).

Exported high-integrity datasets (clean_data.csv and agg_data.csv) for use in BI tools like Power BI or Tableau.

📈 Key Business Insights
Peak Identification: The pipeline identified that sales peaks are highly correlated with specific holiday weeks, allowing for proactive labor and inventory scaling.

Macro Correlation: By including CPI and Unemployment data, the pipeline provides a foundation for analyzing how consumer spending power affects retail demand in real-time.

🚀 How to Run
Clone the repo:

Bash
git clone https://github.com/Wickliffo/retailflux-pipeline.git
Install dependencies:

Bash
pip install pandas pyarrow
Run the pipeline:
Open the Jupyter Notebook or run the script to generate the clean_data.csv and agg_data.csv files.

🎯 About the Author
I am wickliff orina aspiring Data Engineer currently completing the DataCamp Python Data Engineer Associate track. I focus on building scalable, business-centric data solutions that turn raw infrastructure into actionable intelligence.
