# Module 01 - Table Migration

## Migrating Tables to Iceberg and Querying Multiple Table Formats

This module guides you through the process of migrating tables to the Iceberg format on the Cloudera.

### Why Migrate to Iceberg?

Apache Iceberg is an open table format designed for large analytic datasets. It provides several advantages over traditional Hive tables, including:

- **Improved Performance:** Faster query execution due to optimized data access patterns.
- **Better Data Management:** Simplified management of table metadata and schema evolution.
- **Seamless Integration:** Ability to query Iceberg and Hive tables together, allowing gradual migration without disrupting existing workflows.

### Migration Approaches

There are two primary approaches to migrating tables to Iceberg:

- **In-place migration:** Modifies an existing Hive table to use Iceberg for managing metadata.
- **Create Table as Select (CTAS):** Creates a new Iceberg table by reading data from an existing table.

### Examples of Table Migration

You may already be familiar with the following examples of migrating tables to Iceberg format:

- **`flights` table:** Created directly in Iceberg format.
- **`planes` table:** Will migrate using the `ALTER TABLE` utility.
- **`airports` table:** Created as a new Iceberg table using CTAS.

### Choosing Your Migration Approach

In this module, you'll choose one of the approaches listed in the submodules below to work through the process of migrating tables to Iceberg. Each submodule provides detailed instructions for a different method. 

### Key Takeaways

By the end of this module, you'll understand how to:

- Improve performance and data management for specific tables by migrating them to Iceberg.
- Migrate tables to Iceberg over time, ensuring a smooth and non-disruptive transition.

> **Note:** Remember to replace `${prefix}` with your chosen value (e.g., your User ID) throughout the process.

### Submodules

`01` [Migrate Tables to Iceberg Using SQL](migrate_tbl_to_iceberg_SQL.md)
