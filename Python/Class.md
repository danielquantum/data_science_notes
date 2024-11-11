*template/blue print: maintainability, reusability, scalability*

*naming: use capital letter* -> to differentiate between function and class

## **Attribute, Method, Instance**
```python
class BankAccount:
    # Class Attribute 
    domain = '@ddv.com'    # put class variable into class attribute

    # instance
    def __init__(self, acc_num, first_name, last_name, acc_balance):
        # instance attribute 
        self.acc_num = acc_num         # put instance var into instance att
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

## **Inheritance**
Method resolution order
```python
# Parent Class
class Animal():
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return "Animal:" + self.name
```

Approach I
```python
class Cat(Animal):
    def __init__(self, name, age):
        Animal.__init__(self, name)    # inherit from parent class
        self.age = age                 # new atribute
```

Approach II: use super()
super(): child class will inherit all attributes and methods from parent class
```python
class Cat(Animal):
    def __init__(self, name, age):
        super().__init__(name)         # keyword self is no needed
        self.age = age                 # new atribute 
```
