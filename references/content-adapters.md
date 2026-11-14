# Content-Specific Formatting Adapters

This document provides type-specific guidance for formatting different kinds of lecture content.

## Table of Contents
1. [Programming/Code-Heavy Lectures](#programmingcode-heavy-lectures)
2. [Mathematics/STEM Lectures](#mathematicsstem-lectures)
3. [Narrative/Humanities Lectures](#narrativehumanities-lectures)
4. [Mixed-Type Lectures](#mixed-type-lectures)

---

## Programming/Code-Heavy Lectures

### Characteristics
- Contains algorithms, code examples, design patterns, or software concepts
- Focuses on implementation and practical application
- Often includes pseudocode, data structures, or library usage
- May have performance considerations (time/space complexity)

### Formatting Rules

#### 1. **Code Blocks with Syntax Highlighting**
Always use syntax-highlighted code blocks with appropriate language identifier:

```python
def quicksort(arr):
    """Sort array using quicksort algorithm."""
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quicksort(left) + middle + quicksort(right)
```

**Language identifiers to use:**
- `python`, `javascript`, `java`, `cpp`, `csharp`, `go`, `rust`, `typescript`
- `pseudocode` or plain code block if language is mixed or unclear
- `sql`, `html`, `css`, `json`, `yaml`, `bash`, `shell`

#### 2. **Inline Code for Technical Terms**
Use backticks for function names, class names, variables, methods:

✅ **Correct:**
- The `filter()` method takes a callback function
- Use the `Array.prototype.map()` method to transform elements
- The `__init__()` constructor initializes class attributes

❌ **Incorrect:**
- The filter method takes a callback function (no backticks)
- Use the map method (missing context)

#### 3. **Algorithm Explanation with Steps**
When explaining algorithms, use numbered steps with inline code references:

✅ **Correct:**
```markdown
### Binary Search Algorithm

**How it works:**
1. Start with the middle element of a sorted array
2. If the middle element equals the target, return its index
3. If target < middle element, search the left half (recursively call with left subarray)
4. If target > middle element, search the right half (recursively call with right subarray)
5. Continue until element is found or array is empty

**Time Complexity:** O(log n) because we eliminate half the remaining elements each iteration
```

#### 4. **Complexity Analysis Table**
Create tables comparing time and space complexity:

| Operation | Best Case | Average Case | Worst Case | Space |
|:---|:---:|:---:|:---:|:---:|
| Binary Search | O(1) | O(log n) | O(log n) | O(1) |
| Quick Sort | O(n log n) | O(n log n) | O(n²) | O(log n) |
| Merge Sort | O(n log n) | O(n log n) | O(n log n) | O(n) |
| Hash Table Insert | O(1) | O(1) | O(n) | O(n) |

#### 5. **Common Pitfalls Section**
Include "Common Pitfalls" callouts for programming lectures:

**Common Pitfall:** Off-by-one errors in array indexing
```python
# ❌ WRONG: Skips the last element
for i in range(len(arr)):  # range goes from 0 to len(arr)-1, that's correct...
    # Actually this is correct! Common pitfall is using i <= len(arr)

# ❌ WRONG: Off-by-one
for i in range(1, len(arr)):  # Skips first element at index 0

# ✅ CORRECT:
for i in range(len(arr)):
    process(arr[i])
```

#### 6. **Design Pattern Examples**
When discussing design patterns, use clear code examples:

✅ **Correct:**
```markdown
### Singleton Pattern
Ensures a class has only one instance and provides global access.

**Example:**
```python
class Database:
    _instance = None
    
    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance

# Both references point to the same object
db1 = Database()
db2 = Database()
assert db1 is db2  # True
```
```

#### 7. **Error Handling Examples**
Show both correct and incorrect patterns:

```markdown
### Exception Handling

**❌ WRONG: Bare except clause**
```python
try:
    risky_operation()
except:  # Catches everything, including system exits!
    pass
```

**✅ CORRECT: Specific exception handling**
```python
try:
    risky_operation()
except ValueError as e:
    print(f"Invalid value: {e}")
except IOError as e:
    print(f"IO error: {e}")
except Exception as e:  # Catches remaining exceptions
    print(f"Unexpected error: {e}")
```
```

### When to Use Code Blocks vs. Inline

| Use Code Block | Use Inline Code |
|:---|:---|
| Multi-line algorithms | Function/method names: `filter()` |
| Complete function implementations | Class names: `ArrayList` |
| Example programs (5+ lines) | Variable names: `count`, `user_id` |
| Side-by-side comparisons | File paths: `./src/main.py` |
| Error traces or output examples | Code snippets (1-2 lines): `x = arr[0]` |

---

## Mathematics/STEM Lectures

### Characteristics
- Contains formulas, equations, derivations, or mathematical proofs
- Focuses on concepts, theorems, and their applications
- Often includes step-by-step solutions or worked examples
- May involve physics, chemistry, biology, or other sciences

### Formatting Rules

#### 1. **Inline Math with LaTeX**
Use single `$` for inline equations:

✅ **Correct:**
```markdown
The quadratic formula is $x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$, 
which solves equations of the form $ax^2 + bx + c = 0$.
```

❌ **Incorrect:**
```markdown
The quadratic formula is x = (-b ± √(b² - 4ac)) / 2a
```

#### 2. **Display Math with Double Dollar Signs**
Use `$$` on separate lines for emphasized equations:

✅ **Correct:**
```markdown
### The Pythagorean Theorem

For a right triangle with sides a, b and hypotenuse c:

$$a^2 + b^2 = c^2$$

**Proof:**
...
```

#### 3. **Step-by-Step Derivations**
Show mathematical steps clearly:

✅ **Correct:**
```markdown
### Solving Quadratic Equations

**Example:** Solve $x^2 + 5x + 6 = 0$

**Step-by-step:**
1. Factor: $(x + 2)(x + 3) = 0$
2. Apply zero product property: $x + 2 = 0$ or $x + 3 = 0$
3. Solve each equation: $x = -2$ or $x = -3$

**Solution:** $x \in \{-2, -3\}$
```

#### 4. **Mathematical Tables**
Use tables for formulas, unit conversions, or data:

**Trigonometric Identities Table:**

| Identity | Formula |
|:---|:---|
| Pythagorean | $\sin^2(\theta) + \cos^2(\theta) = 1$ |
| Sum | $\sin(A+B) = \sin A \cos B + \cos A \sin B$ |
| Double Angle | $\cos(2\theta) = \cos^2(\theta) - \sin^2(\theta)$ |

#### 5. **Integration/Differentiation Examples**
Show rules and applications clearly:

```markdown
### Derivative Rules

**Power Rule:** If $f(x) = x^n$, then $f'(x) = nx^{n-1}$

**Example:**
- $f(x) = x^3 \implies f'(x) = 3x^2$
- $f(x) = x^{-1} = \frac{1}{x} \implies f'(x) = -x^{-2} = -\frac{1}{x^2}$

**Product Rule:** $(f \cdot g)' = f' \cdot g + f \cdot g'$

**Example:**
$h(x) = x^2 \sin(x)$

$h'(x) = 2x \sin(x) + x^2 \cos(x)$
```

#### 6. **Scientific Notation and Units**
Clearly show units and significant figures:

✅ **Correct:**
```markdown
**Example:** Calculate the gravitational force between two masses

Given:
- $m_1 = 1 \text{ kg}$
- $m_2 = 1 \text{ kg}$
- $r = 1 \text{ m}$
- $G = 6.674 \times 10^{-11} \text{ m}^3 \text{ kg}^{-1} \text{ s}^{-2}$

Using: $F = G \frac{m_1 m_2}{r^2}$

$F = 6.674 \times 10^{-11} \times \frac{1 \times 1}{1^2} = 6.674 \times 10^{-11} \text{ N}$
```

#### 7. **Graphs and Visual Descriptions**
When visual diagrams can't be included, describe them clearly:

```markdown
### Normal Distribution Curve

The normal distribution (bell curve) has these characteristics:
- **Shape:** Symmetric around the mean μ
- **Peak:** Maximum probability at the mean
- **Spread:** Determined by standard deviation σ
- **Area under curve:** Always equals 1 (represents 100% probability)
- **68-95-99.7 rule:**
  - 68% of data within 1σ of mean
  - 95% of data within 2σ of mean
  - 99.7% of data within 3σ of mean
```

#### 8. **Theorem Statement and Proof**
Clearly separate statements from proofs:

```markdown
### The Intermediate Value Theorem

**Statement:** If $f$ is continuous on $[a, b]$ and $N$ is any number between 
$f(a)$ and $f(b)$, then there exists at least one $c$ in $(a, b)$ such that $f(c) = N$.

**Proof:**
[Step-by-step proof here...]

**Application:**
This theorem guarantees that certain equations have solutions.
```

### Characteristic Math Symbols

| Symbol | LaTeX | Usage |
|:---|:---|:---|
| ∀ (for all) | `\forall` | $\forall x \in \mathbb{R}$ |
| ∃ (exists) | `\exists` | $\exists y$ such that... |
| ∈ (element of) | `\in` | $x \in \mathbb{N}$ |
| ⊆ (subset) | `\subseteq` | $A \subseteq B$ |
| ∩ (intersection) | `\cap` | $A \cap B$ |
| ∪ (union) | `\cup` | $A \cup B$ |
| ∞ (infinity) | `\infty` | $\lim_{x \to \infty}$ |
| ≈ (approximately) | `\approx` | $\pi \approx 3.14159$ |

---

## Narrative/Humanities Lectures

### Characteristics
- Historical, literary, philosophical, or social content
- Emphasizes context, connections, and interpretation
- Often includes quotes, primary sources, or key figures
- May have chronological or thematic organization

### Formatting Rules

#### 1. **Key Terms and Figures**
Highlight important people, concepts, and events:

✅ **Correct:**
```markdown
### The Renaissance

The **Renaissance** was a period of cultural and intellectual revival 
that began in **Italy** during the **14th century**. Key figures included 
**Leonardo da Vinci**, **Michelangelo**, and **Dante Alighieri**.
```

#### 2. **Quotes and Primary Sources**
Use blockquotes for direct quotes:

✅ **Correct:**
```markdown
### Martin Luther King Jr.'s Vision

In his famous 1963 speech, King articulated his dream:

> I have a dream that one day this nation will rise up and live out 
> the true meaning of its creed: "We hold these truths to be self-evident, 
> that all men are created equal."

This statement became central to the Civil Rights Movement.
```

#### 3. **Timeline Tables**
Present chronological information clearly:

| Year | Event | Significance |
|:---|:---|:---|
| 1347 | Black Death reaches Europe | Population decimated; social upheaval |
| 1453 | Fall of Constantinople | End of Byzantine Empire; scholars fled to Europe |
| 1492 | Columbus reaches Americas | Beginning of European colonization |
| 1517 | Martin Luther's 95 Theses | Start of Protestant Reformation |

#### 4. **Cause-and-Effect Relationships**
Show connections between events:

```markdown
### The French Revolution

**Causes:**
- Economic crisis and debt
- Famine and food shortages (1788-1789)
- Enlightenment ideas about rights and democracy
- Resentment of aristocratic privileges

↓

**The Revolution (1789-1799)**

↓

**Consequences:**
- Abolition of feudalism
- Declaration of Rights of Man
- Rise of nationalism
- Napoleon's rise to power
```

#### 5. **Comparison Tables**
Compare different schools of thought, periods, or figures:

| Aspect | Romanticism | Enlightenment |
|:---|:---|:---|
| **Time Period** | Late 18th - 19th century | 17th - 18th century |
| **Focus** | Emotion, nature, individualism | Reason, science, logic |
| **Key Figures** | Wordsworth, Byron, Keats | Voltaire, Descartes, Newton |
| **Literary Style** | Lyrical, expressive, dramatic | Clear, rational, systematic |

#### 6. **Context and Background**
Provide historical context for understanding:

```markdown
### The Cold War (1945-1991)

**Context:**
After World War II, the world divided into two ideological camps:
- **Western Bloc**: Led by the **United States**, capitalist democracy
- **Eastern Bloc**: Led by the **Soviet Union**, communist authoritarianism

**Key Points:**
- Not direct military conflict between superpowers
- Proxy wars in Korea, Vietnam, Afghanistan
- Nuclear arms race and MAD (Mutually Assured Destruction)
- Ideological struggle for global influence
```

#### 7. **Important Concepts and Definitions**
Define terms clearly with examples:

```markdown
### Imperialism

**Definition:** The policy of extending a country's rule over foreign lands 
and peoples, often for economic gain or political power.

**Characteristics:**
- Political control over distant territories
- Economic exploitation of resources and labor
- Cultural and ideological domination
- Military enforcement of authority

**Examples:**
- British Empire (19th-20th centuries): controlled ~25% of world population
- Spanish Conquistadors: conquered Americas (15th-16th centuries)
- French colonialism: control of African and Asian territories
```

#### 8. **Counterarguments and Debates**
Present multiple perspectives:

```markdown
### Was the Industrial Revolution Beneficial?

**Arguments in favor:**
- Increased production and wealth
- Technological advancement
- Improved living standards (eventually)
- Economic growth and opportunity

**Arguments against:**
- Terrible working conditions in factories
- Child labor exploitation
- Environmental pollution
- Widening wealth gap
- Displacement of traditional craftspeople

**Modern perspective:** Mixed outcomes—tremendous benefits alongside 
serious costs that fell disproportionately on workers and the environment.
```

#### 9. **Character Analysis (for Literature)**
Structure literary analysis clearly:

```markdown
### Hamlet: Character Analysis

**Background:**
Prince of Denmark seeking revenge for his father's murder.

**Key Characteristics:**
- Intelligent and philosophical
- Prone to depression and indecision
- Questions morality and existence
- Struggles with madness (real or feigned?)

**Major Conflicts:**
- Internal: Should he trust the ghost? Can he commit murder?
- External: Competition with Claudius for the throne

**Significance:**
Hamlet's psychological complexity made him the archetype for the conflicted hero 
in Western literature.
```

### When to Use Descriptive Prose

| Use Narrative Prose | Use Bullet Points/Lists |
|---|---|
| Explaining complex ideas | Sequential processes or steps |
| Telling a story or sequence | Characteristics or features |
| Analyzing motivations/causes | Chronological timelines |
| Discussing themes/meanings | Comparisons between items |
| Philosophical arguments | Common points or divisions |

---

## Mixed-Type Lectures

### Identifying Mixed-Type Content

Some lectures combine multiple content types. Identify the dominant type and apply adapters accordingly:

```
Primarily programming + some math?
→ Use code-heavy formatting, but include LaTeX for equations

Primarily math + some narrative context?
→ Use math formatting, but provide historical/contextual prose

Primarily narrative + some data/charts?
→ Use narrative formatting, but structure data in tables
```

### Strategy for Mixed Lectures

1. **Identify all content types present:**
   - Are there code examples? → Programming adapter
   - Are there formulas or calculations? → Math adapter
   - Is there historical or contextual narrative? → Narrative adapter

2. **Apply adapters in sections:**
   - Use the appropriate formatting for each section based on its content
   - Maintain consistent overall structure (H2 sections, H3 subsections)
   - Transition smoothly between different content types

3. **Example: Data Science Lecture**
   ```markdown
   ## Model Evaluation

   ### Understanding Metrics (Narrative + Math)
   Evaluation metrics are quantitative measures that tell us how well 
   our model performs. The most common metrics are:

   **Accuracy:** The proportion of correct predictions

   $$\text{Accuracy} = \frac{\text{Number of Correct Predictions}}{\text{Total Predictions}}$$

   ### Implementation (Programming + Math)
   In scikit-learn, we calculate accuracy as:

   ```python
   from sklearn.metrics import accuracy_score
   
   predictions = [0, 1, 1, 0, 1]
   actual = [0, 0, 1, 0, 1]
   
   acc = accuracy_score(actual, predictions)
   # accuracy = 0.8 (4 out of 5 correct)
   ```
   ```

---

## Choosing the Right Adapter

**Decision Tree:**

1. **Does the lecture contain primarily code/algorithms/design patterns?**
   - YES → Use Programming adapter
   - NO → Continue

2. **Does the lecture contain primarily formulas/equations/derivations?**
   - YES → Use Mathematics adapter
   - NO → Continue

3. **Does the lecture contain primarily narrative/historical/literary content?**
   - YES → Use Narrative adapter
   - NO → Use Mixed-Type approach

---

## Summary: Adapter Quick Reference

| Type | Key Formatting | Example Structure |
|:---|:---|:---|
| **Programming** | Code blocks, inline code, complexity tables, pseudocode | `### Concept` → Explanation → Code → Common Pitfall |
| **Mathematics** | LaTeX equations, step-by-step solutions, formula tables | `### Theorem` → Definition → Proof/Derivation → Example |
| **Narrative** | Bold key terms, quotes, timelines, cause-effect | `### Event/Period` → Context → Details → Significance |
| **Mixed** | Combine as needed per section | Use primary adapter; supplement with secondary |

