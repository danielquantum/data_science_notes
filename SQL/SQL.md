agg: for all data in a column
group: based on category (all columns in Select, must be included group by) -> use HAVING for filtering
window func: to see other columns not in group by in (agg + group), use window function

```sql
SELECT *                  -- all
	col_1                 -- use for grouping
	agg_func              -- use HAVING, group by col1
FROM table_1              -- table
JOIN table_2 USING        -- for same cols name, diff: ON 
WHERE                     -- filtering, no agg_func
GROUP BY col_1            -- grouping
HAVING                    -- agg_func
ORDER BY                  -- ordering
LIMIT                     -- limit
```

related: [[Select]], [[Filter]], [[Aggregation]], [[Grouping]], [[Window Function]], [[Join]], [[Sub Query]], [[CTE]], [[Functions|Functions]], [[Views]]
