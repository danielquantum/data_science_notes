*immutable, allow duplicate*

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
if s == 'daniel':   # < >
	print(True)
```

String method
```python
s = 'Title'
s.upper()          # 'TITLE'
s.lower()          # 'title'
s.capitalize()     # 'Title'
s.title()          # 'Title'
s.count('e')       # 1
s.find('T')        # return index of 'T'
s.replace('T','b') # 'bitle' 
```
https://www.w3schools.com/python/python_ref_string.asp

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
