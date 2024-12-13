- Functions perform operations without modifying the database. Use procedures for data modification
- Types:
	- System-defined functions: Built-in functions provided by the database
	- User-defined functions: Custom functions created by users
## System defined function
### Extract from date
```sql
SELECT 
	EXTRACT(MONTH FROM date) AS month,     -- Extract year, month, day
	SUM(amt) AS total_amt
FROM table_1
GROUP BY month
```

### Extract from string
```sql
SELECT 
	CASE WHEN SUBSTRING(col1, 1, 3)='S10'
	THEN 'electronic'
	ELSE 'cookware' END AS category
	SUM(amt) as total_amt
FROM table_1
GROUP BY category
```

### List of common system-defined functions

| Category     | functions                               |
| ------------ | --------------------------------------- |
| Aggregate    | avg(), sum(), min(), max()              |
| Casting      | cast()                                  |
| Window       | row_number(), rank(), dense_rank(),     |
| Date/Time    | current_date, current_time, date_part() |
| String       | reverse(), split_part(), substring()    |
| Flow control | case, while, iterate                    |
| Numeric      | abs(), acos(), degrees()                |
Example:
```sql
SELECT 
	col_1,
	function(col_1)
FROM table_1
JOIN table_2
	ON key_table_1 = key_table_2
WHERE function(col_1) operator value
GROUP BY col
HAVING function(col_1) operator value
ORDER BY col_1
LIMIT 10
```

## User defined function
```sql
CREATE FUNCTION final_amt(total_amt INT, disc INT)
RETURN INT
LANGUAGE plpgsql
AS
$$
BEGIN
	RETURN total_amt*(1-(disc::float/100))
END
$$
```

Using the function
```sql
SELECT 
	trx_id,
	total_amt
	final_amt(total_amt, disc)
FROM sales
```

Listing all created functions
```sql
SELECT
	routine_name
FROM 
	information_schema.routines
WHERE
	routine_type='FUNCTION'
	AND routine_schema='public';
```