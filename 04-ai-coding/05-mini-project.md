# 🏗️ 5. Mini Project: CLI Habit Tracker

## Mission

Build a tiny command-line habit tracker that lets a user add a habit and list saved habits. The point is the workflow, not the size of the app.

## Your build plan

| Checkpoint | Outcome | Ask AI for |
| --- | --- | --- |
| 1 | A project folder and a short README | A minimal structure; no code yet |
| 2 | `add` command accepts one habit name | A single function plus tests |
| 3 | Habits save to a local JSON file | The smallest safe read/write change |
| 4 | `list` command displays saved habits | Test cases for empty and populated lists |
| 5 | One clean commit per checkpoint | A review of the diff and README |

## Starter prompt

```text
I am building a beginner Python CLI habit tracker.

First milestone: design a minimal folder structure and explain the role of
each file. The app will eventually add and list habits stored in a local JSON
file. Use only the Python standard library. Do not write implementation code yet.
```

After you understand the plan, implement one checkpoint at a time. Run the tests after each change, inspect the diff, and commit only working checkpoints.

## Stretch ideas

- Add a `done` command with today’s date.
- Reject blank habit names.
- Export a weekly summary as Markdown.

## Finish line

You have succeeded if you can explain the project structure, run the app, show tests for its core behavior, and point to every change AI helped make.

🎉 Next: revisit the [Prompting module](../03-prompt-engineering/README.md) and try applying its patterns to your own project.
