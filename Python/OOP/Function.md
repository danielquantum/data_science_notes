*reusable, encapsulation, structuring*
*variables: remain local*

```python
def mult(a, b):
	"""
	Perform multiplication       # Docstrings

	Parameter:
	a, b : int or float

	Output:
	c : int of float
	"""
	global c       # to make variable exist in global scope
	c = a*b
	return c
```


```python
menus = ['pizza', 'spaghetti', 'meat', 'fish', 'snacks']
days = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday']

def find_menu(day):
	if day in days:
		idx = days.index(day)
		menu = menus[idx]
		print(f"{day}: {menu}")
```

**arg**

**kwargs**