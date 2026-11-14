# Python Functions and Scope: Study Notes

## Overview
This lecture covers how to define and use functions in Python, including parameters, return values, variable scope, and closure. Functions are fundamental building blocks that enable code reuse and organized program structure.

## Table of Contents
1. [Function Definition](#function-definition)
2. [Parameters and Arguments](#parameters-and-arguments)
3. [Return Values](#return-values)
4. [Variable Scope](#variable-scope)
5. [Advanced Concepts](#advanced-concepts)
6. [Key Takeaways](#key-takeaways)

---

## Function Definition

### What is a Function?
A **function** is a reusable block of code that performs a specific task. Instead of repeating code, you define it once and call it whenever needed.

**Basic syntax:**
```python
def function_name(parameters):
    """Docstring explaining what the function does."""
    # Function body
    return result
```

**Example: Simple greeting function**
```python
def greet(name):
    """Greet a person by name."""
    return f"Hello, {name}!"

print(greet("Alice"))  # Output: Hello, Alice!
```

**Why use functions:**
- Avoid code repetition (DRY principle)
- Make code more readable and organized
- Enable testing and debugging of isolated pieces
- Easier to maintain and update code

---

## Parameters and Arguments

### Parameters vs Arguments
- **Parameter**: Variable in function definition
- **Argument**: Value passed when calling the function

```python
def add(a, b):  # a, b are parameters
    return a + b

result = add(3, 5)  # 3, 5 are arguments
```

### Types of Parameters

#### 1. **Positional Parameters**
Arguments must be provided in order:

```python
def create_profile(name, age, city):
    return f"{name}, age {age}, from {city}"

# Must match order
profile = create_profile("Bob", 30, "NYC")  # Correct
# profile = create_profile(30, "Bob", "NYC")  # Wrong order!
```

#### 2. **Keyword Arguments**
Specify parameter names when calling (order doesn't matter):

```python
# These are equivalent:
create_profile("Bob", 30, "NYC")
create_profile(age=30, name="Bob", city="NYC")
create_profile(name="Bob", age=30, city="NYC")
```

#### 3. **Default Parameters**
Provide default values for optional parameters:

```python
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

print(greet("Alice"))                    # Output: Hello, Alice!
print(greet("Bob", greeting="Hi"))       # Output: Hi, Bob!
```

**Important:** Default parameters must come after non-default ones:
```python
def greet(greeting="Hello", name):  # ❌ SyntaxError
    pass

def greet(name, greeting="Hello"):  # ✅ Correct
    pass
```

#### 4. **Variable-Length Arguments**

**`*args`** — accepts multiple positional arguments as a tuple:
```python
def sum_numbers(*args):
    total = 0
    for num in args:
        total += num
    return total

print(sum_numbers(1, 2, 3, 4, 5))  # Output: 15
```

**`**kwargs`** — accepts multiple keyword arguments as a dictionary:
```python
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=30, city="NYC")
# Output:
# name: Alice
# age: 30
# city: NYC
```

**Combining all types:**
```python
def complete_function(a, b=10, *args, **kwargs):
    print(f"a={a}, b={b}")
    print(f"args={args}")
    print(f"kwargs={kwargs}")

complete_function(1, 2, 3, 4, name="test", color="red")
# Output:
# a=1, b=2
# args=(3, 4)
# kwargs={'name': 'test', 'color': 'red'}
```

---

## Return Values

### Returning from Functions

**Single return value:**
```python
def square(x):
    return x ** 2

result = square(5)  # result = 25
```

**Multiple return values (as tuple):**
```python
def get_coordinates():
    return 10, 20  # Returns tuple (10, 20)

x, y = get_coordinates()  # Unpacking
print(x, y)  # Output: 10 20
```

**Implicit return (None):**
```python
def print_message(msg):
    print(msg)
    # No return statement = returns None

result = print_message("Hi")  # result = None
```

**Conditional returns:**
```python
def validate_age(age):
    if age < 0:
        return False
    elif age < 18:
        return "Minor"
    else:
        return "Adult"

print(validate_age(15))  # Output: Minor
```

---

## Variable Scope

### Local vs Global Scope

**Local scope:** Variables defined inside a function (exist only within that function)

**Global scope:** Variables defined outside all functions (accessible everywhere)

```python
x = 10  # Global variable

def my_function():
    y = 20  # Local variable
    print(x)      # Can access global: 10
    print(y)      # Can access local: 20

my_function()
print(x)          # Accessible: 10
print(y)          # ❌ NameError: y not defined (local to function)
```

### The LEGB Rule
Python looks for variables in this order: **Local → Enclosing → Global → Built-in**

```python
x = "global"

def outer():
    x = "enclosing"
    
    def inner():
        x = "local"
        print(x)  # local
    
    inner()
    print(x)      # enclosing

outer()
print(x)          # global
```

### Variable Shadowing
Local variables with same name as global ones hide (shadow) the global:

```python
x = 10  # Global

def shadow_example():
    x = 20  # Local - shadows global
    print(x)  # 20 (uses local)

shadow_example()
print(x)  # 10 (global unchanged)
```

**Important:** Trying to modify global variable without `global` keyword causes error:

```python
count = 0

def increment():
    count = count + 1  # ❌ UnboundLocalError
    # Python sees count on right side before assignment,
    # but count is assigned locally, so it's uninitialized

increment()
```

**Solution: use `global` keyword**

```python
count = 0

def increment():
    global count  # Declare we're using the global count
    count = count + 1

increment()
print(count)  # 1
```

### `nonlocal` Keyword (Nested Functions)
Access variables from enclosing function scope:

```python
def outer():
    x = 10
    
    def inner():
        nonlocal x  # Modify enclosing scope variable
        x = x + 5
    
    inner()
    print(x)  # 15

outer()
```

---

## Advanced Concepts

### Closures
A function that "remembers" variables from its enclosing scope, even after that scope ends.

```python
def make_multiplier(factor):
    # Inner function "closes over" factor
    def multiply(x):
        return x * factor
    return multiply

double = make_multiplier(2)
triple = make_multiplier(3)

print(double(5))  # 10
print(triple(5))  # 15
```

Each function remembers its own `factor` value—this is closure in action.

### Docstrings
String at the beginning of function that documents what it does:

```python
def calculate_bmi(weight_kg, height_m):
    """
    Calculate Body Mass Index.
    
    Args:
        weight_kg (float): Person's weight in kilograms
        height_m (float): Person's height in meters
    
    Returns:
        float: Calculated BMI
    """
    return weight_kg / (height_m ** 2)

# Access docstring:
print(calculate_bmi.__doc__)
help(calculate_bmi)
```

### Lambda Functions (Anonymous Functions)
Short, unnamed functions for simple operations:

```python
# Regular function
def add(x, y):
    return x + y

# Lambda equivalent
add = lambda x, y: x + y

print(add(3, 5))  # 8
```

**Common use: with `map()`, `filter()`, `sorted()`**

```python
numbers = [1, 2, 3, 4, 5]

# Double each number
doubled = list(map(lambda x: x * 2, numbers))
print(doubled)  # [2, 4, 6, 8, 10]

# Filter even numbers
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)  # [2, 4]

# Sort by second element
students = [("Alice", 85), ("Bob", 92), ("Charlie", 78)]
sorted_students = sorted(students, key=lambda s: s[1])
print(sorted_students)  # [("Charlie", 78), ("Alice", 85), ("Bob", 92)]
```

---

## Key Takeaways

- **Functions** organize code into reusable blocks—use them to avoid repetition
- **Parameters and arguments** let functions accept and work with different data
- **Return values** pass results back to where the function was called
- **Scope** determines where variables are accessible:
  - Local variables exist only inside their function
  - Global variables accessible everywhere but should be used sparingly
  - Use `global` or `nonlocal` keywords to modify outer scope variables
- **Closures** let inner functions remember enclosing scope variables
- **Default parameters** make functions flexible without requiring all arguments
- **`*args` and `**kwargs`** handle variable-length arguments elegantly

---

## Summary

Functions are the backbone of organized Python programming. By understanding how to define functions, pass arguments, return values, and manage variable scope, you can write cleaner, more maintainable code. Mastering these concepts enables you to build complex programs by composing simpler, well-defined pieces—the essence of good software engineering.

