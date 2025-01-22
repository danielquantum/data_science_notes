### Data selection by index
iloc
- use index
```python
df.iloc[index_row, index_col]                # Like list, last num not included

# Save column indeces in a list
index_columns = [1,2,3,7,8]
df.iloc[0:7, index_columns]                  # Selecting specified columns
```

loc
- loc: use name, include the last index and col names
```python
df.loc['index_name', 'col_name']

# Access data with index row Peter to Susan from col: customerNumber to address
df.loc['Peter':'Susan', 'customerNumber':'address']
```

## Data selection by condition
```python
df['country'] == 'USA'                        # Return True and False

# Using loc
df.loc[df['country'] == 'USA']                # Select dataset using loc

# Without loc
df[df['country'] == 'USA']                    # Select dataset
df[df['country'] == 'USA'][['name', 'phone']] # Show only 'name' & 'phone' col
```

More than one condition:
- For every condition use: `( )`

| Python Operator | Vector Operator |
| --------------- | --------------- |
| _or_            | \|              |
| _and_           | &               |
| _not_           | ~               |
```python
# Access customer data where country is USA and credit limit > 70000
df[(df['country'] == 'USA') & (df['creditLimit'] > 70000) ]
```

## Slicing data with multiple index
- Make data selection by condition more easy with multiple index
```python
# Data selection by condition
df[(df["country"]== 'USA') & (df['city'] == 'NYC')]

# Slicing data with multiplex index
df = df.set_index(['country', 'city', 'name'])
df.loc['USA', 'NYC']

# When access all 'city'
df.loc['Singapore', slice(None), 'Daniel']
```