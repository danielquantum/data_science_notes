*default: INNER JOIN as JOIN*

ERD: Entity Relationship Diagram
```sql
SELECT *
FROM table_1                       -- left
LEFT JOIN table_2                  -- inner, left, right join
	USING col_name                 -- if keys are similar
	ON table_1.col1 = table_2.col2 -- key
WHERE
GROUP BY
HAVING
ORDER BY
LIMIT
```