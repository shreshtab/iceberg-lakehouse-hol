### UNDER CONSTRUCTION

# Branching

In this section we will work with Branches to create a branch to let us .

Branches are named references to snapshots with their own independent lifecycles.  You can use a <b>Branch</b> in your data engineering workflows and create experimetnal branches for testing & validating new jobs.  Other use cases inclue GDPR requirements and retaining important historical snapshots for auditing. 

**Query the Planes Table (in CDW HUE)**

- Execute the following in HUE for Hive VW

- This query can be used to check results for flight delays

```
SELECT * FROM ${prefix}_airlines.flights
LIMIT 100;
```

- In 

- Execute the following in HUE for Hive VW

- This query can be used to check results for flight delays by making a change to the SQL to see if the results change.

```
```

- This query represents the correct results for flight delays.  This would be how each user querying the table to return Avg. Flight Delays would need to query the table

  - Instead of having complex SQL requirements, it would be better to modify the data accordingly.  We will do this by updating the data

  - Execute the following to update the table

  ```
  ```




**Create Branch for Testing new Data Engineering Workflow**

- Create a branch by basing the branch on a snapshot ID.  You can also use a timestamp, or state of the table.  Using the SNAPSHOT RETENTION clause, you can create a branch that limits the number of snapshots of a table.

- 

- E

**Query the Branch for the Flights Table (in CDW HUE)**

- Execute the following in HUE for Hive VW

```
SELECT * 
  FROM ${prefix}_airlines.flights.branch_${branch_name}
LIMIT 100;
```

- In results you see that 


