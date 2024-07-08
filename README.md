# HomeSales



## Data Querying

The data file used for this project has 11 unique columns of information regarding home sales: **id**, **date**, **date_built**, **price**, **bedrooms**, **bathrooms**, **sqft_living**, **sqft_lot**, **floors**, **waterfront**, and **view**. The information embedded within this csv file is read into a Spark DataFrame and is used to create a temporary table. This temporary table is used to answer a few questions using SparkSQL:

1. What is the average price for a four-bedroom house sold per year?

2. What is the average price of a home per year of house construction that has three bedrooms and three bathrooms?

3. What is the average price of a home per year of house construction that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2000 square feet?

4. What is the average price of a home per view rating that has an average home price that is greater than or equal to $350000?


## Run Time Comparisons

The run time for the fourth query is calculated using uncached data. Then, the run time for the fourth query is calculated after the data is cached. Lastly, the run time for the fourth query is calculated by partitioning the data based on the **date_built** column is parquet formatted data. The order of fastest to slowest run times are: partitioned (0.94 seconds), cached (0.99 seconds), and uncached (1.94 seconds). In other words, partitioning the data into parquet formatted data provides the fastest run time while uncached data has the slowest run time.   