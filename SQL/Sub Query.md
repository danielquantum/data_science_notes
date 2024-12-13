*compact, no reusable, hard to read*
*get  a set of table e.g. above average*

### Sub query in where clause
```sql
SELECT *
FROM table_1
WHERE col_1 > (SELECT AVG(col_1)       -- col_1 above avg value of col_1
			   FROM table_1)
```

### Sub query in from clause
```sql
SELECT MIN(col_1)
FROM (                                -- take min val from col_1 above avg values
	SELECT *
	FROM table_1
	WHERE col_1 > (SELECT AVG(col_1)
				FROM table_1)
) AS trx_above_avg
```