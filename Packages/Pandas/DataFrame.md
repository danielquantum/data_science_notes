
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

Operation
```python
df['item']                             # ['Indomie','Taro','Good Day','Detergen']

# Retrieve cell
df.loc[['IDMF', 'item']]               # 'Indomie'

# Retrieve row
df.loc[['IDMF']]                       # 'Indomie','food',5

# Retrieve coloumn
df.loc[[:, 'item']]                    # 'food','food','food','non-food'

# Update cell
df.loc["TROF","item"] = "Taro SW"      # 'Taro' --> 'Taro SW'

# Update row
df.loc["GODF"]=['GG Day','Food','3']   # 'GG Day','Food','3'

# Update column
df.loc[:,"amount"] = [5, 3, 2, 2]      # 5,3,2,2

# Append row
new_row = pd.DataFrame({
    "item": "Pasta Gigi", 
    "type": "non-food", 
    "amount": 4}, 
    index=["PGIN"]
    )

# Add new_row to DataFrame
df = df.append(new_row)

# Append coloumn
df["price"] = [2500, 6000, 9000, 4500, 12000]

# Delete row
df = df.drop(["PGIN"])

# Delete coloumn
df = df.drop(["price"], axis=1)
```