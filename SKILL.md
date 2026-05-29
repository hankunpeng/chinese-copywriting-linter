---
name: chinese-copywriting-linter
description: Lint and automatically format Chinese copywriting and typesetting in Markdown documents according to the Chinese Copywriting Guidelines. Make sure to use this skill whenever the user asks to format, check, clean, lint, or correct spacing, punctuation, and capitalization in Chinese text or documentation, even if they don't explicitly mention 'Chinese Copywriting Linter'.
---

# Chinese Copywriting Linter

A skill to check and auto-correct Chinese typesetting and copywriting style violations in Markdown files, based on the Chinese Copywriting Guidelines.

## When to use

Use this skill when you need to:
- Check for styling issues in Chinese `.md` files.
- Automatically format and correct Chinese writing files (spacing, punctuation, capitalization).
- Ensure consistency in mixed Chinese-English text.

## Core Rules enforced by the Linter

1. **Spacing (空格)**:
   - Must have a space between CJK characters and Latin/numeric characters.
   - Must have a space between numbers and units (e.g., `10 Gbps`).
   - Must not have a space between numbers and degree/percentage symbols (e.g., `90°`, `15%`).
   - Must not have spaces before or after fullwidth punctuation in Chinese text.
   - Must have a space before and after range tilde `~` (e.g., `50 Hz ~ 8000 Hz`).
2. **Punctuation (标点)**:
   - Must use fullwidth punctuation in Chinese text (e.g. `！`, `，`, `？`).
   - Must not duplicate punctuation (e.g. avoid `！！`, `？？`).
   - Must use halfwidth punctuation within pure English phrases or code snippets.
3. **Numbers (数字)**:
   - Must use halfwidth numbers (e.g. `1234` instead of `１２３４`).
4. **Casing (大小写)**:
   - Proper capitalization of technology names (e.g. `GitHub`, `TypeScript`, `JavaScript`, `Next.js`, `React`, `HTML5`, `CSS3`, `VS Code`, `Node.js`, `iPhone`, `MacBook`, `iPad`, `LeanCloud`).

## How to execute the Linter

This skill includes a Python script `linter.py` located in the `scripts/` directory of the skill.

### 1. Run in linting (dry-run) mode
To scan a file or directory for style violations without modifying the content, run:
```bash
python3 /Users/alex/.gemini/config/skills/chinese-copywriting-linter/scripts/linter.py <path/to/file.md_or_dir>
```

### 2. Run in auto-fix mode
To automatically fix all solvable violations directly in the source file:
```bash
python3 /Users/alex/.gemini/config/skills/chinese-copywriting-linter/scripts/linter.py --fix <path/to/file.md_or_dir>
```

## User Communication

After executing the linter, report the findings clearly:
- If issues were found and fixed, show the count of total issues fixed and highlight a few key examples.
- If run in check-only mode, display a detailed report of line numbers, columns, and what violations occurred.
