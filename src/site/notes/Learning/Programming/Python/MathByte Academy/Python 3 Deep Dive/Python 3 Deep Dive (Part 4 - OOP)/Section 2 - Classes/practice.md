---
{"dg-publish":true,"permalink":"/learning/programming/python/math-byte-academy/python-3-deep-dive/python-3-deep-dive-part-4-oop/section-2-classes/practice/","dg-note-properties":{}}
---


# Python Classes - Practice Questions 🐍

```dataviewjs
const currentFile = dv.current();
const content = await dv.io.load(currentFile.file.path);
const lines = content.split('\n');

// Regex to find: ## Question X: Name (Status, Date)
const regex = /^##\s*(Question\s*\d+[:\s][^(\n]+)(?:\s*\(([^,]+),([^)]+)\))?/;

const tableData = lines
    .map(line => line.match(regex))
    .filter(match => match !== null)
    .map(match => {
        const fullHeading = match[0].replace(/^##\s*/, '').trim(); // Exact text for the link
        const questionText = match[1].trim();
        const status = match[2] ? match[2].trim() : "❌ Pending";
        const date = match[3] ? match[3].trim() : "N/A";

        // Create a link to the heading: [[Note Name#Heading Text|Display Text]]
        const questionLink = `[[${currentFile.file.name}##${fullHeading}|${questionText}]]`;

        return [dv.sectionLink(currentFile.file.path, fullHeading, false, questionText), status, date];
    });

dv.table(["Question", "Status", "Completed On"], tableData);
```

## Question 1: Class vs Instance Attributes (✅, 11/02/2026)



```python
# Create a class called 'Student' with:
# - A class attribute 'school' set to "Python Academy"
# - Instance attributes: name, grade
# - Add a method to display student info

# WRITE YOUR CODE HERE


# Test:
# s1 = Student("Alice", 10)
# s2 = Student("Bob", 11)
# print(s1.school)  # Should print "Python Academy"
# print(s1.info())  # Should print "Alice is in grade 10"
```

---
dg-publish: true

## Question 2: Basic Initialization
```python
# Create a 'Book' class with __init__ method
# Attributes: title, author, year
# Add a method that returns "Title by Author (Year)"

# WRITE YOUR CODE HERE


# Test:
# book = Book("1984", "George Orwell", 1949)
# print(book.info())  # Should print "1984 by George Orwell (1949)"
```

---

## Question 3: Getters and Setters (without property)
```python
# Create a 'Temperature' class
# - Private attribute: _celsius
# - Getter method: get_celsius()
# - Setter method: set_celsius(value) - validate value is number and >= -273.15
# - Method: to_fahrenheit() returns (celsius * 9/5) + 32

# WRITE YOUR CODE HERE


# Test:
# temp = Temperature(25)
# print(temp.get_celsius())  # 25
# print(temp.to_fahrenheit())  # 77.0
# temp.set_celsius(30)
# print(temp.get_celsius())  # 30
# temp.set_celsius(-300)  # Should print error or not set
```

---

## Question 4: Property Decorators
```python
# Rewrite the Temperature class from Question 3 using @property and @.setter
# Make celsius a property with validation

# WRITE YOUR CODE HERE


# Test:
# temp = Temperature(25)
# print(temp.celsius)  # 25
# temp.celsius = 30
# print(temp.celsius)  # 30
# temp.celsius = -300  # Should raise ValueError
```

---

## Question 5: Computed Properties
```python
# Create a 'Rectangle' class
# Attributes: width, height (use properties with validation - positive numbers)
# Computed property: area (calculate on demand)
# Computed property: perimeter (calculate on demand)

# WRITE YOUR CODE HERE


# Test:
# rect = Rectangle(5, 3)
# print(rect.area)  # 15
# print(rect.perimeter)  # 16
# rect.width = 10
# print(rect.area)  # 30
```

---

## Question 6: Cached Computed Property
```python
# Create a 'BankAccount' class
# Attributes: balance, interest_rate (as decimal, e.g., 0.05 for 5%)
# Computed property: interest - calculates balance * interest_rate
# Cache the interest value and recalculate only when balance or rate changes
# (Hint: Use a setter for balance and rate to invalidate cache)

