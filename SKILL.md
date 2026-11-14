---
name: lecture-to-markdown-notes
description: Convert lecture transcripts and slides into detailed, well-organized markdown study notes. Use this skill whenever a user shares lecture materials (PDFs, transcripts, slides) in text or PDF format and wants to transform them into structured notes for learning and review. Also use when users explicitly ask to "convert this lecture into notes", "organize this material", "create study notes from this content", or similar requests. Handles programming lectures (with code examples), mathematics/STEM lectures (with equations and derivations), and narrative lectures (history, humanities, literature). Produces clean, hierarchical markdown with tables, code blocks, highlighted key terms, inline examples, and extracted Q&A with source attribution.
---

# Lecture-to-Markdown Notes Converter

## Purpose

Transform raw lecture materials (transcripts, slide text, course content) into comprehensive, well-organized markdown notes suitable for personal study, review, and later reference. The notes maintain appropriate detail—enough to understand fully without being overwhelming—and adapt formatting based on lecture type (programming, mathematics, narrative).

## When to Use This Skill

- User provides lecture transcripts or slide content in TXT or PDF format
- User asks to convert educational material into organized notes
- User wants structured study notes from academic lectures
- User requests documentation from course materials or presentations
- Multiple lecture files need to be converted into separate, labeled notes

## What This Skill Produces

Well-structured markdown notes that include:
- **Clear table of contents** (auto-generated from sections)
- **Overview section** (2-3 sentence summary of main topics)
- **Prerequisites section** (only when the lecture actually requires prior knowledge)
- **Organized main concepts** with definitions, key points, and inline examples
- **Consistent hierarchy** (H2 for major topics, H3 for subtopics—no jumping levels)
- **Formatted elements**: Code blocks for programming, LaTeX for math, tables for data/comparisons
- **Key takeaways** (3-5 bullet points summarizing main ideas)
- **Questions & Answers section** (extracted Q&A with source metadata: exam year, quiz type, etc.)
- **Final summary** connecting all concepts together

## Core Instructions

### Step 1: Analyze Input Content

1. **Identify the lecture type**:
   - **Programming/Code-heavy**: Contains code examples, algorithms, software concepts
   - **Mathematics/STEM**: Contains formulas, equations, derivations, scientific concepts
   - **Narrative**: History, literature, humanities, social sciences, descriptive content
   - **Mixed**: Multiple types (apply formatting rules for each)

2. **Extract key information**:
   - Main concepts and definitions
   - Examples and use cases
   - Formulas, equations, algorithms
   - Questions with their source/context (exam year, quiz number, etc.)
   - Diagrams or visual descriptions (describe in text)

3. **Assess prior knowledge**: Does this lecture heavily build on prerequisites? Only include a prerequisites section if YES.

### Step 2: Organize Content Logically

- **Reorganize from scratch**, NOT in original slide/source order
- Group related concepts together
- Follow logical progression: simple → complex
- Ensure smooth transitions between topics
- Create a clear hierarchy (no H1→H3 jumps, no skipped levels)

### Step 3: Format Content Appropriately

#### For Programming Lectures:
- Use syntax-highlighted code blocks (```python, ```javascript, etc.)
- Include algorithms, pseudocode, and code snippets inline after concepts
- Highlight common pitfalls or gotchas
- Use tables for comparisons (e.g., method differences, time complexity)

#### For Mathematics/STEM Lectures:
- Use LaTeX for equations and formulas: `$$equation$$` (display) or `$equation$` (inline)
- Show step-by-step derivations under relevant concepts
- Use tables for formula collections, unit conversions, data
- Include worked examples with solutions

#### For Narrative Lectures:
- Use clear, descriptive prose
- **Bold** or `highlight` important figures, events, dates, terminology
- Use tables for timelines, comparisons, or structured data
- Include context and connections between ideas

### Step 4: Generate the Markdown Structure

Follow this template structure:

