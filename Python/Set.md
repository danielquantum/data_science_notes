*mutable, do not allow duplicate (unique)*

```python
S = set()       # create empty set
not with D = {} # will create empty dictionary         
```

Set method
S1 = {3, 4, 5, 6}
S2 = {1, 2, 3, 6}

| operation    | syntax              | output          |
| ------------ | ------------------- | --------------- |
| len          | len(S1)             | 4               |
| in           | 3 in S1             | True            |
| add          | S1.add(7)           | {3,4,5,6,7}     |
| update       | S1.add(S2)          | {1,2,3,4,5,6,7} |
| discard      | S2.discard(6)       | {1,2,3}         |
| union        | S1.union(S2)        | {1,2,3,4,5,6,7} |
| intersection | S1.intersection(S2) | {3,6}           |
