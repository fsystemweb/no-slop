---
name: no-slop
description: Keeps code comments meaningful and free of AI slop. Use whenever writing, editing, or reviewing code.
---

# Commenting Policy

Keep the codebase clean, concise, and easy to read.

**Avoid unnecessary comments.** Don't write comments explaining what the code is doing when the implementation is already self-explanatory.

1. Do not add comments describing obvious operations, assignments, conditions, loops, function calls, or return statements.
2. Do not add comments explaining code line by line or narrating implementation steps.
3. Prefer meaningful variable names, function names, and clear abstractions over comments.
4. Only add comments when necessary to explain non-obvious business logic, architectural decisions, technical constraints, workarounds, or important edge cases.
5. Do not add comments just to make the code look documented or easier for an AI to understand.
6. Preserve existing meaningful comments, but remove redundant, outdated, or misleading comments when modifying the relevant code.
7. Never duplicate information already available in function names, type definitions, docstrings, tests, or surrounding implementation.
8. Keep docstrings concise and focused on public APIs or genuinely complex behavior.

**Before finishing a task, review your changes and remove any comments that do not provide meaningful additional context.**

General principle: comments explain **why**, not **what**. Prioritize readability through good code structure rather than excessive explanations.
