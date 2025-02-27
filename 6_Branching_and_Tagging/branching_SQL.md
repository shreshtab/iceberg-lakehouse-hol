### UNDER CONSTRUCTION

# Branching

In this section we will work with Branches to create a branch to let us create isolated branches of our table to test new data processing workflows, transformations, or schema changes without affecting production data.

Branches are named references to snapshots with their own independent lifecycles. Other use cases inclue GDPR requirements and retaining important historical snapshots for auditing. 

**Query the Planes Table (in CDW HUE)**

- Execute the following in HUE for Hive VW. Pick up a snapshot ID to use for the next step.

```sql
-- See table history
SELECT * FROM ${prefix}_airlines.flights.HISTORY;

-- See table references including branches
SELECT * FROM ${prefix}_airlines.flights.REFS;
```

- Now let's run the following query. Use the snapshot ID from earlier.

```sql
ALTER TABLE ${prefix}_airlines.flights CREATE BRANCH initial FOR SYSTEM_VERSION AS OF ${snapshot_id};

-- Alternate (optional option)
ALTER TABLE ${prefix}_airlines.flights CREATE BRANCH next FOR SYSTEM_TIME AS OF '${create_ts}';

-- See table references including the new branch
SELECT * FROM ${prefix}_airlines.flights.REFS;
```

You can also create a branch without specifying a snapshot or system time version.

```sql
ALTER TABLE ${prefix}_airlines.flights
CREATE BRANCH backup;

-- Run to see updates
SELECT * FROM ${prefix}_airlines.flights.REFS;
```

Next, let's query a branch.

```sql
SELECT year, count(*) 
    FROM ${prefix}_airlines.flights.branch_initial
    GROUP BY year
    ORDER BY year desc;
```

Similarly, one can make updates to a given branch in isolation from the main branch.

Other branching capabilities include:

- Fast-forwarding a Branch (under certain conditions)

- Specify the number of snapshots a branch retains

- Deleting a Branch

## Next Steps

To continue exploring Iceberg, proceed to the next module:

- `01` [Tagging](../6_Branching_and_Tagging/tagging_SQL.md)