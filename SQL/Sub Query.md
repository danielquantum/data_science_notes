- Advantages: Useful for complex filtering or intermediate calculations
- Disadvantages: Compact but not reusable and can be harder to read
- Purpose: Retrieve a subset of data or perform calculations, such as finding values above an average value
### Sub query in WHERE clause
```sql
SELECT *                               -- Retrieve all columns
FROM table_1                           -- Table name
WHERE col_1 > (SELECT AVG(col_1)       -- Filter rows where col_1 is above the average value 
			   FROM table_1)           -- Subquery: calculates the average of col_1
```

### Sub query in FROM clause
```sql
SELECT MIN(col_1)                     -- Get the min value from col_1
FROM (                                -- Subquery: filters rows where col_1 is above the average
	SELECT *
	FROM table_1
	WHERE col_1 > (SELECT AVG(col_1)  -- Inner subquery calculates average of col_1
				FROM table_1)
) AS trx_above_avg                    -- Alias for the subquery result
```