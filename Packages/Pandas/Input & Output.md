
```python
import pandas as pd                 # import pandas package
```

Import from CSV
```python
# Import csv to DataFrame
df = pd.read_csv('filename.csv')    # read_parquet, read_excel, read_json

	index_col = 1                   # Create the 2nd col as an index, 'col_2'
	index_col = False				# False to force not using the first col
									
	parse_dates=['col_date']        # Handle Datetime
	header=0                        # Default first row as a header, None
	
	nrows = 5                       # Number of rows
	skiprows=5                      # Skip the first 5 rows
	
	sep='\t'                        # Separation. '\t', ';', default ',' 
	comment='#'                     # Take characters that are comments
	na_values='Nothing'             # NA/NaN
	
	usecols=col_names               # col_names= ['col1'] or [0, 1, 2]
	names=col_names                 # name the header
	dtype={'col1': str}             # specify dtype
	
	error_bad_lines=False           # skip unparseable row
	warn_bad_lines=True             # warn skip rows
	
	compression='gzip'              # compression, format .csv.gz
```
Read more: https://pandas.pydata.org/docs/reference/api/pandas.read_csv.html 

Export to CSV
```python
# Export to "data1.csv"
df.to_csv("data1.csv")              # Export as a csv file
	index=False                     # Ignore index
	header=False                    # Ignore header
	float_format='%.2f'             # Formatting digits
	sep='\t'                        # Separation, default ','
```

