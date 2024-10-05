*list, tuple, set, dictionary*

 ***control flow**:break, continue, pass*

if --> not effective in this case
```python
i = 0
if i < 5:
	print(i)
	i += 1
	if < 5:
		print(i)
		i += 1
		...
```

for --> when know to stop
```python
for i in 0,1,2,3,4:
	print(i)

for i in range(5):                      # star=0,end,step=1
	print(i)                            # 0,1,2,3,4

L = ['Surabaya', 'Malang', 'Bandung']
for i, val in enumerate(L):             # unpack i, val
	print(f"Index: {i}, Value: {val}")

for i, val in enumerate(L, start=10):   # start i from 10
	print(f"Index: {i}, Value: {val}")
```

while --> when know the condition to stop
```python
i = 0
while i < 5:            # 0,1,2,3,4
	print(i)
	i += 1
```

