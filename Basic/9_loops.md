## **While Loops in Python**

A **loop** is a programming structure that repeats a set of instructions as long as a specified condition is True. In Python, the **`while` loop** allows you to repeatedly execute a block of code as long as the condition is True.

### **1. The Basic Structure of a `while` Loop**

The `while` loop repeatedly executes a block of code as long as the condition is `True`.

#### **Syntax**:
```python
while condition:
    # Code to execute as long as condition is True
```

#### **Example**:
Let’s print numbers from 1 to 5 using a `while` loop.

```python
i = 1
while i <= 5:
    print(i)
    i += 1  # Incrementing i by 1 after each iteration
```

- The loop starts with `i = 1` and checks if `i <= 5`.
- As long as this condition is `True`, it prints the value of `i` and increases it by 1 (`i += 1`).
- The loop ends when `i` becomes 6, as the condition `i <= 5` becomes `False`.

**Output**:
```
1
2
3
4
5
```

### **2. Common Example: Counting Sheep**

Let’s relate this to a common example: Imagine you're counting sheep to fall asleep.

```python
sheep_count = 1
while sheep_count <= 10:
    print(f"Sheep {sheep_count}")
    sheep_count += 1
```

This prints `"Sheep 1"`, `"Sheep 2"`, and so on, until `"Sheep 10"`. After that, the loop stops.

### **3. Avoiding Infinite Loops**

A **`while` loop** can run indefinitely if the condition is always `True`. To prevent this, ensure that the condition eventually becomes `False`.

#### **Example of an Infinite Loop**:
```python
i = 1
while i <= 5:
    print(i)
    # Forgot to update i, so the condition remains True forever!
```

In this case, the loop will keep printing `1` forever because `i` is never incremented, so the condition `i <= 5` will always be `True`.

To avoid this, make sure to **update the variable** that controls the condition within the loop.

### **4. Using `break` to Exit a `while` Loop**

You can use the `break` statement to exit a loop when a certain condition is met.

#### **Example**:
Let’s stop counting sheep after 5 sheep, even though the condition allows counting up to 10:

```python
sheep_count = 1
while sheep_count <= 10:
    print(f"Sheep {sheep_count}")
    if sheep_count == 5:
        print("That's enough counting!")
        break
    sheep_count += 1
```

- The loop stops after `"Sheep 5"` because of the `break` statement, even though the condition was `sheep_count <= 10`.

**Output**:
```
Sheep 1
Sheep 2
Sheep 3
Sheep 4
Sheep 5
That's enough counting!
```

### **5. Using `continue` to Skip an Iteration**

The `continue` statement is used to skip the current iteration and move on to the next one.

#### **Example**:
Let’s say you want to skip counting sheep that are number 4:

```python
sheep_count = 1
while sheep_count <= 5:
    if sheep_count == 4:
        sheep_count += 1
        continue
    print(f"Sheep {sheep_count}")
    sheep_count += 1
```

Here, when `sheep_count` is 4, the `continue` statement skips printing `"Sheep 4"`, and the loop continues with `sheep_count = 5`.

**Output**:
```
Sheep 1
Sheep 2
Sheep 3
Sheep 5
```

### **6. Using `while` Loops for User Input**

You can use a `while` loop to repeatedly ask the user for input until they provide valid data.

#### **Example**:
Let’s ask the user for a PIN until they enter the correct one:

```python
pin = ""
correct_pin = "1234"
while pin != correct_pin:
    pin = input("Enter your PIN: ")
    if pin != correct_pin:
        print("Incorrect PIN. Try again.")
print("PIN accepted. You can proceed.")
```

- The loop keeps running until the user enters the correct PIN.
- If the user enters an incorrect PIN, they are prompted to try again.

### **7. Real-life Example: KSRTC Bus Seats Availability**

Let’s say you want to simulate a KSRTC bus seat booking system. The bus has 5 available seats. Each time a seat is booked, the available seats decrease.

```python
available_seats = 5

while available_seats > 0:
    print(f"{available_seats} seats available.")
    booking = input("Do you want to book a seat? (yes/no): ").lower()
    
    if booking == "yes":
        available_seats -= 1
        print("Seat booked!")
    else:
        print("No booking made.")

print("All seats are booked!")
```

Here, the loop keeps running until all seats are booked. It checks the available seats and asks the user if they want to book one. The loop stops when there are no more seats available.

**Output Example**:
```
5 seats available.
Do you want to book a seat? (yes/no): yes
Seat booked!
4 seats available.
Do you want to book a seat? (yes/no): yes
Seat booked!
...
1 seats available.
Do you want to book a seat? (yes/no): yes
Seat booked!
All seats are booked!
```

### **8. Nested `while` Loops**

You can also nest `while` loops inside each other. This can be useful in more complex scenarios, such as checking multiple conditions or dealing with multi-level data.

#### **Example**:
Let’s simulate a snack machine that allows users to buy snacks as long as both the machine has snacks and the user has money:

```python
snacks_available = 3
money = 10

while snacks_available > 0 and money > 0:
    print(f"Snacks available: {snacks_available}. Money: ₹{money}")
    buy = input("Do you want to buy a snack for ₹5? (yes/no): ").lower()
    
    if buy == "yes" and money >= 5:
        snacks_available -= 1
        money -= 5
        print("Snack purchased!")
    else:
        print("No purchase made.")
        
print("Either snacks are sold out or you are out of money.")
```

