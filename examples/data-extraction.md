# Example: Structured Data Extraction

**Task:** Pull structured fields out of messy, unstructured text (e.g. support tickets, emails, notes) reliably enough to feed into another system.

## ❌ Before

```
Extract the important info from this support ticket:

[ticket text]
```

**Problem:** "Important info" is undefined, and the output format will vary from one run to the next — sometimes prose, sometimes a list, with inconsistent field names. That's unusable if you're feeding it into a downstream system.

## ✅ After

```xml
<ticket>
[ticket text]
</ticket>

<instructions>
Extract the following fields from the ticket above and return ONLY
valid JSON, no other text, matching this exact shape:

{
  "customer_name": string or null if not mentioned,
  "product": string or null,
  "issue_category": one of ["billing", "technical", "account", "other"],
  "urgency": one of ["low", "medium", "high"],
  "summary": string, one sentence,
  "requires_followup": boolean
}

If a field can't be determined from the ticket, use null (or false
for requires_followup) rather than guessing.
</instructions>
```

**Why this works better:**
- The exact JSON shape removes any ambiguity about field names or nesting — critical if this feeds a script or database
- Constraining `issue_category` and `urgency` to fixed enums prevents drift (e.g. "urgent" vs "high" vs "critical" across different runs)
- "Use null rather than guessing" prevents Claude from inventing plausible-but-wrong values to fill every field
- "Return ONLY valid JSON, no other text" avoids having to strip a preamble like "Here's the extracted data:" before parsing

## A note on reliability at scale

For extraction pipelines processing many documents, it's worth spot-checking a sample of outputs against the source text, especially for edge cases (missing fields, ambiguous categories, unusually formatted input). A few worked examples in the prompt (see [examples and few-shot prompting](../docs/03-examples-and-few-shot.md)) covering those edge cases will improve consistency more than more detailed instructions alone.
