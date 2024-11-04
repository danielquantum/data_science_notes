*immutable, allow duplicate*

```python
s = ""        # create empty string
s = str()
```

Operation
```python
'ab' + 'cd'                # 'abcd'
'ab' * 3                   # 'ababab' 

# in
word = ['Daniel Smith']
'Daniel' in word           # True
```

Indexing and slicing
```python
'daniel'[0]                # 'd'
'daniel'[-1]               # 'l'
'daniel'[0:4]              # 'dani'
'daniel'[::2]              # 'dne'

len('daniel')              # 6
```

Comparison
```python
s = 'daniel'
if s == 'daniel':          # can also use '<' '>'
	print(True)
```

String method
```python
s = 'Title 2'
s = s.split()              # ['Title', 2]
s = s.upper()              # 'TITLE 2'
s = s.lower()              # 'title 2'
s = s.capitalize()         # 'Title 2'
s = s.title()              # 'Title 2'
s = s.replace('T','b')     # 'bitle 2'  
c = s.count('e')           # 1
i = s.find('T')            # return index of 'T'
i = s.index('T')           # 0
```
[Reference for string method](https://www.w3schools.com/python/python_ref_string.asp) , [Reference for string method](https://www.pythonmorsels.com/string-methods/) , [Reference for string method](https://www.pythonmorsels.com/string-methods/)

## Loop on string
```python
s = 'Daniel'
for i in range(len(s)):
	print(s[i])            # 'D','a','n','i','e','l'
```
or
```python
for i in s:
	print(i)
```

