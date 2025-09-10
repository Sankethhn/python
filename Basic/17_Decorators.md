# **Decorators in Python**

Decorators allow us to **modify the behavior** of a function **without changing its actual code**.

Think of it like **wrapping a dosa with chutney** — dosa (function) remains the same, but the outer layer (decorator) changes how it tastes (behaves)!


## 📌 Why Use Decorators?

* To **add extra functionality** to existing functions
* Used in **logging, timing, authentication, access control**, etc.
* Helps write **clean and reusable** code


## ✅ Functions are First-Class Citizens in Python

This means:

1. You can **pass functions as arguments**
2. You can **return functions from other functions**
3. You can **store them in variables**

## ⭐ `@decorator` Syntax

Python provides a shortcut for applying decorators using `@`.

```python
def welcome(func):
    def wrapper():
        print("Namaskara!")
        func()
        print("Take care!")
    return wrapper

@welcome
def intro():
    print("I am Chandan from Karnataka.")

intro()
```

## 📥 Decorator with Arguments

Let’s say we want to greet the person by name.

```python
def greet(func):
    def wrapper(name):
        print("Hello!")
        func(name)
        print("Have a nice day!")
    return wrapper

@greet
def say_name(name):
    print(f"My name is {name}")

say_name("Darshan")
```


## ✅ Decorator for Logging

```python
def logger(func):
    def wrapper():
        print(f"Function '{func.__name__}' is being called.")
        func()
    return wrapper

@logger
def greet():
    print("Hey there!")

greet()
```

## 🎯 Another Example

Let’s log when a user logs in:

```python
def login_required(func):
    def wrapper():
        print("Checking if user is logged in...")
        func()
    return wrapper

@login_required
def view_profile():
    print("Ravi's profile opened.")

view_profile()
```


## 🏠 Homework

1. **Create a Decorator to Log Calls**

   * Create a decorator called `log_function_call` that prints function name and when it was called.
   * Apply it to a function like `add()`.

2. **Create a Decorator That Times a Function**

   * Use `time` module to record how long a function takes to run.
   * Apply it to a `long_task()` function that sleeps for 2 seconds.

3. **Multiple Decorators**

   * Create two decorators: one adds `"==="` above and below output, another adds `>>>` before the output.
   * Apply both on a function that prints your name.

4. **Create a Decorator That Only Allows a Specific User**

   * Create a function `view_data(name)`
   * Decorator `allow_only(name)` should print “Access Denied” if the name is not `"admin"`

