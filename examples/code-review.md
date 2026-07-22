# Example: Code Review

**Task:** Get a genuinely useful code review instead of generic style comments.

## ❌ Before

```
Review this code:

[code]
```

**Problem:** With no scope, Claude tends to spread attention evenly across style nitpicks, naming conventions, and substantive issues — and you get a wall of comments where the important ones are easy to miss.

## ✅ After

```xml
<code language="python">
[code]
</code>

<instructions>
Review the code above. Focus specifically on:
1. Correctness bugs — anything that would produce wrong output or crash
2. Edge cases that aren't handled (empty input, None values, concurrent access)
3. Security issues, if any

Do NOT comment on style, naming, or formatting — we have a linter
for that.

For each issue found, give:
- The line number or function name
- What's wrong
- A concrete fix (a code snippet, not just a description)

If you find no issues in a category, say so briefly rather than
skipping it silently.
</instructions>
```

**Why this works better:**
- Explicitly scoping *out* style comments stops them from crowding out substantive ones
- Naming the categories to check (correctness, edge cases, security) means Claude actively checks for each rather than reporting only what's most visually obvious
- Asking for a concrete fix, not just a description, makes the output directly actionable
- "Say so briefly rather than skipping it silently" prevents ambiguity between "no issues found" and "didn't check"

## Variation: reviewing against a specific standard

If your team has conventions Claude wouldn't otherwise know, include them:

```xml
<team_conventions>
- All public functions must have type hints and docstrings
- We use custom exceptions from errors.py, never bare Exception
- Database calls must go through the repository layer, not direct ORM calls in route handlers
</team_conventions>
```
