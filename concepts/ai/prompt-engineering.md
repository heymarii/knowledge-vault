# Prompt Engineering Fundamentals

**Category:** AI / Prompt Engineering  
**Last updated:** 2026-03-27

---

## The Core Insight

Prompting is programming in natural language. The same discipline that makes code readable — clarity, specificity, structure — makes prompts effective.

## The 5 Fundamentals

### 1. Be Specific About the Task
Vague: `"Write something about climate change"`  
Specific: `"Write a 200-word explanation of carbon capture technology for a non-technical audience"`

### 2. Give Context
The model doesn't know who you are, what you're building, or what "good" means unless you tell it.

```
Context: You are helping me write documentation for a Python library used by data scientists.
Audience: Experienced Python developers, new to this library.
Tone: Technical but friendly. Use code examples.
```

### 3. Specify the Output Format
Models will match your format if you show them what you want:
- Use headers and bullets in your prompt → you'll get headers and bullets back
- Provide an example output → model will follow the pattern
- Use XML tags to structure inputs and outputs

### 4. Use Chain-of-Thought for Hard Problems
Add `"Think step by step"` or `"Let's work through this carefully"` for reasoning-heavy tasks. It genuinely helps.

### 5. Iterate and Version
Your first prompt is almost never your best prompt. Treat prompts like code: version them, test them, refine them.

## The XML Trick

Claude (and other models) respond well to XML-tagged content:

```
<task>Review this code for security issues</task>
<code language="python">
{code here}
</code>
<output_format>List issues by severity: CRITICAL, HIGH, MEDIUM, LOW</output_format>
```

This helps the model understand what's instruction vs. data.

## Anti-Patterns

- **Over-constraining:** So many rules that the model can't do anything well
- **Under-specifying:** Assuming the model knows what you mean
- **No examples:** Showing is usually better than telling
- **Prompt injection risk:** Never put untrusted user input directly in system prompts

---

## Further Reading

- [Anthropic Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
- [dair-ai Prompt Engineering Guide](https://github.com/dair-ai/Prompt-Engineering-Guide)