This loop will continue as long as there are snacks available and the user has money. Once one condition is no longer True, the loop stops.

## **For Loops in Python**

In Python, a **`for` loop** is used to iterate over a sequence (like a list, tuple, string, or range) and execute a block of code repeatedly for each element in the sequence.

### **1. The Basic Structure of a `for` Loop**

A **`for` loop** allows you to repeat a block of code a fixed number of times, or once for each element in a sequence.

#### **Syntax**:
```python
for item in sequence:
    # Code to execute for each item in the sequence
```

#### **Example**:
Let’s print each name in a list of Kannada cities:

```python
cities = ["Bengaluru", "Mysuru", "Hubballi", "Mangaluru"]
for city in cities:
    print(city)
```

**Output**:
```
Bengaluru
Mysuru
Hubballi
Mangaluru
```

- Here, `cities` is a list, and the `for` loop iterates over each item (city) in that list.

### **2. Using `range()` with `for` Loops**

The `range()` function generates a sequence of numbers, which you can use in a `for` loop when you want to repeat a block of code a specific number of times.

#### **Syntax of `range()`**:
```python
range(start, stop, step)
```
- `start`: The starting value (inclusive).
- `stop`: The ending value (exclusive).
- `step`: The increment (optional, default is 1).

#### **Example**: Counting from 1 to 10
```python
for i in range(1, 11):
    print(i)
```

This loop will print the numbers from 1 to 10.

**Output**:
```
1
2
3
4
5
6
7
8
9
10
```

#### **Example**: Counting by 2s from 1 to 10
```python
for i in range(1, 11, 2):
    print(i)
```

This loop prints only the odd numbers between 1 and 10.

**Output**:
```
1
3
5
7
9
```

### **3. Looping Over Strings**

You can also loop over each character in a string using a `for` loop.

#### **Example**: Printing each character in a string
```python
name = "Karnataka"
for letter in name:
    print(letter)
```

**Output**:
```
K
a
r
n
a
t
a
k
a
```

This loop goes through the string `"Karnataka"` one character at a time.

### **4. Nested `for` Loops**

You can also have **nested `for` loops**, which means a loop inside another loop. This is useful when working with multi-level data, like lists inside lists.

#### **Example**: Multiplication Table

Let’s print the multiplication table from 1 to 5 using a nested `for` loop.

```python
for i in range(1, 6):
    for j in range(1, 6):
        print(f"{i} x {j} = {i * j}")
    print()  # To print an empty line after each table
```

**Output**:
```
1 x 1 = 1
1 x 2 = 2
1 x 3 = 3
1 x 4 = 4
1 x 5 = 5

2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 10

...

5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
```

Here, the outer loop controls the first number (`i`), and the inner loop controls the second number (`j`). Together, they generate the multiplication table.

### **5. Using `break` in a `for` Loop**

The `break` statement is used to exit a loop early when a certain condition is met.

#### **Example**: Stop the loop when you find a specific item
Let’s say you are searching for a specific city in a list:

```python
cities = ["Bengaluru", "Mysuru", "Hubballi", "Mangaluru"]
for city in cities:
    if city == "Hubballi":
        print(f"Found {city}!")
        break
    print(city)
```

In this case, the loop stops when it finds `"Hubballi"` and prints `"Found Hubballi!"`.

**Output**:
```
Bengaluru
Mysuru
Found Hubballi!
```

### **6. Using `continue` in a `for` Loop**

The `continue` statement is used to skip the current iteration of the loop and move on to the next one.

#### **Example**: Skip a specific item in a list
Let’s skip `"Hubballi"` while looping through the cities:

```python
cities = ["Bengaluru", "Mysuru", "Hubballi", "Mangaluru"]
for city in cities:
    if city == "Hubballi":
        continue
    print(city)
```

**Output**:
```
Bengaluru
Mysuru
Mangaluru
```

Here, `"Hubballi"` is skipped, and the loop continues with the next city.

### **7. Looping Through a List with `enumerate()`**

The `enumerate()` function allows you to loop over a sequence and get both the index and the value of each item.

#### **Example**: Displaying the index and value of each city
```python
cities = ["Bengaluru", "Mysuru", "Hubballi", "Mangaluru"]
for index, city in enumerate(cities):
    print(f"City {index + 1}: {city}")
```

**Output**:
```
City 1: Bengaluru
City 2: Mysuru
City 3: Hubballi
City 4: Mangaluru
```

### **8. Using `else` with `for` Loops**

You can also use an **`else` clause** with a `for` loop. The code inside the `else` block will execute once the loop finishes, unless the loop is terminated by a `break` statement.

#### **Example**:
```python
for city in cities:
    print(city)
else:
    print("No more cities!")
```

**Output**:
```
Bengaluru
Mysuru
Hubballi
Mangaluru
No more cities!
```

In this case, after the loop has finished going through all the cities, it prints `"No more cities!"`.

### **9. Real-Life Example: Distributing Laddus**

Imagine you have 5 laddus to distribute among friends. You can use a `for` loop to give each friend one laddu.

```python
laddus = 5
friends = ["Rahul", "Sneha", "Aman", "Priya"]

for friend in friends:
    if laddus > 0:
        print(f"{friend} gets a laddu!")
        laddus -= 1
    else:
        print("No laddus left!")
```

**Output**:
```
Rahul gets a laddu!
Sneha gets a laddu!
Aman gets a laddu!
Priya gets a laddu!
No laddus left!
```

