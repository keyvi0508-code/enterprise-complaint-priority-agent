# Evaluation evidence

## What is historically supported

The supplied UiPath source contains one evaluation item at [`evaluation-set-default.json`](../workflow/Customer%20Complaint%20Priority%20Agent/evals/eval-sets/evaluation-set-default.json):

- input: a wool-sweater washing question;
- expected output: `Low / Washing/Care Instructions`;
- source marker: `firstSuccessfulRun`;
- saved actual output: not present;
- saved score or evaluator justification: not present.

The project also defines a semantic-similarity LLM evaluator that can score expected versus actual JSON from 0 to 100. Its configuration exists, but no evaluator result is stored in the supplied package.

## Provided email fixtures

The 11 DOCX files contain nine demo inputs and two test inputs. They do not contain expected labels, actual model outputs, scores, or run timestamps.

For portfolio review:

- [`provided-email-fixtures.jsonl`](provided-email-fixtures.jsonl) transcribes the supplied inputs and removes personal sign-off names;
- [`proposed-annotations.csv`](proposed-annotations.csv) applies the current prompt taxonomy as a review annotation created on 2026-09-24;
- every proposed annotation is marked **not executed** and must not be read as a historical model result.

One case is deliberately documented as ambiguous: `Test_Email_2` satisfies both `Repeated Unresolved Complaints` and `Threat of Legal/Regulatory Action`. The proposed primary label selects the explicit regulatory threat, but the prompt does not define a tie-break rule between two labels at the same priority level.

## What the evidence does not support

- no aggregate accuracy or pass rate;
- no category-level coverage result;
- no recorded false positives or false negatives;
- no dated misclassification log;
- no before/after prompt comparison;
- no runtime, latency, cost, or throughput measurement.

## Recommended next evaluation run

1. Freeze a balanced labeled set that covers all 20 current labels, multi-issue escalation, emotional language without high-risk facts, and same-priority ambiguity.
2. Record the agent configuration, prompt hash, model, and run date.
3. Save raw structured outputs before scoring.
4. Score exact `priority_level`, exact `complaint_type`, schema validity, and case ID preservation separately.
5. Review disagreements manually and preserve an error log before changing the prompt.

This plan is unexecuted. It is included to show how the current evidence gap can be closed without inventing results.
