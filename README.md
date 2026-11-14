# Lecture-to-Markdown Notes Skill — Quick Reference

## Skill Overview

**Name:** `lecture-to-markdown-notes`

**Purpose:** Convert raw lecture materials (transcripts, slides, course content) into well-organized, detailed markdown study notes suitable for personal study and review.

**Status:** ✅ Complete and ready for testing

---

## File Structure

```
lecture-to-markdown-notes/
├── SKILL.md (400+ lines)
│   - Core skill instructions and guidelines
│   - When to trigger, what to produce
│   - Step-by-step workflow for conversion
│   - Quality standards and examples
│
├── references/ (1,600+ lines total)
│   ├── formatting-guide.md (~300 lines)
│   │   └── Code blocks, LaTeX, tables, callouts, lists
│   ├── hierarchy-rules.md (~435 lines)
│   │   └── H1/H2/H3 structure, common mistakes, examples
│   ├── content-adapters.md (~550 lines)
│   │   └── Programming, math, and narrative formatting rules
│   └── detail-balance.md (~400 lines)
│       └── Reading time targets, what to include/exclude
│
└── assets/templates/ (1,000+ lines total)
    ├── code-heavy.md (~400 lines)
    │   └── Python Functions & Scope — complete programming example
    ├── math-heavy.md (~400 lines)
    │   └── Calculus: Limits & Continuity — complete math example
    └── narrative.md (~400 lines)
        └── Civil Rights Movement — complete humanities example
```

---

## Key Features

### ✅ Implemented Features

- **Content-aware formatting**: Adapts structure based on lecture type (code, math, narrative)
- **Consistent hierarchy**: Clear H2/H3 structure with no level-jumping
- **Inline examples**: Every concept includes at least one concrete example
- **Smart Q&A handling**: Questions include source metadata (exam year, quiz type)
- **Flexible prerequisites**: Included only when lecture actually requires prior knowledge
- **Detail balance**: Targets 15-25 minute reading time (~3,500-6,500 words)
- **Multiple templates**: Reference examples for each lecture type
- **Comprehensive guidelines**: Rules for code blocks, LaTeX, tables, callouts, lists

### Quality Standards

- ✅ Simple, clear language appropriate to subject level
- ✅ Inline examples for every concept (not separate sections)
- ✅ Consistent markdown formatting and hierarchy
- ✅ Key terms properly highlighted (**bold** or `backticks`)
- ✅ Content reorganized logically, not original slide order
- ✅ No slide number references (only Q&A source metadata)
- ✅ Clean transitions between concepts
- ✅ Proper use of tables, code blocks, and callouts

---

## How the Skill Works

### Input
- Lecture transcript or slide content (text or PDF)
- Can be single or multiple files
- Any subject domain

### Process
1. **Analyze** — Identify lecture type and extract key concepts
2. **Organize** — Reorganize content into logical, progressive structure
3. **Format** — Apply type-specific formatting rules
4. **Structure** — Create clean markdown with proper hierarchy
5. **Review** — Verify quality against standards

### Output
- Well-formatted markdown study notes (~3,500-6,500 words per lecture)
- Clean TOC, sections, and subsections
- Inline examples, callouts, and highlighted terms
- Q&A with source attribution
- Reading time 15-25 minutes

---

## Reference Documents Quick Guide

### formatting-guide.md
Use when you need to verify:
- ✅ Correct code block syntax
- ✅ LaTeX equation formatting
- ✅ Table structure and alignment
- ✅ Callout styling ("**Note:**", "**Important:**", etc.)
- ✅ List formatting (bullets vs. numbered)

### hierarchy-rules.md
Use when you need to verify:
- ✅ Header level usage (H1, H2, H3)
- ✅ Avoiding level-jumping mistakes
- ✅ Consistent structure across sections
- ✅ Proper nesting of subtopics

