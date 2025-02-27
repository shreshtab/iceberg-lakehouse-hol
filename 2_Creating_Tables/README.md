# Module 02 - Creating Tables

## Overview

This module provides a comprehensive guide to creating Iceberg tables on Cloudera using SQL. Iceberg tables are designed to handle large-scale data management with features like schema evolution, partitioning, and efficient querying, making them ideal for modern data environments.

### Why Iceberg Tables?

Iceberg tables offer several key benefits:

- **Efficient Data Management**: Iceberg optimizes storage and querying, leading to faster performance and reduced costs.
- **Schema Evolution**: Easily adapt your tables to changing data structures without rewriting or migrating data.
- **ACID Compliance**: Iceberg ensures data integrity through ACID transactions, even in large-scale environments.
- **Partition Evolution**: Automatically manage and evolve partitions without manual intervention, improving query performance over time.
- **Time Travel**: Query historical data at any point in time, enabling powerful analytics and audits.
- **Compatibility**: Iceberg is compatible with multiple processing engines like Spark, Hive, and Impala, providing flexibility in your data architecture.

### Methods Covered in This Module

This module covers creating Iceberg tables with Impala.

This method leverages standard SQL commands to define the table schema, data storage format (e.g., Parquet), and partitioning scheme. You'll learn how to create a partitioned Iceberg table named `flights` with relevant columns and partitioning by year.

### Key Takeaways

By mastering these methods, you'll be equipped to create Iceberg tables tailored to your specific needs on CDP. Whether you're managing large datasets or developing scalable data architectures, Iceberg tables provide the foundation for efficient, reliable, and future-proof data management.

**Note:** Remember to replace `${prefix}` with your unique value (e.g., your User ID) throughout the process.

## Submodules

Choose the following submodule to get started:

`01` [Create Iceberg Tables Using SQL](create_iceberg_tbl_SQL.md)
