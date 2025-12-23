# python-fundamentals

### Python Conditionals & Control Flow Examples

### Python Fundamentals Projects

This repository contains Python projects developed during my university coursework. 
The projects focus on **basic programming concepts**, **data structures**,
and **problem-solving using Python**.

### ⚠️ Note: These projects are shared for educational and portfolio purposes.


### Project 1: Car Rental Automation System

### Overview
This project simulates a basic **car rental system** for a rental company.
It stores car inventory, allows users to select a brand and model, checks availability,
and calculates the total rental cost.

### Key Concepts
- Dictionaries & lists
- User input validation
- Loops and conditional logic
- Basic business logic modeling


### Project 2: Course Classification System

### Overview
This project classifies university courses into **upper-level** and **lower-level**
categories based on department-specific rules.

### Key Concepts
- String manipulation
- Type conversion
- Conditional logic
- List operations


### Project 1 – car_rental_system.py

### Car Rental Automation System

cars = [
    {"brand": "BMW", "model": "3.18", "year": 2018, "amount": 8, "daily_price": 140},
    {"brand": "Mercedes", "model": "A180", "year": 2019, "amount": 4, "daily_price": 120},
    {"brand": "BMW", "model": "5.20", "year": 2017, "amount": 3, "daily_price": 210},
    {"brand": "Volkswagen", "model": "Passat", "year": 2014, "amount": 3, "daily_price": 120},
]

###  Find unique brands
brands = sorted(set(car["brand"] for car in cars))
print("Available brands:", brands)

while True:
    choice = input("Select a brand (or type 'exit'): ").strip()

    if choice.lower() == "exit":
        break

    selected_cars = [car for car in cars if car["brand"].lower() == choice.lower()]

    if not selected_cars:
        print("Invalid brand. Please try again.")
        continue

    for car in selected_cars:
        print(car)

    model = input("Select model: ").strip()
    days = int(input("Number of rental days: "))

    found = False
    for car in selected_cars:
        if car["model"] == model:
            found = True
            if car["amount"] > 0:
                total_price = days * car["daily_price"]
                print(f"Total rental price: ${total_price}")
            else:
                print("This selection is not available now.")

    if not found:
        print("Invalid model selection.")




### Project 2 – course_classification.py

### Course Classification System

classes = [
    "MATH 150", "PSYCH 111", "PSYCH 313", "PSYCH 412",
    "MATH 300", "MATH 404", "MATH 206", "ENG 100",
    "ENG 103", "ENG 201", "PSYCH 508", "ENG 220",
    "ENG 125", "ENG 124"
]

upper = []
lower = []

for course in classes:
    subject, number = course.split()
    number = int(number)

    if subject == "MATH" and number >= 300:
        upper.append(course)
    elif subject == "ENG" and number >= 200:
        upper.append(course)
    elif subject == "PSYCH" and number >= 400:
        upper.append(course)
    else:
        lower.append(course)

print("Upper Level Courses:", upper)
print("Lower Level Courses:", lower)


### Python Conditionals & Control Flow Examples

This repository contains Python examples developed during my university coursework.
The code demonstrates **conditional statements**, **comparison operators**, and
**control flow logic** using Python.

The purpose of this repository is to showcase fundamental Python programming concepts
and logical thinking rather than production-level applications.

---

### Topics Covered
- Comparison operators (`==`, `!=`, `<`, `>`)
- Identity vs equality (`is` vs `==`)
- Membership operators (`in`, `not in`)
- Boolean logic
- `if`, `if-else`, `elif`
- Nested conditional statements
- Ternary conditional expressions

---

### Notes
- These examples were created for **educational purposes**
- Focus is on **logic and syntax clarity**
- Code is console-based and interactive





### Python Conditionals & Control Flow Examples

This repository contains Python examples developed during my university coursework.
The code demonstrates **conditional statements**, **comparison operators**, and
**control flow logic** using Python.

The purpose of this repository is to showcase fundamental Python programming concepts
and logical thinking rather than production-level applications.



### Topics Covered
- Comparison operators (`==`, `!=`, `<`, `>`)
- Identity vs equality (`is` vs `==`)
- Membership operators (`in`, `not in`)
- Boolean logic
- `if`, `if-else`, `elif`
- Nested conditional statements
- Ternary conditional expressions



### Notes
- These examples were created for **educational purposes**
- Focus is on **logic and syntax clarity**
- Code is console-based and interactive



### Python Conditional Statements & Operators

### --- Comparison Operators ---
print(3 > 2)
print(44 == 41)
print(3 != 2)

name = "Engin"
print(name == "Engin")
print(name == "engin")

###  String comparisons
print('mercan' < 'merdan')
print('can' < 'candan')

###  --- Identity & Membership Operators ---
print(type(name) is str)

### NOTE: 'is' checks object identity, not equality
print(name is "Engin")  # not recommended in real applications

input_name = input("Enter your name: ")
print(input_name == name)
print(input_name is name)

### Reassign to demonstrate identity
input_name = name
print(input_name is name)

print('can' in 'candan')
print('s' in name)

###  --- NOT operator ---
check = False
print(not check)
print('s' not in name)

### --- Basic if statement ---
a = 33
b = 200
if b > a:
    print("b is greater than a")

### --- if with string membership ---
if 'E' in name:
    print("Hello", name)

### --- if / else example ---
if name == "Engin":
    print("Hello", name)
else:
    print("Wrong user")

### --- Logical operators (and / or) ---
saved_user = "example_mail@gmail.com"
saved_pass = "1234"

username = input("Enter your username: ")
if username == saved_user or username + "@gmail.com" == saved_user:
    password = input("Enter your password: ")
    if password == saved_pass:
        print("Welcome dashboard", saved_user)
    else:
        print("Password is incorrect.")
else:
    print("User does not exist.")

### --- Ternary conditional expression ---
age = int(input("Enter your age: "))
check = True if age > 25 else False
print("Age > 25:", check)

###  --- Nested if / elif / else ---
exam_grade = int(input("Enter your exam grade: "))

letter_grade = ""
success = False

if exam_grade >= 90:
    letter_grade = "AA"
elif exam_grade >= 80:
    letter_grade = "BA"
elif exam_grade >= 70:
    letter_grade = "BB"
else:
    letter_grade = "FF"

if letter_grade != "FF" and exam_grade >= 70:
    success = True

message = f"Your letter grade is {letter_grade}. Passed: {success}"
print(message)



