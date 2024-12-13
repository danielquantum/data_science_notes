- *Aggregated all data in a selected column*
- *Use HAVING (not WHERE) for filtering aggregated results*
- ***Aggregate Functions (agg_func)**: AVG, COUNT, SUM, MIN, MAX, STDDEV, VARIANCE*

Handling **NULL**: 
- General Rule: Aggregate functions ignore NULL values
- Exception: COUNT includes NULL when counting rows 

```sql
SELECT
	agg_func(col_1)         -- Apply aggregate function to col_1
	
	COUNT(DISTINCT cust_id) -- Count unique rows in cust_id col
	
FROM table_name
```

