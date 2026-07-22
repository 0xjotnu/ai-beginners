# 5. Common Mistakes

Patterns that show up constantly in prompts that underperform — often from people who already know the basics.

## 1. Confusing "shorter" with "clearer"

A terse prompt isn't automatically a good prompt. "Fix this" is short and useless without saying what's wrong or what "fixed" looks like. Aim for *precise*, not minimal — cut filler, not information.

## 2. Burying the actual instruction

Putting the real ask in the middle of a long block of context means it can get lost or under-weighted relative to everything around it. Put source material in clearly marked sections (see [structure and XML](02-structure-and-xml.md)) and keep the instruction itself distinct and easy to find — often at the end, right before Claude needs to act on it.

## 3. Negative-only constraints

"Don't be too formal," "don't make it too long," "don't use jargon" — each of these defines a boundary but not a target. Pair negative constraints with positive ones: "Keep it conversational, like you're explaining it to a colleague, in under 150 words, no jargon."

## 4. Assuming Claude remembers context it was never given

In a fresh conversation, or in an API call without prior turns included, Claude only has what's in the current prompt. If a task depends on a decision made three messages ago, or on a document you haven't actually included, restate or re-attach it.

## 5. One giant ask instead of breaking it down

Complex, multi-part tasks ("analyze this dataset, write a report, and also draft three social posts about the findings") often go better as a sequence: get the analysis right first, then build the report from it, then the posts. Each step gives you a checkpoint to catch problems before they compound into the next step.

## 6. Not iterating on the prompt

Treating your first prompt as final and only ever revising the *output* means you never fix the actual cause of a recurring problem. If Claude's answer is consistently missing something, that's usually a gap in the prompt, not a one-off mistake — fix the prompt and the next ten outputs improve too.

## 7. Over-specifying trivial details while under-specifying the ones that matter

Spending three sentences on font preferences while leaving the actual audience, goal, or tone unstated. Prioritize the constraints that would actually change what a good answer looks like.

## 8. Forgetting to specify the output format

If you need a specific structure — JSON, a table, a particular section order — say so explicitly and, ideally, show it. Without that, Claude will pick a reasonable default that may not match what your downstream process expects.

## A quick self-check

Before sending a prompt, skim it for:
- Is the actual instruction easy to spot?
- Would a stranger know exactly what "done" looks like?
- Are there positive alternatives to any "don't" instructions?
- Is anything assumed that isn't actually in the prompt?

---
← Back to [README](../README.md)
