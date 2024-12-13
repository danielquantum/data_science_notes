*can't compared agg values with original values, so use windowing*

| Group  | temp | avg_temp |     | Window Function | temp | avg_temp |
| ------ | ---- | -------- | --- | --------------- | ---- | -------- |
| City A | 30   | 30       |     | City A          | 30   | 27.5     |
| City A | 25   | 25       |     | City A          | 25   | 27.5     |
| City B | 27   | 27       |     | City B          | 27   | 24.5     |
| City B | 22   | 22       |     | City B          | 22   | 24.5     |

```sql
SELECT 
	city, 
	temp,
	AVG(temp) OVER() AS avg_temp      -- for all data
	AVG(temp) OVER(PARTITION BY city  -- categorized by city
		ORDER BY temp DESC            -- order by
		frame_clause)                 -- partition boundary, side effect of order by
FROM table_name
```

### Frame Clause
*specifies a subset of rows to consider within the partition*
![[sqlite-window-frame.png]]
```sql
SELECT 
	city,
	temp,
	AVG(temp) OVER(
		PARTITION BY city                  -- group by
		ORDER BY temp DESC                 -- order by
		RANGE BETWEEN UNBOUNDED PRECEDEDING AND UNBOUNDED FOLLOWING --partition
		)
```
reference: https://www.sqlitetutorial.net/sqlite-window-functions/sqlite-window-frame/

## Window Function
### Aggregate function

```sql
SELECT
	agg_func() OVER(PARTITION BY col1)   -- rank func
FROM table_name
```

| Aggregate | Description        |
| --------- | ------------------ |
| COUNT()   | count              |
| AVG()     | average            |
| MIN()     | minimum            |
| MAX()     | maximum            |
| STDDEV    | standard deviation |
| VARIANCE  | variance           |

### Rank function
```sql
SELECT
	rank_func() OVER(ORDER BY col1)   -- rank func
FROM table_name
```

| Ranking        | Description                                                    |
| -------------- | -------------------------------------------------------------- |
| ROW_NUMBER()   | assigns a unique number to each row within a partition         |
| RANK()         | rank: 1 1 3 4                                                  |
| DENSE_RANK()   | rank: 1 1 2 3                                                  |
| PERCENT_RANK() | rank in percentage                                             |
| NTILE()        | n-percentile                                                   |
| CUME_DIST()    | relative rank of a row within its partition in fraction number |

### Value function
```sql
SELECT
	value_func() OVER(PARTITION BY col1)   -- rank func
		ORDER BY col2
		RANGE BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING         -- frame clause
FROM table_name
```

| Analytic            | Description          |
| ------------------- | -------------------- |
| FIRST_VALUE(col_1)  | first value          |
| LAST_VALUE(col_1)   | last value           |
| NTH_VALUE(col_1, N) | Nth value            |
| LAG(col_1, N)       | pull N previous val  |
| LEAD(col_1, N)      | pull N following val |

related: https://www.geeksforgeeks.org/window-functions-in-sql/
https://mode.com/sql-tutorial/sql-window-functions