```markdown
# [Lecture Title / Topic Name]

## Overview
[2-3 sentence summary of main topics]

## Table of Contents
[Auto-generate based on H2 sections below]

## Prerequisites (if needed)
- [Background concept 1]
- [Background concept 2]

## [Main Topic 1]
### [Subtopic 1.1]
Definition and explanation with simple language.

**Example:**
[Inline example—code, equation, or concrete instance]

### [Subtopic 1.2]
[Same structure]

## [Main Topic 2]
### [Subtopic 2.1]
[Similar structure]

## Key Takeaways
- [Main idea 1]
- [Main idea 2]
- [Main idea 3]

## Questions & Answers

### Question 1 [Source: 2002 IIT Previous Year / Midterm Exam / Quiz 3]
**Q:** [Question text]
**A:** [Answer with explanation]

### Question 2 [Source: ...]
**Q:** [Question text]
**A:** [Answer with explanation]

## Summary
[Final paragraph connecting all concepts and their relationships]
```

### Step 5: Apply Quality Guidelines

- **Simple Language**: Explain concepts in easy-to-understand terms appropriate for the subject level
- **Inline Examples**: Every concept should have at least 1-2 examples immediately following it (not in separate sections)
- **Consistent Hierarchy**: Use H2 for major topics, H3 for subtopics only. Never jump from H1→H3 or H2→H4
- **Key Term Formatting**: **Bold** for important terms or use `backticks` for technical terms
- **Smart Use of Formatting**:
  - Tables: For comparisons, timelines, structured data, formulas
  - Code blocks: For programming examples, pseudocode, algorithms
  - Callouts: Use "**Note:**", "**Important:**", "**Example:**", "**Tip:**" when helpful
- **Question Source Metadata**: Always include where questions came from (e.g., "2002 IIT Previous Year", "Midterm Exam Q5", "Practice Problem Set 3")
- **Detail Balance**: Include enough to fully understand the material but not so much that it becomes overwhelming. Target reading time: 15-25 minutes

### Step 6: Handle Multiple Files

If the user provides multiple lecture files:
1. Create a separate markdown note for each file
2. Label each note with the file name or lecture title
3. Maintain consistent formatting across all notes

### Step 7: Review Before Delivery

- ✅ All sections follow proper markdown syntax
- ✅ Hierarchy is consistent (no level jumps)
- ✅ Examples are inline with concepts
- ✅ Formatting (code, math, tables) is appropriate to content type
- ✅ Question sources are clearly labeled
- ✅ Prerequisites section only included if needed
- ✅ Content is reorganized logically, not in original order
- ✅ Reading time is reasonable (15-25 minutes)

## Examples of Good Output

### Programming Lecture Example
```markdown
# Python Functions and Scope

## Overview
This lecture covers how to define and use functions in Python, including parameters, return values, and variable scope.

## Main Concepts

### Function Definition
A function is a reusable block of code that performs a specific task.

**Example:**
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))  # Output: Hello, Alice!
```

### Variable Scope
Variables have different scopes: local (inside function), global (outside functions).

**Important:** A local variable with the same name as a global variable will shadow (hide) the global one inside the function.

**Example:**
```python
x = 10  # global

def my_function():
    x = 20  # local - shadows global x
    print(x)

my_function()  # Output: 20
print(x)  # Output: 10
```
```

### Math Lecture Example
```markdown
# Calculus: Derivatives

## Prerequisites
- Understanding of limits
- Algebraic manipulation skills

## Main Concepts

### The Derivative
The derivative of a function $f(x)$ represents the rate of change at any point.

$$f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$$

**Example:** Find the derivative of $f(x) = x^2$

**Step-by-step:**
1. $f(x+h) = (x+h)^2 = x^2 + 2xh + h^2$
2. $f(x+h) - f(x) = 2xh + h^2$
3. $\frac{f(x+h) - f(x)}{h} = 2x + h$
4. $\lim_{h \to 0} (2x + h) = 2x$

Therefore, $f'(x) = 2x$
```

## See Also

- `references/formatting-guide.md` — Detailed formatting examples
- `references/hierarchy-rules.md` — Rules for consistent structure
- `references/content-adapters.md` — Type-specific formatting guidance
- `references/detail-balance.md` — Guidelines for appropriate detail level
- `assets/templates/` — Template examples for different lecture types

---

**Author**: Lecture-to-Markdown Notes Converter Skill  
**Last Updated**: 2026-11-14  
**Version**: 1.0
