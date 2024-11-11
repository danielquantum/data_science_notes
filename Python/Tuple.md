*immutable, allow duplicate*

```python
t = ()                 # create empty tuple
t = tuple()
```

```python
t = (2, 5, 3.14)       # tuple
t[0]                   # 2
t[0:3]                 # 2, 5, 3.14
```

```python
a, b, c = (2, 3, 4)    # unpacking tuple
```

Tuple method

|          | symbol         | output             |
| -------- | -------------- | ------------------ |
| len      | len(t)         | 3                  |
| in       | 2 in t         | True               |
| index    | t.index(3.14)  | 2                  |
| count    | t.count(5)     | 1                  |
| addition | t1 = t + (4,5) | (2, 5, 3.14, 4, 5) |
| sorted   | ts = sorted(t) | (2, 3.14, 4, 5, 5) |
| min      | min(t)         | 2                  |
| max      | max(t)         | 5                  |

If
```python
t = (2, 5, 3.14)
if 3.14 in t:
	print("3.14 is in t")
```

Loop
```python
t = (1, 2, 3)
for i in t:
	print(i)
```
