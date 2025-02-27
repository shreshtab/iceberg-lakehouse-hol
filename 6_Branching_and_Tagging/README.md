# Module #6 - Branching & Tagging

## Overview

This module explores branching and tagging in Iceberg tables on the Cloudera. Iceberg’s time-travel capabilities are enhanced by the ability to create branches and tags, enabling safer experimentation, versioning, and data governance. In this module, you'll learn how to leverage branching and tagging to manage Iceberg table versions efficiently using SQL.

### Why Branching and Tagging?
Branching and tagging in Iceberg tables provide several key benefits:

- **Safe Experimentation and Isolation**: Create isolated branches of your table to test new data processing workflows, transformations, or schema changes without affecting production data.
- **Instant Rollbacks and Versioning**: Tags allow you to mark specific snapshots of a table, making it easy to revert to a known good state in case of issues or unexpected changes.
- **Efficient Data Pipelines**: Branching enables concurrent workflows, allowing teams to develop and validate data changes independently before merging them into production.
- **Auditability and Governance**: Maintain a historical record of table versions with meaningful tags, improving traceability and compliance with data governance policies.

### Branching and Tagging using SQL

In this method, you’ll explore branching and tagging using SQL. The examples demonstrates how to modify the `flights` table by adding branches and tags.

### Key Takeaways

- Iceberg Tags and Branches are powerful features that enable isolation within a lakehouse without needing to create copies of the same data
- Iceberg branches allow you to safely experiment and build data processing pipelines without needing to worry about impacting others
- Tagging provides robust governance and is a lot easier to use for Time Travel queries