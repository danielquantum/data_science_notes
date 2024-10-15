*reusable, encapsulation, structuring*
*variables: remain local*

print(): show in screen
return: store and return the operation inside function
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

**args**
*receive a flexible number of arguments*

```python
def sum_num(*nums):
	result = sum(nums)
	return result

sum_num(1,2,3,4,5)        # take 5 numbers
sum_num(1,2)              # take 2 numbers

def clients(*name):
	print(f"Clients: {name}")

clients('Daniel', 'Desis', 'Danielle', 'Daaron')
```


**kwargs**
*receive a flexible number of keyword arguments*

```python
def clients(**person):
	for key, value in person.items():
		print(f"{key}: {value}")

clients(name='Daniel', age=30)
```

Mix args and kwargs
```python
def mix(a, b, *c, **kwargs): 
	print(f"a: {a}, b: {b}")           # a = 1, b = 2
	print(f"args: {args}")             # c= 3, 4
	print(f"kwargs: {kwargs}")         # x = 5, y =6

mix(1, 2, 3, 4, x=5, y=6)
```