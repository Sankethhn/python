### **Introduction to OOP Concepts & Classes/Objects**

In this video, we will begin our journey into Object-Oriented Programming (OOP) with the foundational concepts of classes and objects.

---

### **1. What is Object-Oriented Programming (OOP)?**

- **OOP** is a programming paradigm that organizes software design around data, or objects, rather than functions and logic.
- It allows for better modularity and code reusability by creating objects that model real-world entities.

#### **Procedural vs Object-Oriented Programming**:
- **Procedural Programming**: Based on functions, where the main focus is on performing actions.
  - Example: Writing multiple functions to process data.
  
- **Object-Oriented Programming**: Based on objects and classes. The main focus is on objects (data) and the methods (functions) that manipulate this data.

---

### **2. Classes and Objects**

#### **Class**:
A class is a blueprint for creating objects. It defines the attributes and behaviors of the objects created from it.

#### **Object**:
An object is an instance of a class. Each object has its own attributes (data) and can perform actions through methods (functions).

#### **Example**:
```python
class Car:
    # Attributes
    def __init__(self, brand, model):
        self.brand = brand  # Instance variable
        self.model = model  # Instance variable

    # Method
    def display_info(self):
        print(f"Car Brand: {self.brand}, Model: {self.model}")

# Creating an object of the class
my_car = Car("Toyota", "Corolla")
my_car.display_info()
```

**Output**:
```
Car Brand: Toyota, Model: Corolla
```

Here:
- `Car` is the class.
- `my_car` is an object of the `Car` class.
- `brand` and `model` are attributes of the object.
- `display_info()` is a method that displays the car's details.

---

### **3. Attributes (Instance Variables) and Methods**

- **Attributes**: Characteristics that define an object. For example, in the `Car` class, `brand` and `model` are attributes.
- **Methods**: Functions defined inside a class that describe the behaviors of an object.

#### **Example**:
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")

# Creating objects
person1 = Person("Arjun", 30)
person2 = Person("Megha", 25)

person1.greet()
person2.greet()
```

**Output**:
```
Hello, my name is Arjun and I am 30 years old.
Hello, my name is Megha and I am 25 years old.
```

In this example:
- The `Person` class defines two attributes: `name` and `age`.
- The method `greet()` prints a greeting message using these attributes.

---

### **4. Creating Multiple Objects from a Class**

One of the main advantages of OOP is that you can create multiple objects from a class, each with its own unique attributes.

#### **Example**:
```python
class Dog:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed

    def bark(self):
        print(f"{self.name} is barking!")

# Creating multiple objects
dog1 = Dog("Rex", "Golden Retriever")
dog2 = Dog("Bolt", "Beagle")

dog1.bark()
dog2.bark()
```

**Output**:
```
Rex is barking!
Bolt is barking!
```

Here:
- `dog1` and `dog2` are different objects of the `Dog` class, each with its own `name` and `breed`.

- # **The Four Pillars of OOP**



### **1. Encapsulation**

- **Definition**: Encapsulation involves wrapping data and methods that operate on that data within one unit, such as a class. This protects the data from external interference and misuse, improving security and maintainability.
- **Real-World Example**: Imagine an **ATM machine**—you interact with a limited interface (e.g., withdraw, deposit, check balance) but do not have access to the inner mechanics or backend functions.
  
#### **Real-World Example in Code:**

```python
class ATM:
    def __init__(self, balance):
        self.__balance = balance  # Private attribute

    def deposit(self, amount):
        self.__balance += amount
        print(f"Deposited {amount}. New balance: {self.__balance}")

    def withdraw(self, amount):
        if amount <= self.__balance:
            self.__balance -= amount
            print(f"Withdrew {amount}. New balance: {self.__balance}")
        else:
            print("Insufficient balance")

atm = ATM(1000)
atm.deposit(500)
atm.withdraw(300)
```

Here, `__balance` is a private attribute, ensuring only the `deposit()` and `withdraw()` methods can modify it.

#### **Programming Example in Code**:

Consider a `User` class for storing login information:

```python
class User:
    def __init__(self, username, password):
        self.username = username
        self.__password = password  # Private attribute

    def get_username(self):
        return self.username

    def check_password(self, password):
        return password == self.__password

