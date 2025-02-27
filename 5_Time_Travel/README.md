# Module 06 - Time Travel

## Overview

This module explores the **Time Travel** feature of Iceberg tables on Cloudera. Time Travel allows you to query data from a specific point in time, which is especially valuable for tasks like regulatory compliance.

### Iceberg Snapshots and Time Travel

Whenever data is added, deleted, or updated in an Iceberg table, a snapshot is automatically captured. These snapshots provide a historical record of the table's state at different points in time. Time Travel leverages these snapshots to enable querying data as it existed at a specific moment.

### Using Time Travel in CDP

This module demonstrates how to use the Time Travel feature with both SQL (using Hive).

- **SQL Example**: Use the Hive interface in CDW to run Time Travel queries based on snapshot timestamps or snapshot IDs.

The example highlights how to retrieve data as it existed at a specific moment, making it useful for scenarios like auditing or compliance where access to historical data states is required.

Remember to replace `${prefix}` with your actual user ID and `${create_ts}` or `${snapshot_id}` with the chosen timestamp or snapshot ID.

## Prerequisites

Before proceeding, ensure the following:

- You have access to Iceberg tables in CDP with snapshots.
- You can access both Cloudera Data Warehouse (CDW) for SQL queries
- You have the necessary credentials (Kerberos) for cloud storage access.
  
## What You'll Learn

By the end of this module, you will be able to:

- Query historical data using Iceberg Time Travel with SQL (Hive).
- Identify and use Iceberg snapshots to query data from a specific point in time.
- Understand how to utilize Hive to perform Time Travel queries in CDP.


### Time Travel Using SQL  
   This submodule demonstrates how to use SQL in CDP's Hive interface to perform Time Travel queries using snapshots. You will learn to:
   - Retrieve snapshots from an Iceberg table.
   - Query data using a specific snapshot timestamp.
   - Query data using a snapshot ID.

As always, remember to replace `${prefix}` with your actual user ID throughout the process.

## Submodules

- `01` [Time Travel Using SQL](time_travel_SQL.md)
