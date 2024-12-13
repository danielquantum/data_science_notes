- Purpose: Simplify and improve readability of complex queries by breaking them into logical steps
- Advantages: Easier to read and debug compared to sub queries
- Disadvantages: CTEs are less reusable within the same session compared to temporary tables

### Using sub query
*compact but hard to read and not reusable*
```sql
SELECT MIN(col1)
FROM (
	SELECT *
	FROM table1
	WHERE col1 > (SELECT AVG(col1)
				FROM table1)
) AS trx_above_avg
```

### Using common table expression (CTE)
*improve readability but needs to be rerun each time*
```sql
WITH total_trx AS(
	SELECT id, SUM(amt) AS total_amt
	FROM table1
	JOIN table2
		ON tab1.id = tab2.id
	GROUP BY id
)
SELECT *
FROM total_trx
JOIN tab2
	ON total_trx.id = tab2.id
WHERE total_amt < (SELECT AVG(total_amt) FROM total_trx)
```

Multiple CTEs
```sql
WITH cte_1 AS(
	SELECT col_1
	FROM table_1
	WHERE col_1 > ()
),                         -- use comma
cte_2 AS(
	SELECT col_2
	FROM table_2
)
SELECT *
FROM cte_1
JOIN cte_2 ON cte_1.col_1 = cte_2.col_2
```

### Using temporary table
*Reusable within the session, unlike CTEs*
```sql
CREATE TEMPORARY TABLE total_trx AS(
	SELECT id, SUM(amt) AS total_amt
	FROM table1
	JOIN table2
		ON tab1.id = tab2.id
	GROUP BY id
)
SELECT *
FROM total_trx
JOIN tab2
	ON total_trx.id = tab2.id
WHERE total_amt < (SELECT AVG(total_amt) FROM total_trx)
```