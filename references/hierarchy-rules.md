# Hierarchy Rules for Consistent Note Structure

This document defines how to organize markdown headers for clean, readable, and consistent note structure.

## Table of Contents
1. [Header Level System](#header-level-system)
2. [Common Mistakes to Avoid](#common-mistakes-to-avoid)
3. [Examples of Correct Hierarchy](#examples-of-correct-hierarchy)
4. [Content Organization Principles](#content-organization-principles)

---

## Header Level System

### Level 1: H1 (`#`)
**Use for:** The main lecture/document title only

```markdown
# Lecture Title or Topic Name
```

- Appears once per document at the very top
- Examples: "# Python Functions", "# Calculus: Derivatives", "# World War II History"

### Level 2: H2 (`##`)
**Use for:** Major sections/chapters within the lecture

```markdown
## Overview
## Main Concepts
## Examples
## Questions & Answers
## Summary
```

- Represents the main organizational units
- Typically 3-8 H2 sections per lecture
- Separates distinct topics or phases

### Level 3: H3 (`###`)
**Use for:** Subsections within H2 sections

```markdown
### Function Definition
### Variable Scope
### Return Statements
```

- Breaks down H2 sections into detailed subtopics
- Each H3 is a distinct concept or related idea
- Optional: only use if there are distinct subtopics

### Level 4 and Beyond: H4+ (`####`, `#####`, etc.)
**Recommendation:** Avoid in most lecture notes

- Makes hierarchy too deep and hard to navigate
- If you need H4, reconsider your organization
- If absolutely necessary, limit to one level (H4 only)

---

## Common Mistakes to Avoid

### ❌ MISTAKE 1: Jumping Levels (No Intermediate Headers)

```markdown
# Python Basics

### Variable Assignment
### Data Types
### Operators
```

**Problem:** Jumps from H1 directly to H3, skipping H2. Reader doesn't understand the major topic grouping.

**Fix:** Insert H2 header:

```markdown
# Python Basics

## Core Concepts
### Variable Assignment
### Data Types
### Operators
```

### ❌ MISTAKE 2: Inconsistent Level Usage

```markdown
# Data Structures

## Arrays
### Linked Lists
#### Trees
## Graphs
```

**Problem:** Inconsistent nesting—sometimes H3 under H2, sometimes H4. Trees shouldn't be under H3 if Graphs is H2.

**Fix:** Keep consistent depth:

```markdown
# Data Structures

## Linear Structures
### Arrays
### Linked Lists
### Stacks

## Non-Linear Structures
### Trees
### Graphs
```

### ❌ MISTAKE 3: Multiple H1 Headers

```markdown
# Functions
Some content...

# Scope
Some content...

# Return Values
Some content...
```

**Problem:** Multiple H1 headers suggest multiple documents. Markdown should have only one H1.

**Fix:** Use H2 for major sections:

```markdown
# Python Fundamentals

## Functions
Some content...

## Scope
Some content...

## Return Values
Some content...
```

### ❌ MISTAKE 4: Too Many Levels (Oversplitting)

```markdown
# Advanced Algorithms

## Sorting
### Quick Sort
#### Implementation Details
##### Partitioning Strategy
```

**Problem:** Too many nested levels makes the document hard to navigate and read.

**Fix:** Consolidate or reorganize:

```markdown
# Advanced Algorithms

## Sorting Algorithms

### Quick Sort
Content about implementation and partitioning...

### Merge Sort
Content about merge sort...
```

### ❌ MISTAKE 5: Inconsistent Section Names

```markdown
# Introduction to Physics

## Kinematics
### Velocity and Speed

## Dynamical Forces
### Newton's Laws

## Waves and Oscillation
### Properties
```

**Problem:** Sometimes using descriptive names ("Dynamical Forces"), sometimes generic ("Properties"). Inconsistency is confusing.

**Fix:** Use consistent naming pattern:

```markdown
# Introduction to Physics

## Kinematics
### Velocity and Speed
### Acceleration

## Dynamics
### Newton's Laws
### Force and Motion

## Waves
### Wave Properties
### Oscillation
```

---

## Examples of Correct Hierarchy

### Example 1: Programming Lecture (Correct)

```markdown
# Introduction to Python

## Overview
Brief summary...

## Prerequisites
- Understanding of variables
- Basic math concepts

## Main Concepts

### Variables and Data Types
Definition and explanation...

### Control Flow
Explanation of control structures...

### Functions
How to define and use functions...

### Object-Oriented Programming
Introduction to classes and objects...

## Key Takeaways
- Main idea 1
- Main idea 2

## Questions & Answers

### Question 1 [Source: Quiz 1]
Q: ...
A: ...

## Summary
Final thoughts...
```

**Hierarchy Check:**
- ✅ One H1 at top
- ✅ Multiple H2 sections
- ✅ H3 only under "Main Concepts" H2
- ✅ No level jumping
- ✅ Consistent structure

---

### Example 2: Mathematics Lecture (Correct)

```markdown
# Calculus I: Limits and Continuity

## Overview
This lecture covers the foundational concepts of limits and continuity...

## Prerequisites
- Algebra and trigonometry
- Function notation

## Core Concepts

### Limits
Definition of a limit...

**Example:** $\lim_{x \to 2} (x^2 + 1) = 5$

### Continuity
A function is continuous if...

**Example:** $f(x) = x^2$ is continuous everywhere.

### Discontinuities
Types of discontinuities...

## Applications
Real-world uses of limits and continuity...

## Key Takeaways
- Limits describe function behavior
- Continuity ensures no jumps

## Summary
Limits and continuity form the foundation for calculus...
```

**Hierarchy Check:**
- ✅ H1 once at top
- ✅ H2 for major topics (Overview, Prerequisites, Core Concepts, Applications, Summary)
- ✅ H3 for specific concepts within Core Concepts
- ✅ No unnecessary depth
- ✅ Clear, logical flow

---

### Example 3: Humanities Lecture (Correct)

```markdown
# World War II: Causes and Consequences

## Overview
Overview of WWII's historical significance...

## Prerequisites
- Understanding of WWI
- European political geography

## Historical Context

### Root Causes
Economic depression, rise of fascism, Treaty of Versailles...

### Key Figures
Hitler, Churchill, Stalin, Roosevelt...

## Major Events

### Early War (1939-1941)
Blitzkrieg, invasion of Poland, Battle of Britain...

### Turning Point (1942-1943)
Pearl Harbor, Stalingrad, North Africa...

### End of War (1944-1945)
D-Day, fall of Berlin, atomic bombs...

## Consequences

### Political Outcomes
Formation of United Nations, new borders...

### Social Impact
Holocaust, displaced persons, refugee crisis...

## Key Takeaways
- WWII reshaped global politics
- Holocaust demonstrated human atrocity potential
- Led to nuclear age and Cold War

## Summary
World War II fundamentally changed the 20th century...
```

**Hierarchy Check:**
- ✅ Single H1 title
- ✅ Multiple H2 sections (Overview, Prerequisites, Historical Context, Major Events, Consequences, Key Takeaways, Summary)
- ✅ H3 subsections within appropriate H2 sections
- ✅ No jumping levels
- ✅ Logical narrative flow

---

## Content Organization Principles

### Rule 1: One H1 per Document
- The H1 is your document title
- Everything else should be H2 or H3
- Never use multiple H1 headers

### Rule 2: H2 for Major Divisions
- Use H2 to break lecture into logical chapters/sections
- Examples: Overview, Core Concepts, Examples, Applications, Summary
- Each H2 should be distinct and standalone

### Rule 3: H3 for Subdivisions Within H2
- Use H3 only when an H2 section has multiple subtopics
- Each H3 is a related but distinct concept
- If only one subtopic exists under H2, don't use H3

### Rule 4: No Skipping Levels
- Never jump from H1 to H3
- Never jump from H2 to H4 (unless absolutely necessary)
- Always maintain sequential: H1 → H2 → H3

### Rule 5: Limit Depth
- Maximum recommended depth: H3
- If you need H4+, reconsider your organization
- Deeper nesting makes documents hard to navigate

### Rule 6: Consistent Section Names
- Use parallel structure in naming:
  - ✅ "Core Concepts", "Main Ideas", "Key Points" (consistent)
  - ❌ "Key Concepts", "Important Info", "Things to Know" (inconsistent)
- Keep terminology consistent throughout

---

## Hierarchy Checklist

Before finalizing your notes, verify:

- ✅ Exactly one H1 header (the lecture title)
- ✅ Multiple H2 headers (major sections)
- ✅ H3 headers only under appropriate H2 sections
- ✅ No level jumping (no H1→H3, H2→H4, etc.)
- ✅ No excessive nesting (prefer H3, avoid H4+)
- ✅ Consistent naming patterns across sections
- ✅ Each section has distinct content/purpose
- ✅ Logical flow from one section to next
- ✅ Overview/Summary sections present
- ✅ Prerequisites section if content requires prior knowledge

---

## Visual Example: Correct Structure

```
# Lecture Title                           ← H1 (one per document)
│
├─ ## Section 1                           ← H2 (major topics)
│  ├─ ### Subtopic 1.1                    ← H3 (subtopics)
│  ├─ ### Subtopic 1.2                    ← H3
│  └─ ### Subtopic 1.3                    ← H3
│
├─ ## Section 2                           ← H2
│  ├─ ### Subtopic 2.1                    ← H3
│  └─ ### Subtopic 2.2                    ← H3
│
└─ ## Section 3                           ← H2
   (no H3 if no subsections)
```

This structure is clean, scannable, and easy to navigate.

