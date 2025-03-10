
## Index
Approach 1
```python
# Create new index start from 10 
new_index = [i for i in range(10,30)]   # Should have the same length

# Set index
customer_data.index                     # To see current index names
customer_data.index = new_index         # Replace current index with the new one
```

```python
# Change Index
df = df['id'].astype(integer)        # change to dtype integer
new_id = df['id'].values + 1000      # new index start from 1000
df.index = new_id                    # change current index with the new index
```

Approach 2
```python
# When reading dataset
df = pd.read_csv('filename.csv', index_col='col_name')
```

Approach 3
```python
# After importing dataset
df.set_index("col_name", inplace=True)
```

Reset the index
```python
df.reset_index(inplace=True)
```
## Columns
```python
# Create a new list of column names
new_columns_name = ["customer_id", "phone", "addressline", "city"]

# Update column name
df.columns                             # To see current col names
df.columns = new_columns_name          # Replace current column names with new ones

# Renaming columns
df.rename(columns={'customer_id': 'A', 'phone': 'B', 'addressline': 'C', 'city': 'D'}, inplace=True)

# Remove a column
df = df.drop(['id'], axis=1)         # delete column id
```

### Casting
```python
df = df['qty'].astype(float)
df = df['type'].astype('category')
```
### Operation
```python
# Mathematical operation
df["Col_1"] = df["Col_1"]/10       # *,/,+,-
```

