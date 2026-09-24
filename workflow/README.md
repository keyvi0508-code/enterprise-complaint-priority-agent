# UiPath workflow source

This directory preserves the two supplied UiPath source project trees:

- `Customer Complaint Priority Agent`: agent schema, prompt, model configuration, and UiPath evaluator definitions.
- `02_Complaint_Classification`: the orchestration process and pinned dependencies.

## Public-copy changes

The original source was not overwritten. In this review copy:

- `.local` and `userProfile` data were excluded;
- the connector resource containing a personal account name was excluded;
- Google Sheets URL, connection ID, workspace path, and deployment project IDs were replaced;
- one sample customer name in the evaluation fixture was replaced with `Sample Customer`;
- the packaged `.uis` and `.uipx` artifacts were excluded because they retained deployment-specific metadata.

These changes make the project safe to review but require the Google Sheets activities and deployment references to be rebound in UiPath Studio before execution.

No application logic, prompt rule, dependency version, activity order, range name, or data-field mapping was intentionally changed.
