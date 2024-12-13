*agg: for all data, grouping: agg based on category*

*Note: col names which are not aggregated in SELECT, must be in GROUP BY*

*use HAVING, not WHERE for filtering*

```sql
SELECT 
	col_1,                      -- must included in group by
	SUM(col_name2) AS new_name  -- new_name column
FROM table_name
GROUP BY col_1                  -- col1 must be called
HAVING new_name > 5             -- add filter after grouping
```