user = User("dev_karnataka", "pass1234")
print(user.get_username())  # Access allowed
print(user.check_password("wrong_pass"))  # Returns False
print(user.check_password("pass1234"))  # Returns True
```

Encapsulation here hides `__password` from direct access.

---

### **2. Abstraction**

- **Definition**: Abstraction hides the complex inner workings of an object, exposing only the essential parts for interaction.
- **Real-World Example**: Think about **driving a car**. You use the steering wheel and pedals to control the car, without needing to know the engine mechanics or braking systems.

#### **Real-World Example in Code:**

```python
class Car:
    def start_engine(self):
        print("Engine started")

    def accelerate(self):
        print("Car accelerating")

    def brake(self):
        print("Car stopping")

car = Car()
car.start_engine()  # Abstracts complex internal workings
car.accelerate()
car.brake()
```

Here, `Car` abstracts internal functions like ignition and fuel management, presenting only basic methods for interaction.

#### **Programming Example in Code**:

Using a `Database` class:

```python
class Database:
    def __init__(self):
        self.__storage = {}

    def save_data(self, key, value):
        self.__storage[key] = value
        print(f"Data saved for {key}")

    def get_data(self, key):
        return self.__storage.get(key, "No data found")

db = Database()
db.save_data("user_101", {"name": "Raj", "age": 30})
print(db.get_data("user_101"))
```

The user can store and retrieve data without needing to know the storage details.

---

### **3. Inheritance**

- **Definition**: Inheritance allows a class to inherit attributes and methods from another class, facilitating reuse.
- **Real-World Example**: Consider **human families**. Characteristics like surname, traditions, or physical features can be passed down from parents to children.

#### **Real-World Example in Code:**

```python
class Family:
    def __init__(self, surname):
        self.surname = surname

class Child(Family):
    def __init__(self, surname, name):
        super().__init__(surname)
        self.name = name

child = Child("Gowda", "Ajay")
print(f"{child.name} {child.surname}")  # Inherits surname from Family
```

The `Child` class inherits attributes of `Family`, showing that certain characteristics are “inherited.”

#### **Programming Example in Code**:

Consider an e-commerce application where an `Admin` has additional privileges over a basic `User`:

```python
class User:
    def __init__(self, username):
        self.username = username

    def login(self):
        print(f"{self.username} logged in")

class Admin(User):
    def delete_user(self, user):
        print(f"Admin {self.username} deleted user {user}")

admin = Admin("karnataka_admin")
admin.login()  # Inherited from User
admin.delete_user("user_102")  # Admin-specific method
```

Here, `Admin` inherits from `User` and gains additional functionality.

---

### **4. Polymorphism**

- **Definition**: Polymorphism allows objects of different classes to be treated as objects of a common superclass, but they can behave differently depending on the object type.
- **Real-World Example**: Think of **animals making sounds**—both dogs and cats make sounds, but each produces a distinct sound. They share a common method `make_sound()`, but the output varies.

#### **Real-World Example in Code:**

```python
class Animal:
    def make_sound(self):
        pass

class Dog(Animal):
    def make_sound(self):
        print("Bark")

class Cat(Animal):
    def make_sound(self):
        print("Meow")

animals = [Dog(), Cat()]
for animal in animals:
    animal.make_sound()
```

Each animal has a unique sound, demonstrating polymorphism.

#### **Programming Example in Code**:

Consider notifications in a social media app, where different types have the same `send()` method but behave uniquely:

```python
class Notification:
    def send(self):
        pass

class EmailNotification(Notification):
    def send(self):
        print("Sending Email")

class SMSNotification(Notification):
    def send(self):
        print("Sending SMS")

notifications = [EmailNotification(), SMSNotification()]
for notification in notifications:
    notification.send()
```

Each notification type behaves differently while sharing a common interface.

---
