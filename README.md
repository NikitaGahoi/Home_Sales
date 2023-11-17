# Home_Sales

## Overview
The analysis employs PySpark and Spark SQL in Google Colab to extract key metrics from home sales data. The objectives include creating temporary views, partitioning data, caching and uncaching a temporary table, and answering specific questions regarding average home prices under various conditions.

## Data Source
The data was sourced from a CSV file stored on an AWS S3 bucket. Utilizing PySpark, a Spark session was created, and the data was read into a dataframe. The dataset includes essential columns such as ID, date, date_built, price, bedrooms, bathrooms, sqft_living, sqft_lot, floors, and waterfront.

## Data Analysis and Findings

### SQL Queries and Results

  -1. **What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.**
  
    ![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/cb54a179-7171-45fc-bce7-467a8ba273eb)

  -2. **What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? Round off your answer to two decimal places.**

    ![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/7d350023-b495-4528-b71b-6c61d7e1427e)

  -3. **What is the average price of a home for each year built that have 3 bedrooms, 3 bathrooms, with two floors, and are greater than or equal to 2,000 square feet rounded to two decimal places?** 

    ![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/3d04f8a2-df40-4e6d-a30b-a5661e151ac2)

 -4. **What is the "view" rating for the average price of a home, rounded to two decimal places, where the homes are greater than
 or equal to $350,000?** The same question has to be aswered using the original, cached data and parquet formatted data and the run time for the each query was detetmined

 **Original Data**

 ![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/fef64bdd-eb10-4636-94f7-13adc6f3b70d)

 **Cached Data**

 ![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/78f33abe-7465-47e2-9171-d76bb10fccab)

 **Parquet Formatted Data** : For the Parquet format the data was partitioned by the "date_built" field

 ![image](https://github.com/NikitaGahoi/Home_Sales/assets/136101293/f183ff81-c1fe-4032-aaef-4708ff3465f2)



  




