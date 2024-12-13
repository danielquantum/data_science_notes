Aggregation (agg): 
- performs calculations on all data in a column
Grouping:
- organized based on categories (columns) 
- all columns in SELECT clause (except aggregate functions), must be included in the GROUP BY clause
- use HAVING for filtering aggregated data
Window function: 
- allow access to rows that are not grouped while still using aggregate functions 
Join:
- Be cautious with joins as they can create duplicate rows if not structured carefully

```sql
SELECT *                  -- Retrieve all columns
	col_1                 -- Col used for grouping
	agg_func              -- Use HAVING after group by col1
FROM table_1              -- First table
JOIN table_2 USING        -- Use: USING for same col name, else use: ON 
WHERE <condition>         -- Filtering, no agg_func
GROUP BY col_1            -- Group rows by col_1
HAVING <condition>        -- Filtering agg_func results
ORDER BY col_1            -- Sort results
LIMIT <n>                 -- Limit the number of rows
```

Related: [[Select]], [[Filter]], [[Aggregation]], [[Group]], [[Window Function]], [[Join]], [[Sub Query]], [[CTE]], [[SQL/Function|Function]], [[View]]