# 4. Chain of Thought: Letting Claude Think First

For tasks involving math, multi-step logic, tradeoffs, or judgment calls, asking Claude to reason through the problem before giving a final answer tends to produce more accurate, more defensible results than asking for the answer directly.

## Why this helps

Jumping straight to a conclusion means committing to an answer before working through the considerations that should inform it. Working through the reasoning first — identifying the relevant factors, checking them against each other — means the final answer is actually downstream of that reasoning, not a guess that reasoning gets bolted onto afterward.

## A simple version: just ask for it

```
A customer wants a refund on a product they've used for 45 days.
Our policy allows refunds within 30 days, but she says the product
was defective from day one and she has photos proving it.

Think through the relevant policy considerations step by step, then
give your recommendation.
```

Without the "think step by step" instruction, Claude might jump straight to "per policy, no refund" or "yes, refund" without weighing the defect claim against the policy window — both real considerations that deserve to be weighed against each other explicitly.

## A more structured version: separate thinking from the answer

For cases where you want a clean final answer *and* the reasoning behind it, tags help separate the two:

```xml
<instructions>
Work through this step by step inside <thinking> tags, then give
your final recommendation inside <answer> tags. The answer should
be usable on its own without needing the thinking section.
</instructions>
```

This is useful when the reasoning is for your own review (or an audit trail) but the person reading the final output just wants the conclusion.

## Where this matters most

- Math and multi-step calculations
- Anything with competing constraints or tradeoffs (like the refund example)
- Debugging — reasoning through what could cause a symptom before proposing a fix
- Editorial or judgment calls where the *why* matters as much as the *what*

## Where it matters less

For simple factual lookups or straightforward formatting tasks, forcing an explicit reasoning step just adds length without changing the answer. Reach for this when the task actually requires weighing something — not as a default for every prompt.

## A common mistake

Asking Claude to "think step by step" but only in your head, i.e. not actually giving it space to write that reasoning out. The value comes from Claude generating the intermediate reasoning as output, not from you silently hoping it happens internally — so make sure your prompt or format actually allows for a reasoning section rather than demanding a single-line answer.

---
Next: [Common mistakes →](05-common-mistakes.md)
