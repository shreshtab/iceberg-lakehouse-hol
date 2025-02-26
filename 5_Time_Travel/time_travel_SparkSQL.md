# Time Travel Using Spark SQL

## Overview

In the previous steps, we have been loading data into the `flights` Iceberg table. Each time we add, delete, or update data, a snapshot is captured. This ensures eventual consistency and allows multiple reads/writes concurrently from various engines. In this submodule, we will leverage the **Time Travel** feature in Spark SQL to query data from a specific point in time. A common use case for this feature is regulatory compliance.

## Step-by-Step Guide

### Step 1: Execute Time Travel with SYSTEM_VERSION

In this step, you will execute the following commands in a CDE session using Spark version 3.5.1 (or version 3.3.x).

```
from pyspark.sql.functions import col

# Variables - replace <prefix> with your user ID
prefix = "<prefix>"
odl_database_name = prefix + "_airlines"

# RETURN SNAPSHOTS (History)
history_df = spark.sql(f"SELECT * FROM {odl_database_name}.flights.snapshots")

history_df.show()

# GET FIRST SNAPSHOT CREATED - committed_at
history_df = history_df.filter(col("parent_id").isNull())

snapshot_id = history_df.first().snapshot_id

print("Actual Timestamp of Snapshot: ", snapshot_id)

# TIME TRAVEL TO THIS SNAPSHOT
spark.sql(f"SELECT year, count(*) FROM {odl_database_name}.flights SYSTEM_VERSION AS OF {snapshot_id} GROUP BY year ORDER BY year desc").show()
```

### Step 2: Execute Time Travel with SYSTEM_TIME

In this step, you will query historical data using a timestamp-based approach.

```
from pyspark.sql.functions import col
import datetime

# Variables - replace <prefix> with your user ID
prefix = "<prefix>"
odl_database_name = prefix + "_airlines"

# RETURN SNAPSHOTS (History)
history_df = spark.sql(f"SELECT * FROM {odl_database_name}.flights.snapshots")

history_df.show()

# GET FIRST SNAPSHOT CREATED - committed_at
history_df = history_df.filter(col("parent_id").isNull())

first_date = history_df.first().committed_at

# Add 1 minute to date & truncate date to seconds
time_change = datetime.timedelta(minutes=1) 
relative_ts = first_date + time_change
relative_ts = relative_ts.replace(second=0, microsecond=0)

print("Actual Timestamp of Snapshot: ", first_date)
print("Relative Timestamp for Time Travel: ", relative_ts)

# TIME TRAVEL TO THIS DATE
spark.sql(f"SELECT year, count(*) FROM {odl_database_name}.flights FOR SYSTEM_TIME AS OF '{relative_ts}' GROUP BY year ORDER BY year desc").show()
```

### Step 3: Review Snapshots

- The command `SELECT * FROM <db>.<table>.snapshots` returns all available snapshots for the `flights` Iceberg table. These snapshots are automatically captured each time data is loaded.

## Summary

In this submodule, you learned how to use Iceberg’s **Time Travel** feature in Spark SQL to query historical data using both snapshot IDs and timestamps. This allows you to retrieve the state of your data at any specific point in time for auditing or compliance purposes.

## Next Steps

To explore additional functionality with Iceberg and Spark, proceed to the next module as per your learning path.
