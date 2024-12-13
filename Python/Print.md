## Text
*use*: `' '` or `" "` or `''' '''`
```python
print("Hello World!")
```

## Number
*use*: `_` for readability
```python
print(3_000)                       # 3000

num = 3_000
print(f"The price is {num:,.2f}") # 3,000.00
```

## Formatting
```python
name = 'Daniel'
number = 19.500

# f-string (preferred)
print(f"Hello {name}, my number is {number:.2f}!") # 2 decimal places

# Using str.format
print("Hello {}, my number is {}".format(name, number))
print("Hello {0}, my number is {1}".format(name, number))

# Using old-style string formatting (not recommended)
print("Hello %s, my number is %d" % (name, number))
```

| Option | Description |
| ------ | ----------- |
| \n     | New line    |
| \t     | Tab         |
[Reference for Printing format](https://www.w3schools.com/python/ref_string_format.asp)

## Tabulate
```python
from tabulate import tabulate

data = {"Key": ["A", "B", "C"], "Value": [1, 2, 3]}  # Example dictionary

print(tabulate(data, headers='keys', tablefmt='github', stralign="center"))

```
