```python
pd.set_option('display.max_columns', len(data.columns))
pd.set_option('display.max_rows', len(data))
```

```python
df.info()
df.describe()                             # df.describe(include='all').T
df.isnull().sum()
```
## Casting
```python
df.dtypes

df = df['qty'].astype(float)
df = df['type'].astype('category')
```

## Connect to a database
```python
# Import library to acces a database
import sqlite3

# create connection to database
con = sqlite3.connect("chinook.db")

# access invoice table
invoice = pd.read_sql("SELECT * from invoices", con)
invoice.head()
```
