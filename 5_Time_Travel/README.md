# Module 06 - Time Travel

## Overview

This module explores the **Time Travel** feature of Iceberg tables on Cloudera Data Platform (CDP). Time Travel allows you to query data from a specific point in time, which is especially valuable for tasks like regulatory compliance.

### Iceberg Snapshots and Time Travel

Whenever data is added, deleted, or updated in an Iceberg table, a snapshot is automatically captured. These snapshots provide a historical record of the table's state at different points in time. Time Travel leverages these snapshots to enable querying data as it existed at a specific moment.

### Using Time Travel in CDP

This module demonstrates how to use the Time Travel feature with both SQL (using Impala) and Spark SQL within Cloudera Data Engineering (CDE).

- **SQL Example**: Use the Impala interface in CDW to run Time Travel queries based on snapshot timestamps or snapshot IDs.
- **Spark SQL Example**: Use Spark in CDE to query historical data from a snapshot ID or timestamp.

Both examples highlight how to retrieve data as it existed at a specific moment, making it useful for scenarios like auditing or compliance where access to historical data states is required.

Remember to replace `${prefix}` with your actual user ID and `${create_ts}` or `${snapshot_id}` with the chosen timestamp or snapshot ID.

## Prerequisites

Before proceeding, ensure the following:

- You have access to Iceberg tables in CDP with snapshots.
- You can access both Cloudera Data Warehouse (CDW) for SQL queries and Cloudera Data Engineering (CDE) for Spark queries.
- You have the necessary credentials (Kerberos) for cloud storage access.
  
## What You'll Learn

By the end of this module, you will be able to:

- Query historical data using Iceberg Time Travel with SQL (Impala) and Spark SQL.
- Identify and use Iceberg snapshots to query data from a specific point in time.
- Understand how to utilize both Impala and Spark to perform Time Travel queries in CDP.

## Methods Covered in This Module

### Time Travel Using SQL  
   This submodule demonstrates how to use SQL in CDP's Impala interface to perform Time Travel queries using snapshots. You will learn to:
   - Retrieve snapshots from an Iceberg table.
   - Query data using a specific snapshot timestamp.
   - Query data using a snapshot ID.

   [Go to Submodule 01 - Time Travel Using SQL](time_travel_SQL.md)

### Time Travel Using Spark SQL  
   This submodule demonstrates how to use Spark SQL in Cloudera Data Engineering (CDE) to query historical data using snapshots. You will learn to:
   - Retrieve and filter snapshot data from an Iceberg table.
   - Query data based on snapshot IDs or timestamps.

   [Go to Submodule 02 - Time Travel Using Spark SQL](time_travel_spark_SQL.md)

## Key Takeaways

This module demonstrates how to utilize Iceberg's Time Travel feature to query data from specific points in time, using both SQL (Impala) and Spark SQL. This functionality is crucial for tasks such as auditing and regulatory compliance, where historical data states need to be preserved and queried.

As always, remember to replace `${prefix}` with your actual user ID throughout the process.

## Submodules

- `01` [Time Travel Using SQL](time_travel_SQL.md)
- `02` [Time Travel Using Spark SQL](time_travel_spark_SQL.md)
