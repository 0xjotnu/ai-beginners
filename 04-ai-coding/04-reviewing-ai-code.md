# 🔎 4. Review AI-Generated Code

## What you’ll learn

Review an AI suggestion as a developer, even when you are still learning.

## A five-question review

Before accepting a change, ask:

1. **🎯 Does it solve the requested problem?**
2. **🧪 Is there a test or a concrete way to prove it works?**
3. **🧩 Does it fit the project’s existing patterns and public API?**
4. **🔒 Does it expose data, weaken permissions, or introduce unsafe commands?**
5. **✂️ Is the change larger than necessary?**

## A focused review prompt

```text
Review this proposed change as if it were a pull request.

Focus on correctness, edge cases, security, and whether the tests prove the
requirement. Ignore formatting and naming unless they cause a real problem.

For each issue, give the file/function, impact, and a concrete fix. If an area
looks good, say so briefly. Do not assume the change is correct just because it compiles.
```

For a worked version, see [the code-review example](../examples/code-review.md).

## Exercise

Ask an assistant to write a ten-line utility function. Review it with the five questions above before running it. Make one improvement yourself.

Next: [Mini project →](05-mini-project.md)
