*retrieve columns*
```sql
SELECT *                    -- all columns
	col_1, col_2, col_3     -- select col name
	DISTINCT(col1)          -- unique values of col1
	ROUND(0.9*col_1, 2)     -- numerical operation
	CONCAT(first_name, ' ', last_name) AS col3 -- concat string 
FROM table_1                -- table name
ORDER BY col_1              -- ordering
LIMIT 10                    -- only 10 top rows
```

## Operation
|              | symbol |
| ------------ | ------ |
| sum          | +      |
| substractive | -      |
| multiply     | *      |
| divide       | /      |
| modulus      | %      |
