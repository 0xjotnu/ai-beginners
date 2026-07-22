# 🧪 3. Test and Debug

## What you’ll learn

Use AI to investigate a bug without jumping straight to a risky rewrite.

## Debug from evidence

Start with what you observed: the expected result, actual result, exact error, minimal reproduction, and relevant code. Ask the assistant to form hypotheses before proposing a change.

```text
Expected: /total?prices=5,10 returns 15.
Actual: it returns the string "510".
Error: no exception is shown.

Here is the route and its test: [paste only the relevant code]

List likely causes in order. For the most likely cause, propose the smallest
fix and a regression test. Do not refactor unrelated code.
```

## The red-green-refactor loop

1. 🔴 Write or identify a failing test that proves the bug.
2. 🟢 Make the smallest change that makes it pass.
3. 🔵 Clean up only after the test is green.

## Exercise

Create a tiny function with an intentional bug, such as adding strings instead of numbers. Ask an assistant for a test first, then use that test to verify the fix.

## Safety note

An AI-generated test can repeat the same mistaken assumption as the code. Check that the test asserts the behavior your user actually needs.

Next: [Review AI-generated code →](04-reviewing-ai-code.md)
