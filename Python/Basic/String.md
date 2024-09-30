*immutable, allow duplicate*

```python
s = ""        # create empty string
s = str()
```

Operation
```python
'ab' + 'cd'   # 'abcd'
'ab' * 3      # 'ababab' 
```

Indexing and slicing
```python
'daniel'[0]   # 'd'
'daniel'[-1]  # 'l'
'daniel'[0:4] # 'dani'
'daniel'[::2] # 'dne'

len('daniel') # 6
```

Comparison
```python
s = 'daniel'
if s == 'daniel':          # can also use '<' '>'
	print(True)
```

String method
```python
s = 'Title'
s = s.upper()              # 'TITLE'
s = s.lower()              # 'title'
s = s.capitalize()         # 'Title'
s = s.title()              # 'Title'
s = s.replace('T','b')     # 'bitle' 
s.count('e')               # 1
s.find('T')                # return index of 'T'
```
[Reference for string method](https://www.w3schools.com/python/python_ref_string.asp) , [Reference for string method](https://www.pythonmorsels.com/string-methods/) , [Reference for string method](https://www.pythonmorsels.com/string-methods/)


Loop on string
```python
for i in range(len(s)):
	print(s[i])
```
or
```python
for i in s:
	print(i)
```
