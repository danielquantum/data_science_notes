## Series
*1D array*
 
 Create a series 
```python
# Approach 1
list_data = [5,2,1,1]
index_data = ['a','b','c','d']

# Create a series using a list
series_data = pd.Series(list_data)                   
# Create a series using a list with a custom index
series_data = pd.Series(list_data, index=index_data) 

# Approach 2
dict_data = {
    "IDMF":5, 
    "TROF":2, 
    "GODF":1, 
    "DETN":1
    }
# Create a series using a dictionary    
series_data = pd.Series(dict_data)                   
```

Operation
```python
# Using index
series_data['a']                                     # 5
series_data[['a','b']]                               # 5, 2

# Slicing
series_data[:2]                                      # 5, 2
series_data[-3:]                                     # 2, 1, 1
series_data[1:3]                                     # 2, 1

# Update
series_data['a'] = 7                                 # 7,2,1,1

# Append: will be depreciated in future version; use concat instead
new_data = pd.Series([5,1], index = ['e','f'])
series_data = series_data.append(new_data)           # 7,2,1,1,5,1

# Delete
series_data = series_data.drop(['e','f'])            # 7,2,1,1

# Mathematical Operation in Series data
series_data*3                                        # 21,6,3,3
```

## Dataframe
*2D array*

Create Dataframe
```python
# Dictionary
dict_data = {
    "item": ["Indomie", "Taro", "Good Day", "Detergen"],
    "type": ["food", "food", "food", "non-food"],
    "qty": [5, 2, 1, 1]
}

index_data = ["IDMF", "TROF", "GODF", "DETN"]

# Create a DataFrame using a dictionary
df = pd.DataFrame(dict_data)                          # default index
df = pd.DataFrame(dict_data, index=index_data)        # custom index
```

Operation
```python
df[['item']]                           # ['Indomie','Taro','Good Day','Detergen']

# Retrieve
df.loc[['index_name', 'col_name']]     # Retrieve cell value
df.loc[['index_name']]                 # Retrieve row
df.loc[:, ['col_name']]                # Retrieve column

# Update cell
df.loc["TROF","item"] = "Taro SW"      # 'Taro' --> 'Taro SW'

# Update row
df.loc["GODF"]=['GG Day','Food','3']   # 'GG Day','Food','3'

# Update column
df.loc[:,"qty"] = [5, 3, 2, 2]         # 5,3,2,2

# Append row: will be depreciated in future pandas version
new_row = pd.DataFrame({
    "item": "Pasta Gigi", 
    "type": "non-food", 
    "qty": 4}, 
    index=["PGIN"]
    )

# Add new_row to DataFrame
df = df.append(new_row)

# Append column
df["price"] = [2500, 6000, 9000, 4500, 12000]

# Delete row
df = df.drop(["PGIN"])

# Delete column
df = df.drop(["price"], axis=1)       # 0 for row, 1 for column 
```

Related: [[Import & Export]], [[Combining Dataset]], [[Set Index & Columns]], [[Data Selection]], [[Data Cleaning]], [[Data Manipulation]], [[Parsing Dates]]




