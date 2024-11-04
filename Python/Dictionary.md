*mutable, but keys are immutable and do not allow duplicate keys*

```python
D = {}            # create empty dictionary
D = dict()
```

Dictionary method

| operation | syntax                           | output                                  |
| --------- | -------------------------------- | --------------------------------------- |
|           | D = {'name':'Daniel', 'age': 25} |                                         |
| keys      | D.keys()                         | 'name', 'age'                           |
| values    | D.values()                       | 'Daniel', 25                            |
| items     | D.items                          | (key, value)                            |
| len       | len(D)                           | 2                                       |
| get       | D['name']                        | 'Daniel'                                |
|           | D.get('name')                    | 'Daniel'                                |
| add       | D['job'] = 'Dev'                 | 'name':'Daniel', 'age': 25, 'job':'Dev' |
| update    | D.update(D2)                     | similar like append in list             |
| delete    | del(D['job'])                    | 'name':'Daniel', 'age': 25              |
| pop       | D.pop('job')                     | 'name':'Daniel', 'age': 25              |
| in        | 'name' in D                      | True                                    |
| copy      | D2 = D.copy()                    | create duplicate, D2                    |
| clear     | D.clear()                        | {}, delete all                          |

Loop
```python
D = {'name':'Daniel', 'age': 25}

# Get key
for key in D:                     # only key
	print(key)

# Get value
for key in D:                     # only value
	print(D[key])

for key, value in D.items():      # unpack: key, value
	print(f"{key} : {value}")     # .values(), .keys()
```

Combine two Lists
```python
L1 = ['Name', 'Age', 'City']
L2 = ['Daniel', 25, 'Jakarta']

D = dict(zip(L1, L2))
```
