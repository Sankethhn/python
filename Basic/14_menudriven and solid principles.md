# **Menu-Driven Programs in Python**

### **Introduction**

- A **menu-driven program** is a program that allows users to interact by choosing options from a menu.
- These programs are commonly used in applications such as banking systems, shopping carts, or command-line utilities.
- Menu-driven programs are typically implemented using loops and conditional statements (`if-elif-else`).

---

### **Why Use Menu-Driven Programs?**

1. **Interactive**: Provides a user-friendly way to interact with programs.
2. **Reusable**: Can be easily modified or extended by adding new menu options.
3. **Efficient**: Reduces the need for users to remember commands by presenting them with a list of options.

---

### **Steps to Create a Menu-Driven Program**

1. **Display the Menu**: Use `print()` statements to display a list of options.
2. **Take User Input**: Use `input()` to capture the user's choice.
3. **Process the Choice**: Use conditional statements to execute actions based on the user's input.
4. **Repeat Until Exit**: Use a loop (`while`) to keep displaying the menu until the user chooses to exit.

---

### **Basic Structure of a Menu-Driven Program**

```python
def menu():
    print("Welcome to the Menu-Driven Program!")
    print("1. Option 1")
    print("2. Option 2")
    print("3. Option 3")
    print("4. Exit")

while True:
    menu()
    choice = input("Enter your choice (1-4): ")
    
    if choice == '1':
        print("You selected Option 1.")
    elif choice == '2':
        print("You selected Option 2.")
    elif choice == '3':
        print("You selected Option 3.")
    elif choice == '4':
        print("Exiting the program. Goodbye!")
        break
    else:
        print("Invalid choice. Please try again.")
```

---

### **Detailed Example**

#### **Scenario: Simple Calculator**

A menu-driven program to perform basic arithmetic operations.

```python
def menu():
    print("\nSimple Calculator")
    print("1. Addition")
    print("2. Subtraction")
    print("3. Multiplication")
    print("4. Division")
    print("5. Exit")

while True:
    menu()
    choice = input("Enter your choice (1-5): ")

    if choice in ['1', '2', '3', '4']:
        # Get two numbers from the user
        try:
            num1 = float(input("Enter the first number: "))
            num2 = float(input("Enter the second number: "))
        except ValueError:
            print("Invalid input! Please enter numeric values.")
            continue

    if choice == '1':
        print(f"Result: {num1} + {num2} = {num1 + num2}")
    elif choice == '2':
        print(f"Result: {num1} - {num2} = {num1 - num2}")
    elif choice == '3':
        print(f"Result: {num1} * {num2} = {num1 * num2}")
    elif choice == '4':
        if num2 == 0:
            print("Error: Division by zero is not allowed.")
        else:
            print(f"Result: {num1} / {num2} = {num1 / num2}")
    elif choice == '5':
        print("Exiting the calculator. Goodbye!")
        break
    else:
        print("Invalid choice. Please select a valid option.")
```

---

### **Key Points to Note**

1. **Input Validation**:
   - Ensure user input is valid to prevent runtime errors.
   - Example: Check if the user enters a number when required.

2. **Exit Condition**:
   - Use a specific option (e.g., 4 or 5) to allow users to exit the program gracefully.

3. **Error Handling**:
   - Handle cases like division by zero or invalid inputs using `try` and `except`.

4. **Reusability**:
   - Define a separate function for the menu to avoid repeating code.

# **SOLID Principles in Python**

The **SOLID** principles are five guidelines that help us write **clean, maintainable, and scalable object-oriented code**. These are best practices followed by experienced developers to make code better.

> 🎯 **S** – Single Responsibility Principle
> 🎯 **O** – Open/Closed Principle
> 🎯 **L** – Liskov Substitution Principle
> 🎯 **I** – Interface Segregation Principle
> 🎯 **D** – Dependency Inversion Principle

We’ll go through each one with simple, beginner-friendly examples.

---

## ✅ **1. Single Responsibility Principle (SRP)**

**Definition**: A class should have only **one reason to change**. That means, a class should do only **one job**.

### ❌ Bad Example:

```python
class Student:
    def __init__(self, name):
        self.name = name

    def save_to_database(self):
        print("Saving to database...")

    def generate_report_card(self):
        print("Generating report card...")
```

