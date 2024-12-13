try-except example
```python
try:
    result = 10 / 0  # Code that might raise an exception
except ZeroDivisionError as e:
    print(f"Error occurred: {e}")  # Handling the specific exception

```

raise example
```python
def check_number(num):
    if num < 0:
        raise ValueError("Number must be positive!")  # Raise an exception manually
    return num

try:
    check_number(-5)
except ValueError as e:
    print(f"Caught an error: {e}")

```

finally example
```python
try:
    file = open("example.txt", "r")
    data = file.read()
except FileNotFoundError as e:
    print(f"File not found: {e}")
finally:
    print("This block always executes, whether an exception occurred or not.")

```
