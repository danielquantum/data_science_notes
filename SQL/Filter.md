```sql
SELECT *                              -- Retrieve all columns
	EXTRACT(MONTH FROM date) AS month -- Retrieve month from the date col
FROM table_1                          -- Table name
WHERE                                 -- Filtering
	birthday > '1970-01-01'           -- Filtering by date
	strftime('%m', col_1) = '08'      -- Extract parts of the date '%Y','%m','%d'
	                                  -- IS NULL for empty values
	
	AND sex = 'M'                     -- Filtering by gender, Male
	OR salary > 1000                  -- Additional filter

	salary BETWEEN 1000 AND 2000      -- Range filter

	id IN (105,107)                   -- Membership filter

	LENGTH('col1') > 5                -- Length larger than 5 characters

	first_name LIKE 'D%'              -- Case sensitive pattern matching
	first_name ILIKE '_a%'            -- Case insensitive pattern matching
```

## Comparison
| Comparison | Symbol | Symbol |
| ---------- | ------ | ------ |
| Less than  | i < j  | i <= j |
| More than  | i > j  | i >= j |
| Equal      | i = j  |        |
| Not equal  | i != j |        |
## Matching Pattern
|                   | Symbol |                                                      |
| ----------------- | ------ | ---------------------------------------------------- |
| Start with        | 'D%'   | Matches strings starting with letter D               |
| End with          | '%l'   | Matches strings ending with letter l                 |
| Contains          | '%ni%' | Matches strings containing 'ni'                      |
| Specific position | '_an'  | Matches strings containing 'an' in the 2,3 character |
