*1D array*

```python
list_data = [5,2,1,1]
index_data = ['a','b','c','d']

series_data = pd.Series(list_data)                   # Create a series data
series_data = pd.Series(list_data, index=index_data) # Create a series w index
```

Indexing
```python
series_data['a']                                     # 5
series_data[:2]                                      # 5, 2
series_data[-3:]                                     # 2, 1, 1

# Update
series_data['a'] = 7                                 # 7,2,1,1

# Append
new_data = pd.Series([5,1], index = ['e','f'])
series_data = series_data.append(new_data)           # 7,2,1,1,5,1

# Delete
series_data = series_data.drop(['e','f'])            # 7,2,1,1

# Operation
series_data*3                                        # 21,6,3,3
```