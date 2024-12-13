*Aggregation (agg): Applied to all data, 
Grouping: Aggregated data based on categories*

*Note: 
- All non-aggregated columns in the SELECT clause must be included in the GROUP BY clause
- Use HAVING (not WHERE) to filter aggregated results 

```sql
SELECT 
	col_1,                      -- Must included in group by
	SUM(col_name2) AS new_name  -- Agg func with alias
FROM table_1                    -- Table name
GROUP BY col_1                  -- Group by col_1
HAVING new_name > 5             -- Filter aggregated results
```
