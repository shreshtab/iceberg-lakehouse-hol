# Load Data into Iceberg Table Using Spark DataFrame

## Overview

This submodule provides a guide for loading data into an Iceberg table using Spark DataFrames within a Cloudera Data Engineering (CDE) session. By leveraging Spark DataFrames, you'll experience the power of multi-function analytics and see how Iceberg ensures consistency and handles concurrent writes from multiple services.

## Prerequisites

Before starting, ensure you have:

- Access to a Cloudera Data Engineering (CDE) session.
- Proper permissions to execute Spark commands.
- Your `${prefix}` (e.g., your User ID) ready for use in the code.

## Step-by-Step Guide

### Step 1: Set Up Variables

Begin by setting up your environment variables. Replace `<prefix>` with your unique value (e.g., your User ID).

``` python
from pyspark.sql.functions import col

# Variables - replace <prefix> with your user id
prefix = "<prefix>"
csv_database_name = prefix + "_airlines_csv"
odl_database_name = prefix + "_airlines"
```

### Step 2: Load and Filter Data Using Spark DataFrame

Use Spark DataFrames to load data from a CSV file into your Iceberg table. This example demonstrates loading two years of data (2005 and 2006) from the `flights_csv` table into the `flights` Iceberg table.

``` python
# INSERT 2 YEARS OF DATA INTO FLIGHTS TABLE
spark_df = spark.read.table(f"{csv_database_name}.flights_csv").where(col("year").isin([2005, 2006]))
```

### Step 3: Insert Data into the Iceberg Table

With the filtered data in your Spark DataFrame, insert it into the `flights` Iceberg table.

``` python
# INSERT THE DATA INTO FLIGHTS TABLE
spark_df.writeTo(f"{odl_database_name}.flights").using("iceberg").append()
```

### Step 4: Verify the Data Load

After the data load is complete, execute the following command to verify that the data has been correctly inserted into the Iceberg table. This command counts the number of flights for each year and orders the results in descending order.

``` python
# CHECK RESULTS
spark.read.table(f"{odl_database_name}.flights").groupBy(col("year")).count().orderBy(col("year"), ascending=False).show()
```

### Value Proposition

This submodule demonstrates the versatility of Iceberg, showing how it can handle concurrent writes from multiple services while maintaining consistency. By mastering data loading with Spark DataFrames, you'll be better equipped to manage and analyze large datasets in a distributed environment.

### Summary

You have successfully loaded data into an Iceberg table using Spark DataFrames in a CDE session. The data is now stored in a scalable, performant format that supports advanced Iceberg features like time travel, schema evolution, and partition management.

## Next Steps

Having completed Modules 01 to 03, you're now ready to explore more advanced features and functionalities of Iceberg tables. Here are some recommended modules to continue your learning:

- **[Module 04 - Partition Evolution](Module%2004%20-%20Partition%20Evolution/README.md):** Discover how Iceberg automatically manages and evolves table partitions to optimize data organization and query performance.
  
- **[Module 05 - Loading Data Multi-function Analytics](Module%2005%20-%20Loading%20Data%20Multi-function%20Analytics/README.md):** Explore advanced data loading techniques to support various analytics use cases across multiple services.

- **[Module 06 - Time Travel](Module%2006%20-%20Time%20Travel/README.md):** Leverage Iceberg's time travel capabilities to query historical data at specific points in time, enabling powerful analytics and audits.

These modules will build on the foundational knowledge you've gained and introduce you to more sophisticated data management techniques within the Iceberg framework.