# Python Looping & Advanced Control Flow Guide

## Overview of Looping in Programming
In programming, **loops** are fundamental control structures designed to handle repetitive tasks and automate execution routines. Instead of writing the same block of code multiple times, loops execute a specific sequence of instructions dynamically based on defined conditions or iterables. Python provides two primary looping constructs:

1. **`for` loop**: Best utilized when the exact number of iterations is known or when iterating over elements within a sequence (such as lists, tuples, dictionaries, sets, or strings).
2. **`while` loop**: Best utilized when execution must continue indefinitely or until a specific dynamic condition evaluates to `False`.

### Key Control Flow Statements
* **`break`**: Immediately terminates the innermost loop, exiting the execution block ahead of its normal completion.
* **`continue`**: Skips the remaining code inside the current iteration and forces the loop to jump straight to the next evaluation cycle.
* **`pass`**: Acts as a syntactic placeholder when a statement is required by the interpreter but no code execution is desired.

---

## Lesson 1: Fundamentals of Python Loops & Basic Practice

This section covers the core behavior of `while` and `for` loops, incorporating foundational implementations like sequence iteration, range manipulation, and simple validation logic.

### Key Concepts Covered
* **`while` Loops & Sentinel Control**: Monitoring dynamic states and utilizing `else` blocks when loop conditions terminate naturally.
* **`for` Loops & Data Structures**: Iterating across strings, lists, sets, and dictionaries (extracting keys, values, and pairs).
* **Nested Loops**: Implementing multi-level iteration structures (e.g., searching nested dictionaries or multi-dimensional data).

### Practice Problem 1: Automated Class Attendance Tracker
* **Scenario**: As a class president, you need to verify the attendance of 10 students one by one using a controlled counting loop.
* **Implementation Code**:
```python
smager = 1
while smager < 11:
    print(f"Siswa ke {smager} Hadir")
    smager += 1
else:
    print("Semua Siswa telah absen")
```

### Practice Problem 2: Shopping Receipt Total Aggregator
* **Scenario**: Calculating the cumulative cost of items selected during a convenience store checkout process.
* **Implementation Code**:
```python
item_prices = [12500, 5000, 20500, 50000, 150000]
total_sum = 0
for price in item_prices:
    total_sum += price

print(f"Total Transaction Amount: {total_sum}")
```

---

## Lesson 2: Advanced Control Flow & High-Performance Optimization

This section explores complex scenarios, emphasizing security logic (such as PIN authentication limits), data stream validation, and high-efficiency algorithmic implementation.

### Key Concepts Covered
* **Attempt Limiting & Security Breakouts**: Restricting user retries in authentication workflows.
* **Data Stream Filtering**: Filtering incoming input streams using conditional `continue` and sentinel `break` triggers.
* **Algorithmic Optimization (Early Exit)**: Reducing CPU overhead in computational tasks via strategic `break` calls.

### Practice Problem 1: Secure PIN Verification System (Medium)
* **Scenario**: A user is given a maximum of 3 attempts to enter the correct PIN. Exceeding this limit immediately blocks the account.
* **Implementation Code**:
```python
correct_pin = 8989
pin_attempt = 0
max_attempts = 3

while pin_attempt < max_attempts:
    user_input = int(input("Enter your PIN: "))
    
    if user_input == correct_pin:
        print("Access Granted. Proceeding to Menu.")
        break
    else:
        pin_attempt += 1
        if pin_attempt == max_attempts:
            print("Your account has been blocked due to multiple failed attempts.")
            break
        else:
            print(f"Incorrect PIN. Attempts remaining: {max_attempts - pin_attempt}")
```

### Practice Problem 2: High-Performance Prime Number Finder (Hard)
* **Scenario**: Finding all prime numbers up to a user-defined limit $N$ using nested `while` loops optimized with early exits (`break`) and even-number checks (`continue`).
* **Implementation Code**:
```python
current_num = 2
limit = int(input("Enter upper limit N: "))

while current_num <= limit:
    # Skip even numbers greater than 2 for optimization
    if current_num > 2 and current_num % 2 == 0:
        current_num += 1
        continue
        
    divisor = 2
    is_prime = True
    
    while divisor * divisor <= current_num:
        if current_num % divisor == 0:
            is_prime = False
            break # Early exit to save CPU cycles
        divisor += 1
        
    if is_prime:
        print(current_num)
        
    current_num += 1
```