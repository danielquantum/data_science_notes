*Reusable in multiple queries, need rerun query to update, create virtual table*

create view
```sql
CREATE VIEW total_trx_monthly 
AS
SELECT 
	EXTRACT (MONTH FROM date) AS month,
	SUM(amt) AS total_amt
FROM table_1
```

call view
```sql
SELECT *
FROM total_trx_monthly
```

list view
```sql
SELECT 
	table_schema AS schema,
	table_name AS view
FROM 
	information_schema.views
WHERE
	table_schema NOT IN('information_schema', 'pg_category') 
ORDER BY
	schema ASC
	view ASC;
```

## Materialized views
*don't rerun query, only save resulted table, Requires refresh to update, improves performance*
```sql
CREATE MATERIALIZED VIEW avg_product_sell
AS
SELECT
	CASE WHEN SUBSTRING(col1, 1, 3)='S10' THEN 'electronic'
	ELSE 'cockware'
	END AS category
	AVG(total_amt) AS avg_amt
FROM table_1
GROUP BY category
HAVING AVG(total_amt) < (SELECT AVG(total_amt) FROM table_1)
```

