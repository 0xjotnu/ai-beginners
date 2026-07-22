# 🧭 Prompting Claude Well

A practical, example-driven guide to getting great results out of Claude — for beginners and for people who already prompt a lot but want to level up.

> This isn't a reference manual. It's a set of habits, patterns, and before/after examples you can steal.

---

## Why this exists

Most "prompt engineering" advice is either too abstract ("be clear!") or too narrow (one trick for one use case). This repo tries to sit in between: a small number of durable principles, each backed by a real before/after example you can compare side by side.

## Who this is for

- People who want to use Claude daily and want more consistent, higher-quality output
- Developers building on the Claude API who want prompts that hold up in production
- Teams writing internal prompt templates and want a shared vocabulary

## How to use this repo

Read the docs in order if you're new — each one builds on the last. If you already know the basics, jump straight to whichever topic you're stuck on, or browse `examples/` for copy-paste starting points.

## 📚 Contents

| Doc | What it covers |
|---|---|
| [`docs/01-basics.md`](docs/01-basics.md) | The foundation: clarity, specificity, and giving Claude enough context |
| [`docs/02-structure-and-xml.md`](docs/02-structure-and-xml.md) | Using XML tags and structure to organize complex prompts |
| [`docs/03-examples-and-few-shot.md`](docs/03-examples-and-few-shot.md) | Teaching Claude your format and style through examples |
| [`docs/04-chain-of-thought.md`](docs/04-chain-of-thought.md) | Getting better reasoning by asking Claude to think step by step |
| [`docs/05-common-mistakes.md`](docs/05-common-mistakes.md) | The patterns that quietly ruin otherwise-good prompts |

## 🧪 Worked examples

| Example | Task |
|---|---|
| [`examples/email-drafting.md`](examples/email-drafting.md) | Turning a vague ask into consistently well-toned emails |
| [`examples/code-review.md`](examples/code-review.md) | Getting focused, actionable code review instead of generic comments |
| [`examples/data-extraction.md`](examples/data-extraction.md) | Reliable structured data extraction from messy text |

## The short version

If you only remember five things:

1. **Be specific about the outcome, not just the task.** "Write a summary" is a task. "Write a 3-sentence summary a busy exec can skim in 10 seconds" is an outcome.
2. **Show, don't just tell.** One good example of the output you want is worth several sentences of description.
3. **Give Claude room to think before it answers**, especially for anything involving judgment, math, or multi-step reasoning.
4. **Structure long or multi-part prompts** with headers or XML tags so nothing gets lost.
5. **Iterate.** Your first prompt is a draft. Look at what came back, figure out what's missing or wrong, and fix the prompt — not just the output.

## Further reading

For the official, continuously updated reference: [Anthropic's prompt engineering documentation](https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview).

## Contributing

Found a pattern that consistently works (or fails)? Open a PR with a before/after example — that's the most useful unit of content here.

## License

MIT — see [`LICENSE`](LICENSE).