### content-adapters.md
Use when you need to verify:
- ✅ Programming lecture formatting (code blocks, complexity tables, pitfalls)
- ✅ Math lecture formatting (LaTeX, derivations, proofs, tables)
- ✅ Narrative lecture formatting (quotes, timelines, context)
- ✅ Mixed-type content handling

### detail-balance.md
Use when you need to verify:
- ✅ Appropriate level of detail
- ✅ Reading time targets
- ✅ What to include vs. exclude
- ✅ Identifying over/under-explanation

### Template Examples
- **code-heavy.md** — Python Functions: Shows programming format with code blocks, examples, complexity, pitfalls
- **math-heavy.md** — Calculus Limits: Shows math format with definitions, LaTeX, step-by-step solutions, proofs
- **narrative.md** — Civil Rights Movement: Shows narrative format with context, timelines, key figures, significance

---

## Testing Strategy

### Test Cases (Ready to Create)

**Test 1: Programming Lecture**
- Input: Python/JavaScript lecture with code examples and algorithms
- Expected: Code blocks with syntax highlighting, algorithms, complexity analysis, inline examples
- Success criteria: Proper code formatting, organized logically, all concepts explained

**Test 2: Mathematics Lecture**
- Input: Calculus or Physics lecture with formulas and derivations
- Expected: LaTeX equations, step-by-step solutions, theorems, applications
- Success criteria: Math formatted correctly, prerequisites if needed, clear explanations

**Test 3: Humanities Lecture**
- Input: History or literature lecture with context and questions
- Expected: Narrative flow, highlighted key figures/events, timelines, Q&A with sources
- Success criteria: Readable prose, context included, questions have metadata

---

## Next Steps

### Phase 1: Testing (Ready to Begin)
1. Create 3 test prompts (programming, math, humanities)
2. Run tests using Claude with the skill
3. Evaluate outputs against success criteria
4. Gather user feedback

### Phase 2: Iteration (If Needed)
1. Review test results with user
2. Identify any improvements needed
3. Update skill instructions or reference guides
4. Retest if major changes needed

### Phase 3: Optimization (Final)
1. Optimize skill description for triggering
2. Fine-tune edge cases based on feedback
3. Package final skill for deployment

---

## Triggering Contexts

The skill should trigger when:

- User shares lecture transcripts, slides (PDF/TXT), or course materials
- User asks to convert lecture content into study notes
- User requests organized documentation from educational material
- User wants to create detailed markdown notes from academic sources
- User has multiple lecture files needing conversion with consistent formatting

---

## Success Criteria Summary

✅ **All key concepts extracted** with clear definitions  
✅ **Inline examples** (1-2 minimum) for every concept  
✅ **Proper markdown formatting** (valid syntax)  
✅ **Consistent hierarchy** (no H1→H3 jumps)  
✅ **Tables/code blocks** used appropriately  
✅ **Questions include source metadata** (exam type, year)  
✅ **Prerequisites present only when needed**  
✅ **Content reorganized logically**, not in original order  
✅ **Reading time 15-25 minutes** (comprehensively detailed without overwhelming)  
✅ **Notes are standalone** (don't require referencing original source)  

---

## File Statistics

| File | Lines | Purpose |
|:---|---:|:---|
| SKILL.md | ~400 | Core instructions |
| formatting-guide.md | ~300 | Formatting examples |
| hierarchy-rules.md | ~435 | Structure guidelines |
| content-adapters.md | ~550 | Type-specific rules |
| detail-balance.md | ~400 | Depth guidelines |
| code-heavy.md | ~400 | Programming template |
| math-heavy.md | ~400 | Mathematics template |
| narrative.md | ~400 | Humanities template |
| **TOTAL** | **~2,985** | Complete skill |

---

## Ready for Testing

This skill is now complete and ready for evaluation. All components are in place:

- ✅ Core instructions (SKILL.md)
- ✅ Reference documentation (4 comprehensive guides)
- ✅ Template examples (3 complete working examples)
- ✅ Clear quality standards and success criteria
- ✅ Comprehensive guidelines for all lecture types

**Next action:** Create and run test cases to validate the skill's effectiveness.

