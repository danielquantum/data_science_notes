- *Default JOIN: INNER JOIN
- Combines rows from two or more tables on a related column called key
- Use an Entity Relationship Diagram (ERD) to visualize table relationships

```sql
SELECT *                           -- Retrieve all columns
FROM table_1                       -- Left table
JOIN table_2                       -- Inner (default), left, right join
	USING col_name                 -- Use if keys are similar in both tables
	ON table_1.col1 = table_2.col2 -- Use explicit key when col name differ
WHERE <condition>                  -- Filtering results 
GROUP BY col_1                     -- Group rows for aggregation
HAVING <condition>                 -- Filter aggregated results
ORDER BY col_1                     -- Sort results
LIMIT <n>                          -- Restrict number of rows
```
