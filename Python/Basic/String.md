*immutable, allow duplicate*

Operation
```python
'ab' + 'cd'   # 'abcd'
'ab' * 3      # 'ababab' 
```

Indexing
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
s.find('T')        # return index of 'T'
s.replace('T','b') # 'bitle' 
```

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