# WRITE YOUR CODE HERE


# Test:
# acc = BankAccount(1000, 0.05)
# print(acc.interest)  # 50.0 (calculates)
# print(acc.interest)  # 50.0 (uses cache)
# acc.balance = 2000
# print(acc.interest)  # 100.0 (recalculates)
```

---

## Question 7: Class Methods
```python
# Create a 'Car' class with:
# - Class attribute: total_cars (counts all instances created)
# - Instance attributes: make, model
# - Class method: show_total() returns "Total cars: X"
# - Class method: from_string(cls, string) creates Car from "make,model"
# - Instance method: info() returns "make model"

# WRITE YOUR CODE HERE


# Test:
# car1 = Car("Toyota", "Camry")
# car2 = Car("Honda", "Civic")
# print(Car.show_total())  # Total cars: 2
# car3 = Car.from_string("Ford,Mustang")
# print(car3.info())  # Ford Mustang
# print(Car.show_total())  # Total cars: 3
```

---

## Question 8: Static Methods
```python
# Create a 'MathUtils' class with static methods:
# - is_even(number) returns True/False
# - factorial(n) returns n! (use loop, not recursion)
# - fibonacci(n) returns nth fibonacci number

# WRITE YOUR CODE HERE


# Test:
# print(MathUtils.is_even(4))  # True
# print(MathUtils.factorial(5))  # 120
# print(MathUtils.fibonacci(7))  # 13
```

---

## Question 9: Deleter Property
```python
# Create a 'User' class with:
# - Private attribute: _password
# - Property: password (getter returns hidden version: "****")
# - Setter: password (store the password)
# - Deleter: password (set _password to None and print "Password removed")

# WRITE YOUR CODE HERE


# Test:
# user = User()
# user.password = "secret123"
# print(user.password)  # ****
# del user.password  # Should print "Password removed"
# print(user.password)  # None (or maybe AttributeError depending on design)
```

---

## Question 10: Scope Challenge
```python
# What will this code print? Don't run it - figure it out!

name = "Global"

class ScopeTest:
    name = "Class"
    
    list1 = [name] * 2
    list2 = [name for _ in range(2)]
    
    @classmethod
    def class_method(cls):
        return name
    
    @staticmethod
    def static_method():
        return name
    
    def instance_method(self):
        return name

test = ScopeTest()
print(ScopeTest.list1)      # ???
print(ScopeTest.list2)      # ???
print(ScopeTest.class_method())  # ???
print(ScopeTest.static_method()) # ???
print(test.instance_method())    # ???

# Write your answers here:
# 
# 
```

---

## Question 11: Build a Simple Bank System
```python
# Create a 'Bank' class that manages multiple accounts
# Requirements:
# 1. Account class (inner/nested class or separate - your choice)
#    - Attributes: account_number, owner, balance (private)
#    - Properties: balance (getter only), deposit(), withdraw()
# 2. Bank class:
#    - Add account (owner, initial deposit)
#    - Find account by number
#    - List all accounts
#    - Total deposits across all accounts

# WRITE YOUR CODE HERE


# Test:
# bank = Bank()
# acc1 = bank.create_account("Alice", 1000)
# acc2 = bank.create_account("Bob", 500)
# print(acc1.balance)  # 1000
# acc1.deposit(200)
# print(acc1.balance)  # 1200
# acc1.withdraw(100)
# print(acc1.balance)  # 1100
# print(bank.total_deposits())  # 1600
# found = bank.find_account(acc1.account_number)
# print(found.owner)  # Alice
```

---

## Question 12: Fix the Bug
```python
# This code has a bug. Find and fix it:

class Counter:
    count = 0
    
    def __init__(self):
        self.count += 1  # Bug here!
    
    @classmethod
    def show_count(cls):
        return f"Count: {cls.count}"

# Test:
c1 = Counter()
c2 = Counter()
c3 = Counter()
print(Counter.show_count())  # Should be "Count: 3", but it's not

