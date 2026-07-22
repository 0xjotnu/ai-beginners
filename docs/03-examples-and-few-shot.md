# 3. Examples and Few-Shot Prompting

Description tells Claude what you want in the abstract. Examples show it. For anything involving a specific tone, format, or style of judgment, one good example does more work than several sentences of explanation — and two or three examples covering different cases does even more.

## Why this works

Tone, voice, and format are hard to fully specify in words — "professional but warm" means different things to different people. An example collapses that ambiguity instantly: Claude can pattern-match to the actual thing you want instead of a verbal approximation of it.

## Zero example vs. one example

**No example:**
```
Rewrite this customer complaint response to sound more empathetic.
```

Claude will produce *a* reasonable version of "more empathetic" — but possibly not the one you had in mind.

**One example:**
```
Rewrite the response below to sound more empathetic, matching the
style of this reference response we liked:

<reference>
I completely understand how frustrating that must have been,
especially after waiting three weeks for a resolution. Let's get
this fixed for you today — here's exactly what I'm doing right now...
</reference>

<response to rewrite>
[original response]
</response>
```

Now Claude has a concrete target: specific phrasing patterns, sentence length, how it opens, how it transitions to action.

## Use multiple examples to show a range, not just a style

If a task has edge cases, showing 2-3 examples that cover different situations teaches Claude the *boundaries* of what you want, not just one point in the space.

```xml
<examples>
<example>
<input>Ticket: "App crashes every time I open settings."</input>
<output>Category: Bug | Priority: High | Reason: Reproducible crash blocking core functionality</output>
</example>

<example>
<input>Ticket: "Would be nice if dark mode was a bit darker."</input>
<output>Category: Feature request | Priority: Low | Reason: Cosmetic preference, no functional impact</output>
</example>

<example>
<input>Ticket: "Can't log in, get 'invalid credentials' even with correct password."</input>
<output>Category: Bug | Priority: High | Reason: Blocks account access entirely</output>
</example>
</examples>
```

This teaches the classification logic itself — not just the output format — because the examples span different priority levels and reasoning.

## Keep examples realistic

Examples that are cleaner or simpler than your real inputs will teach Claude a version of the task that doesn't match what it'll actually see. If your real data is messy, include a messy example.

## Don't over-constrain with too many examples

For simple, well-defined tasks, one clear instruction is often enough — piling on five examples for a task that isn't ambiguous just adds length without adding signal. Reach for examples when the *thing you want* is hard to describe in words, not as a default for every prompt.

---
Next: [Chain of thought →](04-chain-of-thought.md)
