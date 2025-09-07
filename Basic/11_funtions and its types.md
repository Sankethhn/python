### **1. Basics of Functions**

A function is a reusable block of code that performs a specific task when called. Functions are useful to organize code, make it reusable, and reduce redundancy.

---

### **2. Defining a Function**

You define a function using the `def` keyword followed by the function name, parentheses, and a colon `:`.

#### **Syntax**:
```python
def function_name(parameters):
    # Block of code
```

#### **Example**: Basic function to greet a user
```python
def greet():
    print("Hello! Welcome to the Python course.")
greet()
```

**Output**:
```
Hello! Welcome to the Python course.
```

---

### **3. Function Parameters**

Parameters are variables used to pass data into a function.

#### **Example**: Function with a parameter
```python
def greet_user(name):
    print(f"Hello, {name}! Welcome to the Python course.")

greet_user("Anand")
```

**Output**:
```
Hello, Anand! Welcome to the Python course.
```

---

### **4. Returning Values from a Function**

A function can return a value using the `return` keyword, which allows the output of the function to be reused elsewhere.

#### **Example**: Function that adds two numbers and returns the result
```python
def add_numbers(a, b):
    return a + b

result = add_numbers(10, 20)
print("The sum is:", result)
```

**Output**:
```
The sum is: 30
```

---

### **5. Default Parameter Values**

You can define a default value for a parameter, which is used if no argument is passed when the function is called.

#### **Example**: Function with a default parameter
```python
def greet(name="Student"):
    print(f"Hello, {name}! Welcome to the Python course.")

greet()  # Uses default value "Student"
greet("Geetha")  # Uses passed value "Geetha"
```

**Output**:
```
Hello, Student! Welcome to the Python course.
Hello, Geetha! Welcome to the Python course.
```
Here are the sections for **Nested Functions** and **Local/Global Variables**:

---

### **6. Local and Global Variables**

- **Local Variables** are defined inside a function and are only accessible within that function.
- **Global Variables** are defined outside all functions and are accessible from anywhere in the code.

#### **Example**: Local vs Global variables
```python
name = "Global Name"

def greet():
    name = "Local Name"
    print(name)

greet()  # Prints local variable
print(name)  # Prints global variable
```

**Output**:
```
Local Name
Global Name
```

In this example, the local variable `name` inside the function does not affect the global variable `name`.

### **Functions - Advanced Concepts**

In this part, we'll explore more advanced function concepts, including recursion, lambda functions, and variable-length arguments.

---

### **1. Keyword Arguments**

With keyword arguments, you can pass values to a function by specifying the parameter names.

#### **Example**:
```python
def display_info(name, age):
    print(f"Name: {name}, Age: {age}")

display_info(age=25, name="Kumar")
```

**Output**:
```
Name: Kumar, Age: 25
```

---

### **2. Variable-Length Arguments**

You can use `*args` and `**kwargs` to accept a variable number of arguments in a function.

#### **Example**: Using `*args`
```python
def total_sum(*numbers):
    result = 0
    for num in numbers:
        result += num
    return result

print(total_sum(1, 2, 3, 4))
```

**Output**:
```
10
```

#### **Example**: Using `**kwargs`
```python
def student_info(**details):
    for key, value in details.items():
        print(f"{key}: {value}")

student_info(name="Anand", age=22, course="Python")
```

**Output**:
```
name: Anand
age: 22
course: Python
```

---

### **3. Lambda Functions**

A **lambda function** is a small anonymous function that can take any number of arguments but has only one expression.

#### **Syntax**:
```python
lambda arguments: expression
```

#### **Example**: Lambda function to double a number
```python
double = lambda x: x * 2
print(double(5))
```

**Output**:
```
10
```

---

### **4. Recursion**

Recursion occurs when a function calls itself. It's used to solve problems that can be broken down into smaller, similar problems.

#### **Example**: Recursive function to calculate factorial
```python
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n - 1)

print(factorial(5))
```

**Output**:
```
120
```
Here are the sections for **Nested Functions** and **Local/Global Variables**:

---

### **5. Nested Functions**

A **nested function** is a function defined inside another function. The inner function is only accessible within the outer function, allowing for more modular and controlled code execution.

#### **Example**: Nested function in Python
```python
def outer_function(name):
    def inner_function():
        print(f"Hello, {name}!")
    inner_function()

outer_function("Anand")
```

**Output**:
```
Hello, Anand!
```

In this example, the `inner_function()` is called within `outer_function()` and uses the `name` parameter of the outer function.

---

### **Homework**:
1. **Lambda Function**: Write a lambda function that multiplies two numbers.
2. **Recursive Function**: Write a recursive function that calculates the sum of the first `n` numbers.
3. **Variable-Length Arguments**: Write a function that accepts any number of arguments and returns their average.

