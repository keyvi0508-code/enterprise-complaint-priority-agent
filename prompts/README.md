# Prompt evidence

These files are extracted from the current UiPath agent configuration:

- [`system-prompt.md`](system-prompt.md) contains the taxonomy, escalation rule, and output constraints.
- [`user-prompt.md`](user-prompt.md) maps the three workflow inputs into the model request.

The prompt is also preserved inside [`agent.json`](../workflow/Customer%20Complaint%20Priority%20Agent/agent.json), which is the runtime source of truth. These Markdown copies improve reviewability and should be kept synchronized with that file.
