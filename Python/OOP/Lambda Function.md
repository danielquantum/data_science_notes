*anonymous function*

```python
square = lambda x: x**2
```

```python
discount_price = lambda amount, price, discount: (amount*price) - (amount*price*discount/100)

discount_price(2, 10_000, 15)
```

```python
day_off = lambda overtime, offday: print("You can have day off") if overtime >= 8 and offday < 4 else print("You can't have day off")

cuti(8, 3)
```