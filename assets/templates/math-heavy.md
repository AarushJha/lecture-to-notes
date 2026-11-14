# Calculus I: Limits and Continuity

## Overview
This lecture introduces the foundational concepts of limits and continuity, which form the mathematical basis for calculus. Limits describe how functions behave as inputs approach certain values, while continuity ensures functions don't have unexpected jumps or gaps. These concepts are essential for understanding derivatives and integrals.

## Table of Contents
1. [Limits](#limits)
2. [Computing Limits](#computing-limits)
3. [One-Sided Limits](#one-sided-limits)
4. [Continuity](#continuity)
5. [Discontinuities](#discontinuities)
6. [Key Takeaways](#key-takeaways)

---

## Limits

### What is a Limit?

A **limit** describes the value that a function approaches as the input gets arbitrarily close to some number.

**Formal definition:**

We say $\lim_{x \to a} f(x) = L$ if, for every small distance $\epsilon > 0$, there exists a small distance $\delta > 0$ such that whenever $0 < |x - a| < \delta$, we have $|f(x) - L| < \epsilon$.

**Intuitive explanation:** As $x$ gets closer and closer to $a$, the function $f(x)$ gets closer and closer to $L$. The limit describes this behavior.

### Limit Notation

$$\lim_{x \to a} f(x) = L$$

- $x \to a$ means "as x approaches a"
- $f(x) = L$ means "f approaches L"
- The limit can exist even if $f(a)$ is undefined or doesn't equal $L$

### Example: Computing a Limit

**Find** $\lim_{x \to 2} (x^2 + 1)$

**Solution:**
As $x$ approaches 2, we substitute to see what value the function approaches:

$$\lim_{x \to 2} (x^2 + 1) = 2^2 + 1 = 4 + 1 = 5$$

The limit is 5—as $x$ gets close to 2, $f(x)$ gets close to 5.

### Limit Properties

**If** $\lim_{x \to a} f(x) = L$ and $\lim_{x \to a} g(x) = M$, **then:**

$$\lim_{x \to a} [f(x) + g(x)] = L + M$$
$$\lim_{x \to a} [f(x) - g(x)] = L - M$$
$$\lim_{x \to a} [f(x) \cdot g(x)] = L \cdot M$$
$$\lim_{x \to a} \frac{f(x)}{g(x)} = \frac{L}{M} \quad \text{(if } M \neq 0\text{)}$$
$$\lim_{x \to a} [f(x)]^n = L^n$$

**Constant rule:** $\lim_{x \to a} c = c$ (limit of a constant is the constant)

**Why this matters:** These rules let us compute complicated limits by breaking them into simpler pieces.

---

## Computing Limits

### Direct Substitution

**Method:** Simply substitute the value of $a$ into the function.

**Works when:** The function is defined at $x = a$ and is continuous there (more on continuity later).

$$\lim_{x \to 3} (2x - 1) = 2(3) - 1 = 5$$

### Factoring

**Used when:** Direct substitution gives $\frac{0}{0}$ (indeterminate form).

**Example:**

$$\lim_{x \to 2} \frac{x^2 - 4}{x - 2}$$

Direct substitution: $\frac{2^2 - 4}{2 - 2} = \frac{0}{0}$ ❌ Indeterminate

**Solution: Factor the numerator**

$$\lim_{x \to 2} \frac{x^2 - 4}{x - 2} = \lim_{x \to 2} \frac{(x-2)(x+2)}{x - 2}$$

Cancel $(x-2)$ terms:

$$= \lim_{x \to 2} (x + 2) = 2 + 2 = 4$$

**Key point:** We can cancel because $x$ approaches 2 but never equals it, so $x - 2 \neq 0$.

### Rationalizing

**Used when:** The function contains square roots and direct substitution gives $\frac{0}{0}$.

**Example:**

$$\lim_{x \to 0} \frac{\sqrt{x + 1} - 1}{x}$$

Direct substitution: $\frac{\sqrt{1} - 1}{0} = \frac{0}{0}$ ❌

**Solution: Rationalize by multiplying by conjugate**

$$\lim_{x \to 0} \frac{\sqrt{x + 1} - 1}{x} \cdot \frac{\sqrt{x + 1} + 1}{\sqrt{x + 1} + 1}$$

$$= \lim_{x \to 0} \frac{(x + 1) - 1}{x(\sqrt{x + 1} + 1)} = \lim_{x \to 0} \frac{x}{x(\sqrt{x + 1} + 1)}$$

Cancel $x$:

$$= \lim_{x \to 0} \frac{1}{\sqrt{x + 1} + 1} = \frac{1}{2}$$

---

## One-Sided Limits

### Left and Right Limits

A function might approach different values from the left and right.

**Left limit** ($x$ approaches from values less than $a$):
$$\lim_{x \to a^-} f(x)$$

**Right limit** ($x$ approaches from values greater than $a$):
$$\lim_{x \to a^+} f(x)$$

### Relationship to Two-Sided Limit

$$\lim_{x \to a} f(x) = L \text{ if and only if } \lim_{x \to a^-} f(x) = \lim_{x \to a^+} f(x) = L$$

If left and right limits differ, the two-sided limit does not exist.

### Example: Piecewise Function

$$f(x) = \begin{cases} x + 1 & \text{if } x < 2 \\ x^2 - 1 & \text{if } x \geq 2 \end{cases}$$

Find the left and right limits as $x \to 2$:

**Left limit** (use $x + 1$):
$$\lim_{x \to 2^-} f(x) = 2 + 1 = 3$$

**Right limit** (use $x^2 - 1$):
$$\lim_{x \to 2^+} f(x) = 2^2 - 1 = 3$$

**Two-sided limit:**
$$\lim_{x \to 2} f(x) = 3 \text{ (both sides agree)}$$

---

## Continuity

### What is Continuity?

A function is **continuous** at a point if there's no break, jump, or gap in its graph at that point. Visually, you can draw the function without lifting your pencil.

**Formal definition:** A function $f$ is continuous at $x = a$ if:

1. $f(a)$ is defined
2. $\lim_{x \to a} f(x)$ exists
3. $\lim_{x \to a} f(x) = f(a)$

All three conditions must be true.

### Example: Checking Continuity

**Is** $f(x) = x^2$ **continuous at** $x = 2$?

**Check condition 1:** $f(2) = 2^2 = 4$ ✓ (defined)

**Check condition 2:** $\lim_{x \to 2} x^2 = 4$ ✓ (limit exists)

**Check condition 3:** $4 = 4$ ✓ (limit equals function value)

**Answer:** Yes, $f(x) = x^2$ is continuous at $x = 2$.

### Common Continuous Functions

These functions are continuous everywhere on their domain:

- Polynomials: $f(x) = 3x^2 + 2x + 1$
- Sine and cosine: $\sin(x)$, $\cos(x)$
- Exponentials: $e^x$, $2^x$
- Logarithms: $\ln(x)$ (for $x > 0$)
- Rational functions (except where denominator = 0)

---

## Discontinuities

### Types of Discontinuities

#### 1. **Removable Discontinuity (Hole)**

Limit exists, but function is undefined at that point, OR the function value doesn't equal the limit.

**Example:**
$$f(x) = \frac{x^2 - 4}{x - 2} = \frac{(x-2)(x+2)}{x - 2}$$

- Function is undefined at $x = 2$ (division by zero)
- But $\lim_{x \to 2} f(x) = 4$ (the limit exists)
- This creates a "hole" that could be filled by redefining $f(2) = 4$

#### 2. **Jump Discontinuity**

Left and right limits exist but are different.

**Example:**
$$f(x) = \begin{cases} x & \text{if } x < 0 \\ x + 2 & \text{if } x \geq 0 \end{cases}$$

- $\lim_{x \to 0^-} f(x) = 0$ (left limit)
- $\lim_{x \to 0^+} f(x) = 2$ (right limit)
- Limits don't match → function "jumps" at $x = 0$

#### 3. **Infinite Discontinuity (Asymptote)**

Function approaches infinity or negative infinity as $x$ approaches a point.

**Example:**
$$f(x) = \frac{1}{x}$$

- As $x \to 0^-$: $f(x) \to -\infty$ (approaches negative infinity)
- As $x \to 0^+$: $f(x) \to +\infty$ (approaches positive infinity)
- Vertical asymptote at $x = 0$ (function has infinite discontinuity)

### Identifying Discontinuities

| Type | What to Look For | Example |
|:---|:---|:---|
| Removable | Hole in graph; limit exists | $\frac{x^2-1}{x-1}$ at $x=1$ |
| Jump | Function changes value abruptly | Piecewise with different limits |
| Infinite | Vertical asymptote; function → ±∞ | $\frac{1}{x}$ at $x=0$ |

---

## Key Takeaways

- **Limit** describes what value a function approaches as input approaches a specific point
- **Direct substitution** works when the function is continuous at that point
- **Indeterminate forms** like $\frac{0}{0}$ require algebraic manipulation (factoring, rationalizing)
- **One-sided limits** can differ, indicating the two-sided limit doesn't exist
- **Continuity** requires three conditions: function defined, limit exists, limit equals function value
- **Discontinuities** come in three types: removable (hole), jump, and infinite (asymptote)
- Understanding limits and continuity prepares you for derivatives, which measure instantaneous rates of change

---

## Summary

Limits and continuity are the mathematical foundation for calculus. Limits formalize our intuition about what happens as values get arbitrarily close to a point, while continuity captures the idea of functions without breaks or gaps. By mastering these concepts, you develop the precision needed to understand derivatives (how fast things change) and integrals (accumulated quantities), which build directly on these ideas. The techniques for computing limits—direct substitution, factoring, rationalizing—are tools you'll use throughout calculus to analyze function behavior.

