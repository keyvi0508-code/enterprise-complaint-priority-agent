# User prompt template

Extracted verbatim from the supplied UiPath `agent.json`. Line endings were normalized for Markdown; wording was not edited.

```text
Analyse the following customer email and classify it according to the priority and complaint type rules.

Case ID:
{{input.case_id}}

Email Subject:
{{input.email_subject}}


Email Body:
{{input.email_body}}

Return the classification using the defined output schema.
```
