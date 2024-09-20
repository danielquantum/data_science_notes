*mutable, allow duplicate*
```python
L = []                # create empthy list
L = list()
```

Operation
```python
L = [1, 3, 5]         # list
L = L + [6, 7]        # [1, 3, 5, 6, 7]
L[-1]                 # 7
L[1:3]                # [3, 5]
```

List method

|         | symbol                 | output                    |
| ------- | ---------------------- | ------------------------- |
| len     | len(L)                 | 5                         |
| sum     | sum(L)                 | 22                        |
| count   | L.count(value)         | count #value              |
| in      | 1 in L                 | True                      |
| index   | L.index[value]         | index                     |
| extend  | L.extend([8, 9])       | [1, 3, 5, 6, 7, 8, 9]     |
| append  | L.append([8, 9])       | [1, 3, 5, 6, 7, [8, 9]]   |
| insert  | L.insert(index, value) | + index, value            |
| del     | del(L[0])              | [3, 5, 6, 7]              |
| remove  | L.remove(value)        | remove value              |
| pop     | L.pop(index)           | remove value with i index |
| sorted  | L2 = L.sorted()        | return new list           |
| sort    | L.sort()               | change directly           |
| reverse | L.reverse()            | change directly           |





Casting string to list
```python
"hard rock".split() # default by space: ["hard", "rock"]
list("hard rock")   # ['h','a','r','d',' ','r','o','c','k']
```

Clone vs aliasing
```python
L2 = L[:]           # copy
L2 = L              # alias
```

If
```python
if 3 in L:
	print("3 is in L")
```

List comprehension
```python
L = [1, 2, 3]
square = [i**2 for i in L]
```


