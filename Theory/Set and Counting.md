### Set
```python
x_set = {1,2,3,4}
y_set = {3,4,5,6,7}

# Check membership
1 in x_set                        # True

# Add a new element
x_set.add(5)                      # {1,2,3,4,5}
# Remove
x_set.remove(2)                   # {1,3,4,5}
# Length of a set
len(x_set)                        # 4

# Intersection
x_set.intersection(y_set)         # {3,4,5}
x_set & y_set                     # {3,4,5}
# Union
x_set.union(y_set)                # {1,3,4,5,6,7}
x_set | y_set                     # {1,3,4,5,6,7}
# Difference
x_set.difference(y_set)           # {1}

# Subset
x_set.issubset(y_set)             # False
# Disjoint: check two sets do not have overlap elements
x_set.isdisjoint(y_set)           # False
# Superset 
x_set.issuperset(y_set)           # False 
```

### Venn Diagram
```python
import matplotlib.pyplot as plt
import matplotlib_venn as venn

S = {-1, 0, 1, 2, 3,4,5,7, 20,90}
A = {1, 2, 3,4,5}
B = {0, 2, -1, 5,7}
C = {20,90}
D = {100}

# Venn Diagram for sets above
venn.venn3([A, B, C], set_labels=('A','B', 'C'))
plt.show()
```

