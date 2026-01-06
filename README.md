# Shop-easy-Data-analysis

Project Structure
data_analysis_by_sql.sql: SQL scripts used to clean, transform, and extract data from the database.

sentiment_analysis.py: A Python script that fetches review data, calculates sentiment scores, and categorizes reviews.

Dashboard.pbix: A Power BI dashboard file used to visualize the processed data.

ecommerge_database.bak: The backup file for the SQL Server database used in this project.

README.md: Project documentation.

Key Features
1. Data Cleaning & Transformation (SQL)
The data_analysis_by_sql.sql file handles the preparation of several key datasets:

Customers: Enriches customer data by joining it with geographic information (Country, City).

Products: Categorizes products into price segments ('Low', 'Medium', 'High') for segmentation analysis.

Reviews: Standardizes review text by removing unnecessary double spaces.

Customer Journey:

Identifies and removes duplicate journey records using Common Table Expressions (CTEs) and window functions (ROW_NUMBER).

Standardizes stages to uppercase.

Handles missing duration values by calculating the average duration for the specific visit date.

2. Sentiment Analysis (Python)
The sentiment_analysis.py script performs advanced text analysis on customer reviews:

Data Fetching: Connects directly to the SQL Server database (PortfolioProject_MarketingAnalytics) using pyodbc to retrieve review data.

Sentiment Scoring: Uses the NLTK VADER library to calculate a compound sentiment score for each review.

Advanced Categorization: Categorizes sentiment into groups (e.g., 'Positive', 'Mixed Negative', 'Neutral') by combining both the text sentiment score and the numerical customer rating.

Bucketing: Groups sentiment scores into specific ranges (e.g., '0.5 to 1.0') for easier analysis.

Export: Saves the enriched data to fact_customer_reviews_with_sentiment.csv.

Getting Started
Prerequisites
SQL Server: To restore the .bak file and run queries.

Python 3.x: For running the sentiment analysis script.

Power BI Desktop: To view the dashboard.

Python Dependencies
Install the required libraries using pip:

Bash

pip install pandas nltk pyodbc sqlalchemy
Setup Instructions
Database Setup: Restore the ecommerge_database.bak file to your SQL Server instance.

Data Cleaning: Run the scripts in data_analysis_by_sql.sql to create the necessary views or clean tables.

Run Sentiment Analysis:

Update the connection string in sentiment_analysis.py to match your server details (currently set to ALI-LT2024\SQLEXPRESS).

Run the script:

Bash

python sentiment_analysis.py
This will generate a CSV file with sentiment insights.

Visualization: Open Dashboard.pbix in Power BI and refresh the data sources to see the latest analysis.
