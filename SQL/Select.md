*Retrieve columns*

```sql
SELECT *                    -- Retrieve all columns
	col_1, col_2, col_3     -- Retrieve specific cols name
	DISTINCT(col_1)         -- Unique values of col_1
	ROUND(0.9*col_1, 2)     -- Numerical operation
	first_name||' '||last_name AS col4 -- Concatenate (MySQL use CONCAT)
FROM table_1                -- Table name
ORDER BY col_1              -- Sort result, default ASC
LIMIT <n>                   -- Limit the number of rows
```

## Operation
|                     | symbol |
| ------------------- | ------ |
| Addition            | +      |
| Subtraction         | -      |
| Multiplication      | *      |
| Division            | /      |
| Modulus (remainder) | %      |
