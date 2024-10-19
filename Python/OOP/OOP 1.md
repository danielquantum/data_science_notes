*maintainability, reusability, scalability*

*naming: use capital letter* -> to differentiate between function and class

```python
class BankAccount:
    # Attribute Class
    domain = '@ddv.com'

    # instance
    def __init__(self, acc_num, first_name, last_name, acc_balance):
        # attribute instance
        self.acc_num = acc_num
        self.first_name = first_name
        self.last_name = last_name
        self.full_name = f'{first_name} {last_name}'
        self.acc_balance = acc_balance
        self.email = f'{first_name.lower()}.{last_name.lower()}{self.domain}'

    # method
    def display(self):
        print(f'Account Information:')
        print(f'Name: {self.full_name}')
        print(f'Account number: {self.acc_num}')
        print(f'Account balance: {self.acc_balance:,.2f}')
        print(f'Email: {self.email}')
    
    def saving(self, amount):
        self.acc_balance = self.acc_balance + amount
    
    def withdraw(sef, amount):
        self.acc_balance = self.acc_balance - amount
```
