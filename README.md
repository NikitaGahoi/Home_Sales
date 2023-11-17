# Home_Sales

## Overview
The analysis employs PySpark and Spark SQL in Google Colab to extract key metrics from home sales data. The objectives include creating temporary views, partitioning data, caching and uncaching a temporary table, and answering specific questions regarding average home prices under various conditions.

## Data Source
The data was sourced from a CSV file stored on an AWS S3 bucket. Utilizing PySpark, a Spark session was created, and the data was read into a dataframe. The dataset includes essential columns such as ID, date, date_built, price, bedrooms, bathrooms, sqft_living, sqft_lot, floors, and waterfront.

## Data Analysis and Findings

### SQL Queries and Results

  -1. **Average Price for Four-Bedroom Houses Each Year:**
    python ```
    spark.sql("""
    SELECT
      YEAR(date),
      ROUND(AVG(price), 2),
    FROM home_sales
    WHERE bedrooms = 4
    GROUP BY YEAR
    ORDER BY YEAR DESC
    """).show() ```



