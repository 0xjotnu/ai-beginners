# Example: Email Drafting

**Task:** Draft a follow-up email to a client after a delayed project delivery.

## ❌ Before

```
Write an email to a client apologizing for a late delivery.
```

**Problem:** Claude has to guess the relationship, the reason for the delay, whether to offer compensation, how formal to be, and how long the email should be. You'll likely get something generic and need several rounds of edits.

## ✅ After

```xml
<context>
We're a design agency. We delivered the final brand assets to a
client 5 business days late due to an internal resourcing issue.
This is a long-term client (2 years) and the relationship is good —
this is the first delay we've had with them.
</context>

<instructions>
Write a follow-up email to the client:
- Acknowledge the delay directly, no over-apologizing
- Briefly note the cause (internal resourcing) without over-explaining
- Confirm the assets are now delivered and ready for their review
- Offer a specific goodwill gesture: 10% off their next invoice
- Tone: warm, direct, professional — like writing to someone we
  know well, not a form apology
- Length: under 150 words
</instructions>
```

**Why this works better:**
- `<context>` gives Claude the relationship history, which changes the appropriate tone (a first-time delay with a good client reads differently than a pattern of delays)
- The instructions separate *what* to cover from *how* to say it
- A concrete constraint ("10% off next invoice") replaces a vague one ("offer something")
- The length and tone constraints prevent the generic, over-apologetic default

## Variation: matching an existing voice

If you have a reference email that sounds right, add it as an example (see [examples and few-shot prompting](../docs/03-examples-and-few-shot.md)):

```xml
<reference_tone>
[a previous email in your company's actual voice]
</reference_tone>

<instructions>
Match the tone and sentence rhythm of the reference above.
</instructions>
```
