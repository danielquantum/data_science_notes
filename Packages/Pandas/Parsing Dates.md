Series
```python
series = pd.Series(['3/11/10', '3/12/10', '3/13/10'])
pd.to_datetime(series, dayfirst=True)                  # 'yearfirst'
```

From csv
```python
# Parse date
df = pd.read_csv('filename.csv', parse_dates=['Datetime'])
# Use 'Datetime' as index
df = pd.read_csv('filename.csv', parse_dates=['Datetime'],index_col=['Datetime'])
df.info()

# Plot
import seaborn as sns
sns.lineplot(data = df, x = "Datetime", y='col1')

# Extract 
df['date'] = df['Datetime'].dt.date
df['time'] = df['Datetime'].dt.time
df['day'] = df['Datetime'].dt.day
df['month'] = df['Datetime'].dt.month
df['year'] = df['Datetime'].dt.year
df['weekday'] = df['Datetime'].dt.weekday
df['day_name'] = df['Datetime'].dt.day_name()
df['dayofweek'] = df['Datetime'].dt.dayofweek

# Grouping 
df2 = df[["date", "col1"]].groupby("date").mean()
df2.reset_index(inplace=True)
# plot 
sns.lineplot(data=df2, x="date", y="col1")
```

Resampling Data

| Code | Description             |
| ---- | ----------------------- |
| MS   | monthly start frequency |
| M    | month end frequency     |
| D    | calendar day frequency  |
| B    | business day frequency  |
| W    | weekly frequency        |
| H    | hourly frequency        |
| T    | minutely frequency      |
| S    | secondly frequency      |
```python
# Downsampling (reduce sample) in day with aggregation
df2 = df.resample('D').mean()
# check number of index
df2.index[0]

# Upsampling (increase sample) every 10 minutes
df2.resample('10T').mean()[:10]
# Fill NaN with forward filling
df2.resample('10T').mean().ffill()
# Fill NaN with backward filling
df2.resample('10T').mean().bfill()
```