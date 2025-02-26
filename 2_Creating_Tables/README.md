# Module 02 - Creating Tables

## Overview

This module provides a comprehensive guide to creating Iceberg tables on the Cloudera Data Platform (CDP) using three distinct methods: SQL, Spark SQL, and Spark DataFrames. Iceberg tables are designed to handle large-scale data management with features like schema evolution, partitioning, and efficient querying, making them ideal for modern data environments.

### Why Iceberg Tables?

Iceberg tables offer several key benefits:

- **Efficient Data Management**: Iceberg optimizes storage and querying, leading to faster performance and reduced costs.
- **Schema Evolution**: Easily adapt your tables to changing data structures without rewriting or migrating data.
- **ACID Compliance**: Iceberg ensures data integrity through ACID transactions, even in large-scale environments.
- **Partition Evolution**: Automatically manage and evolve partitions without manual intervention, improving query performance over time.
- **Time Travel**: Query historical data at any point in time, enabling powerful analytics and audits.
- **Compatibility**: Iceberg is compatible with multiple processing engines like Spark, Hive, and Impala, providing flexibility in your data architecture.

### Methods Covered in This Module

This module covers three distinct methods for creating Iceberg tables. Choose one of the following approaches based on your preferred toolset and requirements:

#### 1. Creating Iceberg Tables Using SQL

This method leverages standard SQL commands to define the table schema, data storage format (e.g., Parquet), and partitioning scheme. You'll learn how to create a partitioned Iceberg table named `flights` with relevant columns and partitioning by year.

#### 2. Creating Iceberg Tables Using Spark SQL

Spark SQL offers a programmatic approach to defining Iceberg tables within Spark applications. This method is ideal for those who prefer or require integration with Spark for data processing tasks.

#### 3. Creating Iceberg Tables Using Spark DataFrames

Using Spark DataFrames, you'll learn a programmatic way to create and manage Iceberg tables within Spark environments, allowing for greater flexibility and control over data operations.

### Key Takeaways

By mastering these methods, you'll be equipped to create Iceberg tables tailored to your specific needs on CDP. Whether you're managing large datasets or developing scalable data architectures, Iceberg tables provide the foundation for efficient, reliable, and future-proof data management.

**Note:** Remember to replace `${prefix}` with your unique value (e.g., your User ID) throughout the process.

## Submodules

Choose one of the following submodules to get started:

`01` [Create Iceberg Tables Using SQL](create_iceberg_tbl_SQL.md)

`02` [Create Iceberg Tables Using Spark SQL](create_iceberg_tbl_SparkSQL.md)

`03` [Create Iceberg Tables Using Spark DataFrames](create_iceberg_tbl_SparkDataFrame.md)
