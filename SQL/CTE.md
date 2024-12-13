*common table expression: to reduce complexity of sub query*

### Using sub query
*compact, no reusable, hard to read*
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
*improve readability, less reusable (need to rerun)*
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

two CTE
```sql
WITH table_name AS(
	SELECT col_1
	FROM table_1
	WHERE col_1 > ()
),                         -- use comma
table_2 AS(
	SELECT
	FROM
)
```

### Using temporary table
*reused multiple times in the session*
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