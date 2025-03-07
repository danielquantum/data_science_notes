## General
```python
import pandas as pd

df2 = df.copy()          # copy dataframe to a new one

# Set display limits
pd.set_option('display.max_columns', len(df.columns))    # adjust display columns
pd.set_option('display.max_rows', len(df))               # adjust display rows
```

## Data Exploration
```python
df.info()                # Display df summary (non-null counts, dtypes)
df.describe()            # Summary statistics for numerical columns

# Summary for all columns, transposed for better readability
df.describe(include='all').T  

df.isnull().sum()        # Check for missing values in each column

df.dtypes                # Display data types of each column
df.columns               # List all column names
df.values                # Get the values
df.index                 # Get indexes
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

Related: [[Input & Output]], [[Combining Dataset]], [[Index & Columns]], [[Data Selection]], [[Data Cleaning]], [[Data Manipulation]], [[Parsing Dates]], [[Pandas Data Structure]]
