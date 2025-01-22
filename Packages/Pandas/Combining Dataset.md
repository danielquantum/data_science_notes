Concat 
- This can create duplicate columns

| item | qty | item | price |
| ---- | --- | ---- | ----- |
|      |     |      |       |

```python
df1 = pd.DataFrame({
    "item": ["Indomie", "Taro"],
    "qty": [5, 2]
    })

df2 = pd.DataFrame({
    "item": ["Good Day", "Deterjen", "Pasta gigi"],
    "qty": [1,1,1]
    })

df3 = pd.DataFrame({
    "item": ["Indomie", "Taro"],
    "price": [5000, 1000]
    })

df4 = pd.concat([df1, df2])             # on row
df4 = pd.concat([df1, df3], axis=1)     # on col, but 'item' col: duplicate 
```

Merge
- The default is an inner join, which includes only overlapping data. Use `on` to combine two data frames

| item | qty | price |
| ---- | --- | ----- |
|      |     |       |

```python
# Merge, default = 'inner'
pd.merge(df1, df2, on="item", how='left')      # 'left', 'right'/'outer', 'inner'
```

Join
- Key should be the index, default: left join

| item | qty | price |
| ---- | --- | ----- |
|      |     |       |

```python
# Create df1
df1 = pd.DataFrame({
    "item": ["Indomie", "Taro"],
    "qty": [5, 2]
    })
df1.set_index('item', inplace=True)
df1 = df1.set_index('item')                     # or you can use this command

# Create df2
df2 = pd.DataFrame({
    "item": ["Indomie", "Taro", "Pasta gigi"],
    "stock": [17,11,5]
    })
df2.set_index('nama_barang', inplace=True)

# Join
df1.join(df2)
```
