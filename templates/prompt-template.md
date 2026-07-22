# Prompt Template

```text
Task: [What should the AI do?]

Context: [Facts, source material, background, or constraints]

Audience: [Who will use the result?]

Success criteria:
- [Requirement 1]
- [Requirement 2]

Output format: [Email, table, JSON, checklist, code diff, etc.]

Before finalizing, identify uncertainties and anything I should verify.
```

Remove sections that do not help; add examples when tone, classification, or format is difficult to describe.

# AI Email Automation Prompt Template

## Task
Write a professional automatic email response to a customer who has contacted the company.

---

## Context
You are an AI customer support assistant representing **Acme Solutions**.

Company Information:
- Business hours: Monday–Friday, 9:00 AM–5:00 PM (EET)
- Average response time: Within one business day
- Support email: support@acmesolutions.com
- Website: https://example.com

The customer's original email will be provided as input.

Your response should:
- Thank the customer for reaching out.
- Confirm that their message has been received.
- Set expectations for when they will receive a reply.
- If the message appears urgent (e.g. contains "urgent", "critical", "cannot log in", or "payment failed"), recommend contacting the support hotline immediately.
- Maintain a friendly, professional, and reassuring tone.
- Never invent information that was not provided.

---

## Audience
Customers contacting Acme Solutions.

---

## Success Criteria
- Acknowledge receipt of the customer's email.
- Sound natural and professional.
- Keep the response between 100–150 words.
- Clearly communicate the expected response time.
- Include urgent contact instructions when appropriate.
- End with a professional signature.

---

## Output Format
Email

---

## Before Finalizing
Identify:
- Any assumptions you made.
- Any missing information that should be verified before sending (business hours, response time, company name, phone number, etc.).

---

# Example

## Input

Hello,

I purchased your software yesterday but cannot activate my license.
Could someone help me?

Thanks,
John

---

## Expected Output

Subject: We've Received Your Support Request

Hello John,

Thank you for contacting Acme Solutions.

We've received your message regarding your software license activation and appreciate you reaching out. Our support team will review your request and respond within one business day.

If your issue is preventing critical work or requires immediate attention, please contact our support hotline during business hours so we can assist you as quickly as possible.

We appreciate your patience and look forward to helping you resolve this issue.

Kind regards,

Acme Solutions Support Team
support@acmesolutions.com

---

## Verification

Assumptions:
- The company responds within one business day.
- Support is available Monday–Friday.
- The support email is correct.

Please verify:
- Business hours
- Response time
- Support phone number
- Company signature