# What's wrong? Fix the code.
```

---

## Answers (Try first, then check!)

<details>
<summary>Click for Question 1 Solution</summary>

```python
class Student:
    school = "Python Academy"
    
    def __init__(self, name, grade):
        self.name = name
        self.grade = grade
    
    def info(self):
        return f"{self.name} is in grade {self.grade}"

s1 = Student("Alice", 10)
s2 = Student("Bob", 11)
print(s1.school)  # Python Academy
print(s1.info())  # Alice is in grade 10
```
</details>

<details>
<summary>Click for Question 3 Solution</summary>

```python
class Temperature:
    def __init__(self, celsius):
        self.set_celsius(celsius)
    
    def get_celsius(self):
        return self._celsius
    
    def set_celsius(self, value):
        if not isinstance(value, (int, float)):
            print("Temperature must be a number")
            return
        if value < -273.15:
            print("Temperature cannot be below absolute zero")
            return
        self._celsius = value
    
    def to_fahrenheit(self):
        return (self._celsius * 9/5) + 32

temp = Temperature(25)
print(temp.get_celsius())  # 25
print(temp.to_fahrenheit())  # 77.0
temp.set_celsius(-300)  # Temperature cannot be below absolute zero
```
</details>

<details>
<summary>Click for Question 4 Solution</summary>

```python
class Temperature:
    def __init__(self, celsius):
        self._celsius = None
        self.celsius = celsius  # Use property setter
    
    @property
    def celsius(self):
        return self._celsius
    
    @celsius.setter
    def celsius(self, value):
        if not isinstance(value, (int, float)):
            raise ValueError("Temperature must be a number")
        if value < -273.15:
            raise ValueError("Temperature cannot be below absolute zero")
        self._celsius = value
    
    def to_fahrenheit(self):
        return (self._celsius * 9/5) + 32
```
</details>

<details>
<summary>Click for Question 6 Solution</summary>

```python
class BankAccount:
    def __init__(self, balance, interest_rate):
        self._balance = balance
        self._interest_rate = interest_rate
        self._interest_cache = None
    
    @property
    def balance(self):
        return self._balance
    
    @balance.setter
    def balance(self, value):
        self._balance = value
        self._interest_cache = None  # Invalidate cache
    
    @property
    def interest_rate(self):
        return self._interest_rate
    
    @interest_rate.setter
    def interest_rate(self, value):
        self._interest_rate = value
        self._interest_cache = None  # Invalidate cache
    
    @property
    def interest(self):
        if self._interest_cache is None:
            print("Calculating interest...")
            self._interest_cache = self._balance * self._interest_rate
        return self._interest_cache
```
</details>

<details>
<summary>Click for Question 7 Solution</summary>

```python
class Car:
    total_cars = 0
    
    def __init__(self, make, model):
        self.make = make
        self.model = model
        Car.total_cars += 1
    
    @classmethod
    def show_total(cls):
        return f"Total cars: {cls.total_cars}"
    
    @classmethod
    def from_string(cls, string):
        make, model = string.split(",")
        return cls(make.strip(), model.strip())
    
    def info(self):
        return f"{self.make} {self.model}"
```
</details>

<details>
<summary>Click for Question 10 Solution</summary>

```python
# Output:
# ['Class', 'Class']  # list1 - class scope
# ['Global', 'Global']  # list2 - comprehension uses module scope
# 'Global'  # class_method - uses module scope
# 'Global'  # static_method - uses module scope
# 'Global'  # instance_method - uses module scope
```
</details>

<details>
<summary>Click for Question 12 Solution</summary>

```python
class Counter:
    count = 0
    
    def __init__(self):
        Counter.count += 1  # Fix: use class name, not self
        # Or: type(self).count += 1
    
    @classmethod
    def show_count(cls):
        return f"Count: {cls.count}"

# self.count += 1 creates an INSTANCE attribute called 'count'
# that masks the class attribute. Use Counter.count or cls.count!
```
</details>

---

**Want more questions on a specific topic? Let me know!** 🚀