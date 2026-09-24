# Source audit

Reviewed on 2026-09-24.

| Supplied item | What it establishes | Portfolio treatment |
|---|---|---|
| `Customer Complaint Management part2.uis` | One UiPath AI agent, one Google Sheets classification process, dependencies, and one evaluation case | Core project source extracted; connection and user-specific metadata removed or redacted |
| `JSON.xlsx` | Variable dictionary and an 18-category design-stage priority dictionary | Preserved as design evidence; not presented as run results |
| `优先级+分类.pdf` | Rationale, examples, escalation rule, and a broader proposed team flow | Used to cross-check the taxonomy; original PDF omitted because publication rights were not established |
| Eleven email DOCX files | Nine demo inputs and two test inputs | Transcribed with names removed; no saved model outputs were present |
| `Introduction_ReAct_Learner.ipynb` | A separate, incomplete venue-planning ReAct exercise | Excluded because it is unrelated to complaint classification |

## Confirmed implementation

- Google Sheets row iteration over `Pending_Agent`.
- Agent invocation with `case_id`, `email_subject`, and `email_body`.
- Structured string outputs for `priority_level` and `complaint_type`.
- Append of the three output fields to `Priority_Table`.
- Prompt-based three-level taxonomy and escalation logic.
- One UiPath evaluation case with an expected label.

## Not confirmed or not present

- mailbox ingestion;
- automatic reply generation or sending;
- employee/manager routing after classification;
- deployed solution status;
- aggregate evaluation scores;
- saved outputs for the 11 provided email fixtures;
- documented misclassifications or a dated prompt-adjustment log;
- individual authorship of workflow components beyond the contribution statement supplied for this portfolio.

## Sensitive material handling

The public copy excludes the raw `.uis` archive, connector resource, `userProfile`, and local UiPath settings. A personal email address, workspace name, spreadsheet URL, Integration Service connection ID, cloud path, and deployment project IDs were removed or replaced. No API key or password value was found in the reviewed files.
