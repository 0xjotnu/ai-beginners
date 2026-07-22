# 1. The Basics: Clarity, Specificity, Context

Everything else in this repo is a refinement of one idea: **Claude can only work with what you give it.** Vague input reliably produces vague, generic, or misaligned output — not because Claude is guessing badly, but because there was genuinely more than one reasonable way to interpret the request.

## Treat Claude like a smart new hire, not a mind reader

A capable new hire can do great work, but only if you tell them:
- What the actual goal is (not just the task)
- Who the output is for
- What "done well" looks like
- Any constraints they wouldn't otherwise know about

Claude is the same. It has broad knowledge but zero context about your specific situation unless you supply it.

## Before / after

**Vague:**
```
Write a product description for my headphones.
```

**Specific:**
```
Write a product description for wireless noise-cancelling headphones,
for an Amazon listing. Audience: commuters and remote workers.
Tone: confident but not hypey — no "revolutionary" or "game-changing."
Length: 3 short paragraphs. Lead with the noise cancellation, since
that's our main differentiator vs. the competitor at this price point.
```

The second prompt doesn't just describe the task — it describes the *decision space*: audience, tone, structure, and what to emphasize. Claude no longer has to guess at five different things simultaneously.

## Say what you want, not just what you don't want

"Don't make it too long" tells Claude one boundary. "Keep it to two paragraphs" tells Claude exactly where to land. Positive, concrete instructions are easier to follow than negative, vague ones.

## Give Claude the material it needs

If the task depends on facts, data, prior conversations, or a document, include them. Claude won't infer specifics it wasn't given — and asking Claude to "guess" the details of your codebase, your company's style guide, or your customer's complaint history produces exactly what you'd expect: a plausible-sounding guess.

## Specify the output format explicitly

If you need JSON, a table, markdown, or a specific structure, say so — and ideally show the shape you want. "Give me the results" is ambiguous between prose, a list, and a table. "Give me a markdown table with columns Name, Score, Notes" is not.

## A useful test

Before sending a prompt, ask: *if I handed this exact text to a smart colleague who knows nothing about my project, would they produce what I actually want?* If there's a step where they'd have to guess, that's the gap to fill.

---
Next: [Structure and XML tags →](02-structure-and-xml.md)
