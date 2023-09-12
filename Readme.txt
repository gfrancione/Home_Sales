Help came from Stack Overflow

#Also, ask tutor about this.

AnalysisException                         Traceback (most recent call last)
<ipython-input-29-e861923e2c74> in <cell line: 22>()
     20 """
     21 
---> 22 uncached_result = spark.sql(uncached_query)
     23 
     24 # Show the result (optional)

2 frames
/content/spark-3.4.0-bin-hadoop3/python/pyspark/errors/exceptions/captured.py in deco(*a, **kw)
    173                 # Hide where the exception came from that shows a non-Pythonic
    174                 # JVM exception message.
--> 175                 raise converted from None
    176             else:
    177                 raise

AnalysisException: [UNRESOLVED_COLUMN.WITH_SUGGESTION] A column or function parameter with name `ROUND` cannot be resolved. Did you mean one of the following? [`parquet_data`.`id`, `parquet_data`.`date`, `parquet_data`.`view`, `parquet_data`.`price`, `parquet_data`.`floors`].; line 4 pos 4;
'Aggregate [view#1184], [view#1184, 'ROUND, named_struct(col1, avg(Price#1177), col2, 2) AS AveragePrice#1580]
+- Filter (Price#1177 >= 350000)
   +- SubqueryAlias parquet_data
      +- View (`parquet_data`, [id#1175,date#1176,price#1177,bedrooms#1178,bathrooms#1179,sqft_living#1180,sqft_lot#1181,floors#1182,waterfront#1183,view#1184,date_built#1185])
         +- Relation [id#1175,date#1176,price#1177,bedrooms#1178,bathrooms#1179,sqft_living#1180,sqft_lot#1181,floors#1182,waterfront#1183,view#1184,date_built#1185] parquet


Before You Begin
Create a new repository for this project called, Home_Sales. Do not add this homework to an existing repository.

Clone the new repository to your computer.

Push your changes to GitHub.

Files
Download the following files to help you get started:

Module 22 Challenge filesLinks to an external site.

Instructions
Rename the Home_Sales_starter_code.ipynb file as Home_Sales.ipynb.

Import the necessary PySpark SQL functions for this assignment.

Read the home_sales_revised.csv data in the starter code into a Spark DataFrame.

Create a temporary table called home_sales.

Answer the following questions using SparkSQL:

What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.

What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? Round off your answer to two decimal places.

What is the average price of a home for each year that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? Round off your answer to two decimal places.

What is the "view" rating for homes costing more than or equal to $350,000? Determine the run time for this query, and round off your answer to two decimal places.

Cache your temporary table home_sales.

Check if your temporary table is cached.

Using the cached data, run the query that filters out the view ratings with an average price of greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.

Partition by the "date_built" field on the formatted parquet home sales data.

Create a temporary table for the parquet data.

Run the query that filters out the view ratings with an average price of greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.

Uncache the home_sales temporary table.
Readme file

Verify that the home_sales temporary table is uncached using PySpark.

Download your Home_Sales.ipynb file and upload it into your "Home_Sales" GitHub repository.

Support and Resources
Your instructional team will provide support during classes and office hours. You will also have access to learning assistants and tutors to help you with topics as needed. Make sure to take advantage of these resources as you collaborate with your partner on this project.

Requirements
A Spark DataFrame is created from the dataset. (5 points)

A temporary table of the original DataFrame is created. (10 points)

A query is written that returns the average price, rounded to two decimal places, for a four-bedroom house that was sold in each year. (5 points)

A query is written that returns the average price, rounded to two decimal places, of a home that has three bedrooms and three bathrooms. (5 points)

A query is written that returns the average price of a home with three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet for each year built rounded to two decimal places. (5 points)

A query is written that returns the view rating for the average price for homes that are greater than or equal to $350,000, rounded to two decimal places. (The output shows the run time for this query.) (10 points)

A cache of the temporary "home_sales" table is created and validated. (10 points)

The query from step 6 is run on the cached temporary table, and the run time is computed. (10 points)

A partition of the home sales dataset by the "date_built" field is created, and the formatted parquet data is read. (10 points)

A temporary table of the parquet data is created. (10 points)

The query from step 6 is run on the parquet temporary table, and the run time is computed. (10 points)

The "home_sales" temporary table is uncached and verified. (10 points)