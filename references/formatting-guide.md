# Formatting Guide for Lecture Notes

This guide provides concrete examples of proper formatting for different types of lecture content.

## Table of Contents
1. [Code Blocks](#code-blocks)
2. [Mathematical Equations](#mathematical-equations)
3. [Tables](#tables)
4. [Key Term Highlighting](#key-term-highlighting)
5. [Callouts and Emphasis](#callouts-and-emphasis)
6. [Lists](#lists)

---

## Code Blocks

### ✅ CORRECT: Syntax-Highlighted Code Blocks

```python
def fibonacci(n):
    """Calculate the nth Fibonacci number."""
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

# Usage
print(fibonacci(5))  # Output: 5
```

Use triple backticks with language identifier (python, javascript, java, etc.)

### ❌ INCORRECT: Plain Text Code

    def fibonacci(n):
        if n <= 1:
            return n
        return fibonacci(n-1) + fibonacci(n-2)

Don't use indented plain text for code that should be highlighted.

---

## Mathematical Equations

### ✅ CORRECT: Inline and Display Math

**Inline math** (within text): The derivative is defined as $f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$.

**Display math** (centered, emphasized):

$$E = mc^2$$

For quadratic equations:

$$ax^2 + bx + c = 0 \implies x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

Use single `$` for inline, double `$$` for display mode.

### ❌ INCORRECT: Plain Text Math

E = mc^2 should be $E = mc^2$

x^2 + 2x + 1 = 0 should be $x^2 + 2x + 1 = 0$

---

## Tables

### ✅ CORRECT: Comparison Table

| Method | Time Complexity | Space Complexity | Best For |
|:---|:---:|:---:|:---|
| Binary Search | O(log n) | O(1) | Sorted arrays |
| Hash Table Lookup | O(1) avg | O(n) | Quick lookups |
| Linear Search | O(n) | O(1) | Unsorted data |

### ✅ CORRECT: Timeline Table

| Year | Event | Significance |
|:---|:---|:---|
| 1859 | Darwin publishes Origin of Species | Foundation of modern evolution theory |
| 1953 | Watson & Crick discover DNA structure | Understanding heredity mechanism |
| 1977 | Sequencing technologies developed | Enables genomics research |

### ✅ CORRECT: Formula Collection Table

| Operation | Formula | Example |
|:---|:---|:---|
| Area of Circle | $A = \pi r^2$ | $r=5 \implies A = 25\pi$ |
| Circumference | $C = 2\pi r$ | $r=5 \implies C = 10\pi$ |
| Arc Length | $s = r\theta$ | $r=2, \theta=\pi/2 \implies s = \pi$ |

---

## Key Term Highlighting

### ✅ CORRECT: Consistent Highlighting

**Bold for primary terms**: The **stack** is a **LIFO** (Last-In-First-Out) data structure.

`Backticks for code/technical terms`: Use the `push()` method to add elements.

**Important concept**: The time complexity of a hash table insertion is **O(1)** on average.

### ❌ INCORRECT: Inconsistent Highlighting

Stack is a LIFO data structure. (No highlighting)

The Stack is a LIFO Data Structure. (Random capitalization)

---

## Callouts and Emphasis

### ✅ CORRECT: Using Callouts

**Note:** This is a simple observation that doesn't require special formatting but is worth emphasizing.

**Important:** This is critical information that learners must remember.

**Tip:** This is a helpful hint that makes understanding easier.

**Example:** Here's a concrete instance of the concept.

**Common Pitfall:** Many students mistakenly think X when they should think Y.

### Format for Callouts

Start with the callout type in bold, followed by a colon, then the content:

```markdown
**Note:** This observation...
**Important:** This critical information...
```

---

## Lists

### ✅ CORRECT: Bullet Lists for Unordered Items

**Advantages of using a dictionary:**
- O(1) average lookup time
- Flexible key types
- Dynamic resizing
- Automatic memory management

### ✅ CORRECT: Numbered Lists for Sequential Steps

**Steps to implement quicksort:**
1. Choose a pivot element from the array
2. Partition array into: elements < pivot, pivot, elements > pivot
3. Recursively sort left and right partitions
4. Combine all three parts

### ✅ CORRECT: Nested Lists for Hierarchical Information

**Data Structures:**
- **Linear Structures**
  - Arrays (contiguous memory)
  - Linked Lists (pointer-based)
  - Stacks (LIFO)
  - Queues (FIFO)
- **Non-Linear Structures**
  - Trees (hierarchical)
  - Graphs (networks)
  - Hash Tables (key-value)

### ❌ INCORRECT: Mixing List Styles Inconsistently

Advantages:
- First point
* Second point (wrong bullet style)
- Third point
1. Fourth point (shouldn't number when others aren't)

---

## Complete Example: Programming Lecture Section

```markdown
## Arrays and Lists

### Arrays
An **array** is a fixed-size collection of elements stored in contiguous memory locations.

**Characteristics:**
- Fixed size (determined at creation)
- Contiguous memory
- O(1) access time by index
- O(n) insertion/deletion in middle

**Example:**
```python
numbers = [1, 2, 3, 4, 5]
print(numbers[2])  # Output: 3 (O(1) access)
```

**Tip:** Arrays are efficient for random access but inefficient for insertions/deletions in the middle.

### Linked Lists
A **linked list** is a dynamic collection where elements (nodes) are connected via pointers.

| Property | Array | Linked List |
|:---|:---:|:---:|
| Access | O(1) | O(n) |
| Insert (middle) | O(n) | O(1) |
| Space | Fixed | Dynamic |
| Memory | Contiguous | Non-contiguous |

**Example:**
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

head = Node(1)
head.next = Node(2)
head.next.next = Node(3)
```

**Important:** Linked lists require O(n) time to access elements but O(1) to insert after finding position.

### When to Use What
1. Use arrays when you need fast random access
2. Use linked lists when you frequently insert/delete at front or middle
3. Use stacks/queues for specific ordering needs (LIFO/FIFO)
```

---

## Formatting Checklist

- ✅ Code blocks use triple backticks with language identifier
- ✅ Math uses `$...$` for inline and `$$...$$` for display
- ✅ Tables use proper markdown syntax with alignment
- ✅ Key terms are **bolded** or `backticked` consistently
- ✅ Callouts start with bold type label: "**Note:**", "**Important:**", etc.
- ✅ Lists use consistent bullet (-) or number (1.) markers
- ✅ Nested items properly indented with 2 spaces
- ✅ Examples immediately follow concepts (inline, not separate)
- ✅ No unnecessary formatting (avoid RANDOM Capitalization)

