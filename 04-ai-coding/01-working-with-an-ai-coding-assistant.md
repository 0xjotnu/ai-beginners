# 🤝 1. Work With an AI Coding Assistant

## What you’ll learn

Turn a fuzzy request into a small coding task an AI assistant can help you implement and you can still understand.

## Ask for a slice, not a whole product

“Build me a social app” is too large to review. “Add a function that validates an email address and write five tests” is small enough to understand, test, and improve.

## A strong first request

```text
I am learning Python and have a small command-line project.

Task: Add a function called `is_valid_email` in validators.py.
Requirements:
- Return True only when the value contains one @ and text on both sides.
- Return False for empty strings and non-string input.
- Do not add external packages.

First explain your plan in three bullets. Then show the smallest code change
and five pytest test cases. Explain how I can run the tests.
```

## Why this works

You gave the assistant the language, location, goal, boundaries, desired output, and a request for tests. That sharply reduces guessing.

## Exercise

Choose a tiny feature from a project or tutorial you are following. Write a request with a task, relevant context, at least two constraints, and a test request. Before accepting any code, explain every line you do not recognize.

## Safety note

Do not run generated commands blindly. Check what an install, script, or database command will do first.

Next: [Give code context safely →](02-giving-code-context.md)
