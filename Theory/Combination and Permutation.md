
In Combination: $\{ \text{A, B} \} = \{ \text{B, A} \}$
In Permutation: $\{ \text{A, B} \} \neq \{ \text{B, A} \}$

### Permutation
- An arrangement of objects in a specific order. The order of selection matters in permutations

If you have `n` distinct objects and you want to arrange `k` of them in a sequence:
<center><img src="https://sekolahdata-assets.s3.ap-southeast-1.amazonaws.com/notebook-images/mds-probability/live_02_09.PNG" alt="Drawing" style="width: 100px;"/></center>

How many ways can you arrange 3 letters from {A, B, C, D}? 

${ P(4, 3) = \frac{4!}{(4-3)!} = \frac{4!}{1!} = \frac{4 \times 3 \times 2 \times 1}{1} = 24 }$

```python
from itertools import permutations
letters = {'A','H','L','O'}
perm = permutations(letters)

# Show all possible permutation
for i in list(perm):
    print(i)

# Only two letters
k = 2
perm_k = permutations(letters, k)
for i in list(perm_k):
    print(i)
```

### Combination
- a way of **selecting** objects where the **order does not matter**

If you have `n` distinct objects and you want to choose `r` of them without considering order:
<center><img src="https://sekolahdata-assets.s3.ap-southeast-1.amazonaws.com/notebook-images/mds-probability/live_02_10.PNG" alt="Drawing" style="width: 300px;"/></center>

```python
from itertools import combinations
friends = {'Joko', 'Budi', 'Seno'}
comb = combinations(friends,2)
for i in list(comb):
    print(i)
```


