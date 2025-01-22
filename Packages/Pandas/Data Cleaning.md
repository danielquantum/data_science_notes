## Handling missing values
```python
# Identify missing value
df.isna() or df.isnull()
df.isna().sum()                           # Sum of missing value
df.isna().sum() / len(df) * 100           # Sum of missing value in %

# Check data types
df.dtypes
df["col_1"] = df["col_1"].astype("int64") # casting to int

# Imputation
# Calculate median/mean
med_col1 = df["col1"].median()
# Use mean as a filler
df["col1"] = df["col1"].fillna(med_col1)

# replace NaN and empty string with 0
df["col_1"] = df["col_1"].fillna(0)
df["col_1"] = df["col_1"].replace({" ": 0})

# For numerical discrite and categorical use mod (most freq number)
mod_num_bedrooms = df["num_bedrooms"].mode()[0]
df["num_bedrooms"] = df["num_bedrooms"].fillna(mod_num_bedrooms)
```
## Handling outliers
```python
# Identify outliers
import seaborn as sns
sns.histplot(data=df, x="col_1", bins=100)     # Histogram
sns.boxplot(data=df, x="col_1")                # Boxplot

# Data without outlier
# threshold
threshold = df["col_1"].quantile(q=0.75) * 1.5
# plot without outlier
df_without_outlier = df[df["col_1"] < threshold]
# plot col_1 witout outlier
sns.histplot(df_without_outlier["col_1"])

# Imputation
# threshold
threshold = df["col_1"].quantile(0.75) * 1.5
# Find median value
median = df["col_1"].median()
df.loc[df["col_1"] > threshold, "col_1"]= median
# histogram
sns.histplot(df["col_1"])
```
## Handling duplicates
```python
# Identify duplicate data
df.duplicated(keep=False)                       # Result True and False
df[df.duplicated(keep=False)]

# Handling duplicate data
df = df.drop_duplicates(keep='first')           # 'first', 'last', False
```
## Handling Inconsistency
```python
# Identify inconsistency
df["col1"].unique()
df["col1"].value_counts()

# Handling inconsistency
# mapping inconsistency to correct format
map_inconsistent = {
    "LXT" : "LEXINGTON",
    "berkeley" : "BERKELEY",
    "Berkeley" : "BERKELEY",
}
df["col1"] = df["col1"].replace(map_inconsistent)
```