## Text
*use*: ' ' or " " or ''' '''
```python
print("Hellow World!")
```

## Number
*use*: _ for readability
```python
print(3_000)                       # 3000

num = 3_000
print(f"The price is {numb:,.2f}") # 3,000.00
```

## Formatting
```python
name = 'Daniel'
number = 19.500
print(f"Hello {name}, my number is {number:.2f}!") # 2 dec

print("Hello {}, my number is {}".format{name, number})

print("Hello {0}, my number is {1}".format{name, number})

print("Hello %s, my number is %d"%{name, number})
```

| Option |          |
| ------ | -------- |
| \n     | new line |
| \t     | tab      |
[Reference for Printing format](https://www.w3schools.com/python/ref_string_format.asp)

## Tabulate
```python
from tabulate import tabulate
dict = {key: val}

print(tabulate(dict, headers='keys'))
```
