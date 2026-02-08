---
name: brainstorming
description: Explores user intent, requirements, and design before implementation. Use when the user has a vague idea, wants to discuss a new feature, or asks for design advice.
---

# Brainstorming & Design Exploration

## When to use this skill
- When the user says "I have an idea..." or "How should I build..."
- Before writing any code for a new, undefined feature.
- When requirements are ambiguous.

## Workflow
1.  **Understand**: Ask questions to clarify the goal and constraints.
2.  **Explore**: Propose multiple approaches with trade-offs.
3.  **Refine**: Narrow down to a single design through dialogue.
4.  **Document**: Finalize the design into a spec.

## Instructions

### 1. Understanding the Idea
- **Check Context**: Look at existing files and docs first.
- **One Question at a Time**: Don't overwhelm the user. Ask one clear question per message.
- **Multiple Choice**: When possible, offer options (A, B, C) to make answering easier.
- **Focus**: Pin down the purpose, constraints, and success criteria.

### 2. Exploring Approaches
- Propose 2-3 different technical approaches.
- Explain the trade-offs (Pros/Cons) for each.
- Give a recommendation, but leave the final choice to the user.

### 3. Presenting the Design
- Once the path is chosen, present the design in small sections (200-300 words).
- check for agreement after each section ("Does this look right so far?").
- Cover: Architecture, Components, Data Flow, Error Handling, and Test Strategy.

### 4. Key Principles
- **YAGNI Ruthlessly**: Remove unnecessary features.
- **Incremental Validation**: Don't dump a massive spec at once. Validate piece by piece.
- **Be Flexible**: If the user changes their mind, adapt the design immediately.
