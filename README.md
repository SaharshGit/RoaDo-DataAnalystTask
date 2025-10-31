# RoaDo-DataAnalystTask

NYC Taxi Data Analysis - Data Analyst Project

1. Project Objective

The objective is to demonstrate end-to-end data analysis skills: sourcing, cleaning, processing, analyzing, and deriving actionable business insights from a real-world dataset.

Business Domain: Transportation & Urban Logistics

Reasoning: This domain was chosen for its direct relevance to the transportation and logistics industry, providing a parallel analysis to a company like Roado.

2. Data Source

Dataset: NYC Taxi and Limousine Commission (TLC) Trip Record Data

Specifics: Yellow Taxi Trip Records for January 2025

Download Link: https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

Helper Data: NYC Taxi Zone Lookup Table (used to map LocationIDs to Boroughs and Neighborhoods).

3. Project Workflow & Methodology

The analysis was conducted in a single Python notebook, following a structured workflow:

Data Loading: The raw January 2024 Parquet file was loaded into a pandas DataFrame.

Data Cleaning & Preprocessing:

Handled Nulls: Investigated and handled systematic null values. Over 540,000 rows with missing data for passenger_count, RatecodeID, etc., were identified and removed.

Filtered Outliers: Removed illogical data points, including:

Trips with trip_distance of 0 or less.

Trips with passenger_count of 0.

Trips with unrealistic durations (less than 1 minute or greater than 24 hours).

Corrected Data Types: Converted columns like passenger_count and RatecodeID from float to int for logical consistency.

Feature Engineering: Created new columns to enable deeper analysis:

trip_duration: Calculated from pickup and dropoff timestamps.

pickup_hour: Extracted from the pickup timestamp.

pickup_day_of_week: Extracted from the pickup timestamp.

tip_percentage: Calculated for credit card payments to normalize tipping behavior.

speed_mph: Calculated from trip_distance and trip_duration.

Exploratory Data Analysis (EDA): Analyzed the clean data to identify patterns and uncover the key insights listed below.

Visualization: Used matplotlib and seaborn to create visualizations supporting each insight.

4. Key Business Insights

Here are the top 5 actionable insights derived from the analysis:

Insight 1: Demand Peaks Mid-Week, Not on Weekends.

Finding: Trip demand peaks on Thursday, not on Friday or Saturday. This suggests the business is heavily reliant on a professional/commuter cycle rather than just leisure travel.

Implication: Resource allocation (drivers, vehicles) should be maximized from Wednesday to Friday.

Insight 2: The Evening Rush (4 PM - 7 PM) is the Primary Revenue Window.

Finding: A pronounced and sustained trip-demand peak occurs in the evening.

Implication: This "golden window" is the ideal time to implement dynamic pricing and offer driver incentives to ensure maximum fleet availability.

Insight 3: A Dual Market Exists (High-Volume vs. High-Value).

Finding: The highest volume of trips originates in dense Manhattan neighborhoods. However, the highest average fare trips originate from airports (JFK, Newark, LaGuardia).

Implication: The business must serve two distinct markets: high-frequency, short-distance trips in the city and low-frequency, high-value trips to/from airports.

Insight 4: Tipping Culture is Standardized at 20%.

Finding: A histogram of tip percentages for credit card payments shows a massive convergence at the 20% mark.

Implication: Customer tipping is highly predictable and heavily influenced by in-cab payment prompts. This provides a stable, forecastable revenue stream.

Insight 5: Fare is a Function of Time, Not Just Distance.

Finding: A notable cluster of high-fare trips exists at near-zero distance.

Implication: This confirms that the time-based fare component is a critical revenue driver, protecting driver earnings and company revenue during heavy traffic congestion.

5. Repository Structure

├── data_cleaning&Analysis_scripts.ipynb     # Main Jupyter Notebook with all Python code for cleaning, analysis, and visualization.
├── Dataset Selection Document.pdf           # Deliverable 1: The Dataset Selection Document.
├── Analysis_Report.pdf                      # Deliverable 3: The final 2-page report summarizing the 5 key insights.
├──yellow_tripdata_2025-01.parquet           # Main dataset
├── taxi_zone_lookup.csv                     # Helper data used to map location IDs to names.
└── README.md                                # This file.


6. How to Run This Project

Clone the repository:

git clone 


Install the required libraries:

pip install pandas matplotlib seaborn pyarrow


Run the Jupyter Notebook:

Launch Jupyter Notebook: jupyter notebook

Open the data_cleaning&Analysis_scripts.ipynb file.

Run the cells from top to bottom.

## Note: Ensure the path to datasets are correct. You might need to change it according to the location you store data)

7. Tools Used

Language: Python

Libraries:

Pandas: For data manipulation and cleaning.

Matplotlib & Seaborn: For data visualization.

PyArrow: For loading the Parquet file.

Environment: Google Collab / Jupyter Notebook
