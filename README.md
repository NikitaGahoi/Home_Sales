# Home_Sales

## Overview
The analysis employs PySpark and Spark SQL in Google Colab to extract key metrics from home sales data. The objectives include creating temporary views, partitioning data, caching and uncaching a temporary table, and answering specific questions regarding average home prices under various conditions.

## Data Source
The data was sourced from a CSV file stored on an AWS S3 bucket. Utilizing PySpark, a Spark session was created, and the data was read into a dataframe. The dataset includes essential columns such as ID, date, date_built, price, bedrooms, bathrooms, sqft_living, sqft_lot, floors, and waterfront.

## Data Analysis and Findings

### SQL Queries and Results

-1. **What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.**
  
![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/d02b3296-3b30-4b8c-954a-f74aaad2e695)

-2. **What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? Round off your answer to two decimal places.**

![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/ec6989b8-b991-4e2b-825e-2b9a87535ce2)

-3. **What is the average price of a home for each year built that have 3 bedrooms, 3 bathrooms, with two floors, and are greater than or equal to 2,000 square feet rounded to two decimal places?** 

 ![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/632f0e88-8cf5-4ff1-9326-8dd085cb45f1)

 -4. **What is the "view" rating for the average price of a home, rounded to two decimal places, where the homes are greater than
 or equal to $350,000?** The same question has to be aswered using the original, cached data and parquet formatted data and the run time for the each query was detetmined

 **Original Data**

 ![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/fef64bdd-eb10-4636-94f7-13adc6f3b70d)

 **Cached Data**

 ![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/78f33abe-7465-47e2-9171-d76bb10fccab)

 **Parquet Formatted Data** : For the Parquet format the data was partitioned by the "date_built" field

 ![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/f183ff81-c1fe-4032-aaef-4708ff3465f2)

 ## Results

The runtime results clearly indicate that both cached data **(0.489 seconds)** and Parquet-formatted data **(0.616 seconds)** exhibit faster processing times compared to the original dataset **(1.058 seconds)**. This acceleration can be attributed to the optimizations derived from caching and utilizing the Parquet data format.

Caching, as implemented in your code, involves storing the data in memory. Querying the cached data allows for direct retrieval from memory, eliminating the need to read data from the disk.

Parquet, designed as a columnar storage format for efficient data processing, boasts advantages over traditional row-based formats like CSV or JSON. Its organization of data into columns facilitates column pruning and predicate pushdown, enabling queries to skip irrelevant columns and partitions during execution.

Ideally the paruquet format should have shown the most effiecient run-time has the data been partioned by views or the house-price. Since the data was patrition by the year the houses were built, the query had to run on all the partitions to find the matches and therefore it took greater time **(0.616 seconds)** than the cache data **(0.489 seconds)**.

## Conclusion

In summary, this analysis provides a comprehensive exploration of key metrics in home sales data using PySpark and Spark SQL. Through insightful SQL queries, visualizations, and runtime comparisons, the report demonstrates the impact of various data processing techniques on performance. The findings underscore the significance of optimized storage formats, particularly Parquet, for efficient data processing in real-world scenarios.

 



  




