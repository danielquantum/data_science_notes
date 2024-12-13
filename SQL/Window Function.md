- Use window functions to compare aggregated values with original values, allowing calculations within a group without collapsing rows

| Grouping | temp | avg_temp |     | Window Function | temp | avg_temp |
| -------- | ---- | -------- | --- | --------------- | ---- | -------- |
| City A   | 30   | 30       |     | City A          | 30   | 27.5     |
| City A   | 25   | 25       |     | City A          | 25   | 27.5     |
| City B   | 27   | 27       |     | City B          | 27   | 24.5     |
| City B   | 22   | 22       |     | City B          | 22   | 24.5     |

```sql
SELECT 
	city, 
	temp,
	AVG(temp) OVER() AS avg_temp      -- Calc over all temp rows
	AVG(temp) OVER(PARTITION BY city  -- Categorized by city
		ORDER BY temp DESC            -- Sort by
		frame_clause)                 -- Defined partition boundary, side effect of order by
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

## Window Function Types
### Aggregate functions

```sql
SELECT
	agg_func() OVER(PARTITION BY col_1)   -- rank func
FROM table_name
```

| Aggregate | Description        |
| --------- | ------------------ |
| COUNT()   | Count rows         |
| AVG()     | Calculate average  |
| MIN()     | Find minimum value |
| MAX()     | Find maximum value |
| STDDEV    | Standard deviation |
| VARIANCE  | Variance           |

### Ranking functions
```sql
SELECT
	rank_func() OVER(ORDER BY col1)   -- rank func
FROM table_name
```

| Ranking        | Description                                  |
| -------------- | -------------------------------------------- |
| ROW_NUMBER()   | Unique rank for each row                     |
| RANK()         | Rank with gaps (e.g., 1, 1, 3, 4)            |
| DENSE_RANK()   | Rank without gaps (e.g., 1, 1, 2, 3)         |
| PERCENT_RANK() | Rank expressed as a percentage               |
| NTILE(N)       | Divides rows into N groups                   |
| CUME_DIST()    | Cumulative distribution as a fractional rank |

### Value functions
```sql
SELECT
	value_func() OVER(PARTITION BY col1)   -- rank func
		ORDER BY col2
		RANGE BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING         -- frame clause
FROM table_name
```

| Analytic            | Description                  |
| ------------------- | ---------------------------- |
| FIRST_VALUE(col_1)  | First value in the partition |
| LAST_VALUE(col_1)   | Last value in the partition  |
| NTH_VALUE(col_1, N) | Nth value in the partition   |
| LAG(col_1, N)       | N rows before the current    |
| LEAD(col_1, N)      | N rows after the current     |

related: https://www.geeksforgeeks.org/window-functions-in-sql/
https://mode.com/sql-tutorial/sql-window-functions