# 🧩 2. Give Code Context Safely

## What you’ll learn

Provide enough context for a helpful answer without dropping your entire repository or private data into a prompt.

## Give the assistant a map

For most changes, share only the relevant pieces:

- The language, framework, and package manager
- The exact error message or expected behavior
- The relevant function, file, or a small directory tree
- Existing tests and important conventions
- Constraints such as “no new dependencies” or “keep this API compatible”

```text
Project: Node.js + TypeScript API
Relevant files: src/auth/login.ts and tests/login.test.ts
Problem: valid users receive a 401 after login
Constraint: do not change the response schema or add packages

Read the code below. List your two most likely hypotheses first. Then suggest
the smallest change and the test that would prove the fix.
```

## Keep secrets out

Never paste `.env` files, access tokens, private keys, connection strings, customer records, or proprietary source code into a tool unless it is approved for that information. Replace values with clear placeholders, such as `DATABASE_URL="<redacted>"`.

## Exercise

Take an old error message or a public open-source issue. Write a context block that gives only the information needed to investigate it.

Next: [Test and debug →](03-testing-and-debugging.md)
