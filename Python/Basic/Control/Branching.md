***control flow**: break, continue, pass*

simple branching
```python
x = int(input('Enter an integer:'))
if x % 2 == 0:
	print(f"{x} is even")
else:
	print(f"{x} is odd")
```

advance branching
```python
x = int(input('Enter your math exam score:'))
if x >= 80:
	print("You got A")
elif x >= 70:
	print("You got B")
elif x >= 60:
	print("You got C")
elif x >=50:
	print("You got D")
else:
	print("Failled")
```

*pass*
```python
if h > 70:
	print("Turn on the alarm")
else:
	pass
```