> This class is handling both **data storage** and **report generation**. Too many responsibilities!

---

### ✅ Good Example:

```python
class Student:
    def __init__(self, name):
        self.name = name

class StudentDatabase:
    def save(self, student):
        print(f"Saving {student.name} to database...")

class ReportCard:
    def generate(self, student):
        print(f"Generating report card for {student.name}...")
```

> Now each class has **one job**: Student handles data, StudentDatabase saves, ReportCard generates.

---

## ✅ **2. Open/Closed Principle (OCP)**

**Definition**: Software entities (classes, functions, etc.) should be **open for extension but closed for modification**.

### ❌ Bad Example:

```python
class Discount:
    def get_discount(self, customer_type):
        if customer_type == "regular":
            return 10
        elif customer_type == "premium":
            return 20
```

> If we add a new customer type (e.g., VIP), we need to modify this class.

---

### ✅ Good Example:

```python
class Discount:
    def get_discount(self):
        return 0

class RegularCustomer(Discount):
    def get_discount(self):
        return 10

class PremiumCustomer(Discount):
    def get_discount(self):
        return 20
```

> You can now add more customer types by **extending**, not modifying the existing code.

---

## ✅ **3. Liskov Substitution Principle (LSP)**

**Definition**: Subclasses should be able to **replace their parent class** without breaking the program.

### ❌ Bad Example:

```python
class Bird:
    def fly(self):
        print("Flying...")

class Penguin(Bird):
    def fly(self):
        raise NotImplementedError("Penguins can't fly")
```

> Penguin violates LSP because it **can’t actually replace Bird**.

---

### ✅ Good Example:

```python
class Bird:
    def move(self):
        pass

class Sparrow(Bird):
    def move(self):
        print("Flying...")

class Penguin(Bird):
    def move(self):
        print("Swimming...")
```

> Now, both follow LSP because they behave correctly when used as a Bird.

---

## ✅ **4. Interface Segregation Principle (ISP)**

**Definition**: Don’t force a class to **implement methods it does not use**.

Python doesn’t have interfaces like Java/C#, but we can still follow this idea using base classes.

### ❌ Bad Example:

```python
class Worker:
    def work(self):
        pass

    def eat(self):
        pass

class Robot(Worker):
    def eat(self):
        raise NotImplementedError("Robots don't eat")
```

> Robot shouldn’t be forced to have `eat()`.

---

### ✅ Good Example:

```python
class Workable:
    def work(self):
        pass

class Eatable:
    def eat(self):
        pass

class Human(Workable, Eatable):
    def work(self):
        print("Human working")

    def eat(self):
        print("Human eating")

class Robot(Workable):
    def work(self):
        print("Robot working")
```

> Now, each class only implements the methods it **really needs**.

---

## ✅ **5. Dependency Inversion Principle (DIP)**

**Definition**: High-level modules should not depend on low-level modules. Both should depend on **abstractions**.

### ❌ Bad Example:

```python
class Keyboard:
    def input(self):
        return "User typing..."

class Computer:
    def __init__(self):
        self.keyboard = Keyboard()

    def get_input(self):
        return self.keyboard.input()
```

> `Computer` is **tightly coupled** to `Keyboard`.

---

### ✅ Good Example:

```python
class InputDevice:
    def input(self):
        pass

class Keyboard(InputDevice):
    def input(self):
        return "User typing..."

class Mouse(InputDevice):
    def input(self):
        return "Mouse clicked"

class Computer:
    def __init__(self, device: InputDevice):
        self.device = device

    def get_input(self):
        return self.device.input()
```

> Now `Computer` depends on an **abstraction**, and you can switch the input device easily!

---

## 🧠 Summary Table

| Principle | What It Means                   | Example Tip                          |
| --------- | ------------------------------- | ------------------------------------ |
| SRP       | One class = One job             | Don’t mix save logic & display logic |
| OCP       | Extend, don’t modify            | Add new types via subclass           |
| LSP       | Subclasses must replace parents | Don’t break functionality            |
| ISP       | No unnecessary methods          | Use multiple small classes           |
| DIP       | Depend on abstraction           | Use base classes/interfaces          |

