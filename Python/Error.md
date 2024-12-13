### Syntax error
syntax error
```python
print('Hello'           # Missing closing parenthesis (syntax error)

```

indentation error
```python
for i in range(10):
print(i)                # Incorrect indentation (indentation error)
```

### Exception error

| Nama Error        | Description                                                                  |
| ----------------- | ---------------------------------------------------------------------------- |
| AttributeError    | The object does not contain the specified variable or method                 |
| ImportError       | The `import` statement failed to locate the module, or the name is incorrect |
| IndexError        | The index is out of range for a sequence (list, string, tuple)               |
| KeyError          | The specified key does not exist in the dictionary                           |
| NameError         | The specified local or global variable does not exist                        |
| TypeError         | An operation or function is applied to an inappropriate type                 |
| ValueError        | An operation or function has a valid type but an inappropriate value         |
| ZeroDivisionError | The second operand in a division or modulus operation is zero                |

### Logical Error
Logical errors occur when the code runs without raising exceptions but produces incorrect or unexpected results due to flawed logic.