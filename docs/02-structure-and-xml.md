# 2. Structure and XML Tags

Once a prompt has more than one moving part — instructions, background info, examples, source text — structure stops being a nicety and starts being necessary. Claude is very good at following clearly delimited structure, and noticeably worse at parsing a wall of undifferentiated text where instructions, context, and content all run together.

## Why XML tags work well

Claude was trained extensively on data containing XML-like tags, so it pays close attention to content wrapped this way and treats tag names as meaningful signals about what's inside. Unlike markdown headers, tags can nest and wrap arbitrary content without ambiguity about where a section ends.

## A simple example

**Unstructured (works, but is easy to misread):**
```
Summarize the following article for a 10 year old. Keep it under
100 words. Here is the article: [long article text] Also make sure
to mention the main scientist's name.
```

Where does the article end? Where does the instruction resume? A human can figure it out, but it's doing unnecessary work — and with a longer article, it gets genuinely ambiguous.

**Structured:**
```xml
<instructions>
Summarize the article below for a 10 year old. Keep it under 100
words, and make sure to mention the main scientist's name.
</instructions>

<article>
[long article text]
</article>
```

Now there's no ambiguity about what's instruction and what's content.

## Common tags worth using

There's no fixed schema — pick names that describe the content:

- `<context>` / `<background>` — situational info Claude needs but shouldn't necessarily act on directly
- `<instructions>` — the actual task
- `<examples>` — sample input/output pairs (see [few-shot examples](03-examples-and-few-shot.md))
- `<document>` / `<data>` — source material to work from
- `<formatting>` — output format requirements
- Custom tags for your domain — `<transcript>`, `<code>`, `<ticket>`, whatever matches your content

## Referencing tags in your instructions

Once content is tagged, you can refer back to it by name, which makes multi-step instructions much easier to follow:

```xml
<document>
[contract text]
</document>

<instructions>
Read the document above. List every clause in <document> that
mentions a payment deadline, quoting the exact clause number.
</instructions>
```

## For long documents, put instructions last

If you're including a long document or dataset, consider putting your actual instructions *after* the content rather than before. This matters more as documents get long — Claude attends well to instructions positioned close to where it needs to act on them.

## Nesting for multi-part prompts

Tags can nest to organize genuinely complex prompts:

```xml
<task>
  <context>We're a B2B SaaS company launching a pricing change.</context>
  <audience>Existing customers on legacy plans.</audience>
  <instructions>Draft an email announcing the change.</instructions>
  <constraints>
    - Under 200 words
    - No mention of competitors
    - Must include the effective date: March 1, 2027
  </constraints>
</task>
```

## The takeaway

Structure isn't about making prompts look formal — it's about removing ambiguity between "here is information" and "here is what to do with it." As soon as a prompt has more than one section, that boundary is worth marking explicitly.

---
Next: [Examples and few-shot prompting →](03-examples-and-few-shot.md)
