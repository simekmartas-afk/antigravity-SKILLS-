---
name: planning
description: Creates detailed implementation plans for complex coding tasks. Use when the user asks for a plan or when a task requires multiple steps and files.
---

# Planning & Implementation Design

## When to use this skill
- When the user asks for an implementation plan.
- When a task involves modifying multiple files or complex logic.
- Before starting a large refactoring or feature implementation.

## Workflow
1.  **Analyze Request**: Understand the goal, architecture, and tech stack.
2.  **Create Plan**: Write a `docs/plans/YYYY-MM-DD-<feature>.md` file (or `implementation_plan.md` if preferred by the user's rules) with bite-sized tasks.
3.  **Review**: Present the plan to the user for approval.

## Instructions

### 1. Plan Philosophy
Write comprehensive implementation plans assuming the engineer has zero context. Document everything they need to know: which files to touch, code to write, and how to test it.

**Bite-Sized Task Granularity**:
Break the work down so each step is a single atomic action (2-5 minutes):
- "Write the failing test"
- "Implement minimal code"
- "Run tests"

### 2. Plan Document Format
Every plan MUST start with a clear header and structural breakdown.

```markdown
# [Feature Name] Implementation Plan

**Goal:** [One sentence describing what this builds]

**Architecture:** [2-3 sentences about approach]

**Tech Stack:** [Key technologies/libraries]

---

### Task N: [Component Name]

**Files:**
- Create: `exact/path/to/file.py`
- Modify: `exact/path/to/existing.py:123-145`

**Step 1: Write the failing test**
[Code snippet]

**Step 2: Implementation**
[Code snippet]

**Step 3: Verification**
[Command to run]
```

### 3. Key Principles
- **Exact file paths always**: Never use relative descriptions like "the utils file".
- **Complete code in plan**: Don't say "add validation", show the validation code.
- **Verification steps**: Explicitly state how to verify each step.
- **DRY, YAGNI, TDD**: Encourage best practices in the plan.
