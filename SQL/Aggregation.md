*aggregate for all data in selected column*

*Note: use HAVING, not WHERE for filtering*

***agg_func**: AVG, COUNT, SUM, MIN, MAX, STDDEV, VARIANCE*

**NULL**: in general don't take into account NULL, but counted in COUNT

```sql
SELECT
	agg_func(col_1)         -- agg func
	
	COUNT(DISTINCT cust_id) -- count num of cust (unique row) (agg_func)
	
FROM table_name
```

