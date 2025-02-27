# Module 03 - Loading Data

## Overview

This module provides a comprehensive guide to loading data into Iceberg tables on the Cloudera Data Platform (CDP). Iceberg tables offer robust features for managing large-scale datasets, and efficient data loading is key to leveraging these capabilities. This module demonstrates how to load data into Iceberg tables using various methods, ensuring that your data is stored in a scalable, performant, and queryable format.

### Why Load Data into Iceberg Tables?

Loading data into Iceberg tables provides several key benefits:

- **Efficient Data Storage**: Iceberg tables are optimized for storing large datasets in a compact, performant format, reducing storage costs.
- **ACID Transactions**: Iceberg supports ACID transactions, ensuring data integrity during the loading process, even in concurrent environments.
- **Schema Evolution**: As your data evolves, Iceberg allows for easy schema modifications without disrupting existing data or queries.
- **Partitioning and Filtering**: Iceberg's advanced partitioning and filtering capabilities improve query performance by minimizing the amount of data scanned.

### What You'll Learn

In this module, you'll learn how to:

- Load data from external sources (e.g., CSV files) into Iceberg tables.
- Filter and transform data during the load process.
- Verify data integrity and consistency after loading.

### Methods Covered in This Module

This module covers loading data into Iceberg using Spark DataFrames:

This method provides flexibility and control, particularly when working with complex data pipelines.

### Key Takeaways

By mastering these data-loading techniques, you'll ensure that your Iceberg tables are populated with accurate, consistent, and well-organized data. This foundation enables you to fully leverage Iceberg's advanced features, such as time travel, partition evolution, and schema management, leading to more efficient data processing and querying.

**Note:** Remember to replace `${prefix}` with your unique value (e.g., your User ID) throughout the process.

## Submodules

Get started:

`01` [Load Iceberg Tables Using Spark DataFrames](load_iceberg_tbl_SparkDF.md)
