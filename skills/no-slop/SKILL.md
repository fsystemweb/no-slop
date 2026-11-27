---
name: no-slop
description: Prevents AI-slop code comments. Use whenever writing, editing, refactoring, or reviewing code in any language, and before finishing any coding task.
---

# No Slop Comments

Comments explain **why**, never **what**. If the code already says it, don't write it.

## Don't

- Narrate operations, assignments, conditions, loops, calls, or returns.
- Walk through the implementation step by step (`// Step 1: ...`).
- Add section banners or headers inside functions.
- Restate what a name, type, test, or docstring already says.
- Describe the change you just made (`// now uses X`, `// added for Y`). That belongs in the commit.
- Write for the reviewer or for an AI (`// this handles the edge case`).
- Document trivial or private code. Keep docstrings short and for public APIs or genuinely complex behavior.

## Do

- Fix unclear code with better names and smaller functions before reaching for a comment.
- Comment only what the code can't show: business rules, architectural decisions, technical constraints, workarounds, non-obvious edge cases.
- Keep existing meaningful comments. Remove ones that become redundant, outdated, or wrong when you touch the code they describe.

## Before finishing

Review your diff and delete every comment that adds no context beyond the code.
