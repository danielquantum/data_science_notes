### Using print() statements
```python
x = 10
y = 0
print(f"x: {x}, y: {y}")  # Debugging output
result = x / y            # Causes ZeroDivisionError
```

### Using `pdb` (python debugger)
- Python’s built-in debugger, `pdb`, allows you to set breakpoints and step through code interactively.

**Example: Setting a Breakpoint in Code**
```python
import pdb

pdb.set_trace()  # Start debugger here
x = 10
y = 5
result = x / y
print(f"Result: {result}")
```

**Or: Run Debugger from Command Line**
```bash
python -m pdb file.py
```


**Common Debugger Commands**:
- `n`: Execute the next line of code.
- `c`: Continue execution until the next breakpoint.
- `q`: Quit the debugger.
- `l`: List source code around the current line.
- `p <variable>`: Print the value of a variable.