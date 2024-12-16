
```python
import pandas as pd                 # import pandas package
```

Import CSV to DataFrame
```python
# Import csv to DataFrame
df = pd.read_csv('filename.csv')    # read_table, read_excel, read_json, 
									# read_stata, read_sql, read_fwf

	index_col = 0                   # Create the first col as index
	parse_dates=True                # Handle Datetime
	header=0                        # Default first row as a header
	
	nrows = 5                       # number of rows
	skiprows=5                      # skip the first 5 rows
	
	sep='\t'                        # Separation format ',' or '\t'
	comment='#'                     # take characters that are comments
	na_values='Nothing'             # NA/NaN
	
	usecols=col_names               # col_names= ['col1'] or [0, 1, 2]
	names=col_names                 # name the header
	dtype={'col1': str}             # specify dtype
	
	error_bad_lines=False           # skip unparseable row
	warn_bad_lines=True             # warn skip rows
```

Write DataFrame to CSV
```python
# Export to "data1.csv"
df.to_csv("data1.csv")              # Export as csv file
	index=False                     # Ignore index
	header=False                    # Ignore header
	float_format='%.2f'             # Formatting digits
	sep='\t'                        # Separation
```

Create DataFrame
```python
# Dictionary
dict_data = {
    "item": ["Indomie", "Taro", "Good Day", "Detergen"],
    "type": ["food", "food", "food", "non-food"],
    "amount": [5, 2, 1, 1]
}

index_data = ["IDMF", "TROF", "GODF", "DETN"]

# Create DataFrame from dictionary
df = pd.DataFrame(dict_data, index=index_data)        # Create DF
```

Concat
```python
df3 = pd.concat([df1, df2])
```

Merge
```python
# df1
df1 = pd.DataFrame({
    "item": ["Indomie", "Taro"],
    "amount": [5, 2]
    })

# df2
df2 = pd.DataFrame({
    "item": ["Indomie", "Taro", "Pasta gigi"],
    "stock": [17,11,5]
    })

# Merge, default = 'inner'
pd.merge(df1, df2, on="item", how='left')      # 'left', 'right'/'outer', 'inner'
```

Join:
key should be the index, default: left join
```python
# Create df1
df1 = pd.DataFrame({
    "item": ["Indomie", "Taro"],
    "amount": [5, 2]
    })
df1.set_index('nama_barang', inplace=True)

# Create df2
df2 = pd.DataFrame({
    "item": ["Indomie", "Taro", "Pasta gigi"],
    "stock": [17,11,5]
    })
df2.set_index('nama_barang', inplace=True)

# Join
df1.join(df2)
```

Casting
```python
df.dtypes

df = df['amount'].astype(float)
df = df['type'].astype('category')
```

### Set index
Approach 1
```python
# Create new index start from 10 
new_index = [i for i in range(10,30)]

# Set index
customer_data.index = new_index
customer_data.head()
```

Approach 2
```python
# Read Data
df = pd.read_csv('filename.csv', index_col='name')
df.head()

# After import
df.set_index("col_name", inplace=True)
```

Reset index
```python
df.reset_index(inplace=True)
```
### Set Columns
```python
df.columns

# Create a new list of column names
new_columns_name = ["customer_id", "phone", "addressline", "city"]

# Update column name
df.columns = new_columns_name
```

Related: [[Series]], [[DataFrame]], [[Data Selection]]

