```sql
SELECT *
FROM table_1
WHERE
	birthday > '1970-01-01'        -- date
	
	sex = 'M'                      -- only Male
	AND salary > 1000              -- more filter

	salary BETWEEN 1000 AND 2000   -- between

	id IN (105,107)                -- IN operator

	first_name LIKE 'D%'           -- case sensitive
	first_name ILIKE '_a%'         -- case insensitive
```

## Comparison
| Comparison | Symbol | Symbol |
| ---------- | ------ | ------ |
| less       | i < j  | i <= j |
| more       | i > j  | i >= j |
| equal      | i = j  |        |
| not equal  | i != j |        |
## Matching Pattern
|            | Symbol |                                    |
| ---------- | ------ | ---------------------------------- |
| start with | 'D%'   | start with letter D                |
| end with   | '%l'   | end with letter l                  |
|            | '%ni%' | contains 'ni' character            |
|            | '_an'  | contains 'an' in the 2,3 character |
