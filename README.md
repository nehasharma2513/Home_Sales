# Home_Sales

In this project, we are using SparkSQL to determine key metrics about home sales data. We are also using Spark to create temporary views, partition the data, cache and uncache a temporary table, and verify that the table has been uncached.

Following steps have been performed :

1. Import the necessary PySpark SQL functions for this assignment.
2. Read the home_sales_revised.csv data in the starter code into a Spark DataFrame.
3. Create a temporary table called home_sales.
4. Answer the following questions using SparkSQL:
5. What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.
6. What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? Round off your answer to two decimal places.
7. What is the average price of a home for each year that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? Round off your answer to two decimal places.
8. What is the "view" rating for homes costing more than or equal to $350,000? Determine the run time for this query, and round off your answer to two decimal places.
9. Cache your temporary table home_sales.
10. Check if your temporary table is cached.
11. Using the cached data, run the query that filters out the view ratings with an average price of greater than or equal to $350,000. _Determine the runtime and compare it to uncached runtime._
    **The runtime decreases from 0.8665130138397217 seconds to 0.5367162227630615 seconds**
    **Caching**: PySpark cache() method is used to cache the intermediate results of the transformation into memory so that any future transformations on the results of cached transformation improve the performance. Caching is a lazy evaluation meaning it will not cache the results until you call the action operation and the result of the transformation is one of the optimization tricks to improve the performance of the long-running PySpark applications/jobs
12. Partition by the "date_built" field on the formatted parquet home sales data.
13. Create a temporary table for the parquet data.
14. Run the query that filters the view ratings with an average price of greater than or equal to $350,000. _Determine the runtime and compare it to uncached runtime._
    **The runtime is 1.0306816101074219 seconds**
    **Parquet**: Apache Parquet file is a columnar storage format available to any project in the Hadoop ecosystem, regardless of the choice of data processing framework, data model, or programming language.While querying columnar storage, it skips the nonrelevant data very quickly, making faster query execution. As a result aggregation queries consume less time compared to row-oriented databases.
    Pyspark SQL provides support for both reading and writing Parquet files that automatically capture the schema of the original data, It also reduces data storage by 75% on average. Pyspark by default supports Parquet in its library hence we don’t need to add any dependency libraries.
15. Uncache the home_sales temporary table.
16. Verify that the home_sales temporary table is uncached using PySpark.

References:
https://sparkbyexamples.com/pyspark/pyspark-cache-explained/
https://sparkbyexamples.com/pyspark/pyspark-read-and-write-parquet-file/
