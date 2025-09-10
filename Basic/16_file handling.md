# **File Handling in Python**

File handling allows us to **read from** and **write to** files — a common task in almost every real-world application (storing data, logs, reports, etc.).

## 📁 Why File Handling?

* To save user data permanently (like notes, records, etc.)
* To read content from a file (like student marks, exam results)
* Helps build real applications like:

  * Address books
  * Billing systems
  * Exam report generators


## 📌 Python File Modes

| Mode  | Meaning                           | Use Case                      |
| ----- | --------------------------------- | ----------------------------- |
| `'r'` | Read (default mode)               | Read an existing file         |
| `'w'` | Write (overwrites if file exists) | Write new content             |
| `'a'` | Append (adds content at the end)  | Add data without deleting old |
| `'x'` | Create (fails if file exists)     | Create new file safely        |
| `'b'` | Binary mode                       | For images, videos, etc.      |
| `'t'` | Text mode (default)               | For text files                |


## ✅ Opening a File

```python
file = open("students.txt", "r")
```

### Parts:

* `"students.txt"` → file name
* `"r"` → mode (read mode)


## ✅ Reading From a File

### 1. `read()` – Reads entire file

```python
file = open("notes.txt", "r")
print(file.read())
file.close()
```

### 2. `readline()` – Reads one line

```python
file = open("notes.txt", "r")
print(file.readline())
file.close()
```

### 3. `readlines()` – Reads all lines into a list

```python
file = open("notes.txt", "r")
lines = file.readlines()
print(lines)
file.close()
```


## ✅ Writing to a File

### `write()` – Overwrites entire file

```python
file = open("data.txt", "w")
file.write("Namaskara Bengaluru!\n")
file.write("Python is awesome!")
file.close()
```

> 🎯 If the file exists, it **clears** the old content and writes fresh.


## ✅ Appending to a File

```python
file = open("data.txt", "a")
file.write("\nThis line is added later.")
file.close()
```

> 📌 Adds new content without deleting old content.


## ✅ Using `with` Statement (Best Practice)

```python
with open("students.txt", "r") as file:
    content = file.read()
    print(content)
```

> ✅ Automatically closes the file
> ✅ Clean and professional


## 🗃️ Writing List of Data to File

```python
students = ["Ravi", "Meena", "Dinesh"]
with open("students.txt", "w") as file:
    for student in students:
        file.write(student + "\n")
```


## 📝 Reading File and Processing Each Line

```python
with open("students.txt", "r") as file:
    for line in file:
        print("Student:", line.strip())
```

> `.strip()` removes `\n` from the end of each line


## 🧠 Common Errors

| Error               | Cause                           |
| ------------------- | ------------------------------- |
| `FileNotFoundError` | Trying to read a missing file   |
| `PermissionError`   | Access denied                   |
| `IsADirectoryError` | Trying to open a folder as file |


# **File Handling in Python**

File handling allows us to **read from** and **write to** files — a common task in almost every real-world application (storing data, logs, reports, etc.).

## 📁 Why File Handling?

* To save user data permanently (like notes, records, etc.)
* To read content from a file (like student marks, exam results)
* Helps build real applications like:

  * Address books
  * Billing systems
  * Exam report generators


## 📌 Python File Modes

| Mode  | Meaning                           | Use Case                      |
| ----- | --------------------------------- | ----------------------------- |
| `'r'` | Read (default mode)               | Read an existing file         |
| `'w'` | Write (overwrites if file exists) | Write new content             |
| `'a'` | Append (adds content at the end)  | Add data without deleting old |
| `'x'` | Create (fails if file exists)     | Create new file safely        |
| `'b'` | Binary mode                       | For images, videos, etc.      |
| `'t'` | Text mode (default)               | For text files                |


## ✅ Opening a File

```python
file = open("students.txt", "r")
```

### Parts:

* `"students.txt"` → file name
* `"r"` → mode (read mode)


## ✅ Reading From a File

### 1. `read()` – Reads entire file

```python
file = open("notes.txt", "r")
print(file.read())
file.close()
```

### 2. `readline()` – Reads one line

```python
file = open("notes.txt", "r")
print(file.readline())
file.close()
```

### 3. `readlines()` – Reads all lines into a list

```python
file = open("notes.txt", "r")
lines = file.readlines()
print(lines)
file.close()
```


## ✅ Writing to a File

### `write()` – Overwrites entire file

```python
file = open("data.txt", "w")
file.write("Namaskara Bengaluru!\n")
file.write("Python is awesome!")
file.close()
```

> 🎯 If the file exists, it **clears** the old content and writes fresh.


## ✅ Appending to a File

```python
file = open("data.txt", "a")
file.write("\nThis line is added later.")
file.close()
```

> 📌 Adds new content without deleting old content.


## ✅ Using `with` Statement (Best Practice)

```python
with open("students.txt", "r") as file:
    content = file.read()
    print(content)
```

> ✅ Automatically closes the file
> ✅ Clean and professional


## 🗃️ Writing List of Data to File

```python
students = ["Ravi", "Meena", "Dinesh"]
with open("students.txt", "w") as file:
    for student in students:
        file.write(student + "\n")
```


## 📝 Reading File and Processing Each Line

```python
with open("students.txt", "r") as file:
    for line in file:
        print("Student:", line.strip())
```

> `.strip()` removes `\n` from the end of each line


## 🧠 Common Errors

| Error               | Cause                           |
| ------------------- | ------------------------------- |
| `FileNotFoundError` | Trying to read a missing file   |
| `PermissionError`   | Access denied                   |
| `IsADirectoryError` | Trying to open a folder as file |


## 🏠 Homework

1. **Create a File and Write**

   * Ask user for 3 friend names.
   * Write them into `friends.txt`, one per line.

2. **Append Marks**

   * Ask for student name and marks.
   * Append the info to `marks.txt` in this format: `Ravi - 85`

3. **Read and Count Lines**

   * Read any file and count how many lines it has.
   * Example: How many students are listed?

4. **Search From File**

   * Write a program that searches for a name in `friends.txt`
   * If found, print "Found!" else "Not Found!!"

