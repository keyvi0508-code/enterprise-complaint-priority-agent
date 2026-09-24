# Priority classification

This is the taxonomy implemented in the supplied UiPath agent prompt.

## Low

Minor or informational issues that can normally be handled with a standard response:

- General Product Enquiry
- Size/Colour/Material Enquiry
- Washing/Care Instructions
- Normal Delivery Enquiry
- Discount/Promotion Question
- Simple Website/Navigation Issue

## Medium

Issues that affect an order or shopping experience and require employee follow-up without serious or urgent risk:

- Wrong Item Received
- Wrong Size Received
- Minor Product Defect
- Normal Return/Refund Request
- Missing Item
- Delayed Delivery
- Exchange Request

## High

Issues involving serious impact, significant financial loss, health or safety, fraud, repeated unresolved contact, legal or regulatory action, or serious reputational risk:

- Injury or Safety Issue
- Serious Health/Allergic Reaction
- Large-Value Financial Dispute
- Unauthorized Payment/Fraud Concern
- Repeated Unresolved Complaints
- Threat of Legal/Regulatory Action
- Serious Reputational Risk

## Decision rules

1. Use both the email subject and body.
2. Select the highest applicable priority when an email contains issues from multiple levels.
3. Within that priority, select the complaint type that best matches the most serious issue.
4. Do not add facts that the email does not state.
5. Emotional wording alone does not justify `High`.
6. Return the exact title-cased values defined above.

## Source discrepancy

The design-stage workbook in [`evidence/classification-design-dictionary.xlsx`](../evidence/classification-design-dictionary.xlsx) contains 18 snake-case categories. The current agent prompt contains 20 title-cased categories. Examples of the difference include:

- the workbook combines size mismatch and exchange as `size_exchange_request`, while the agent separates `Wrong Size Received` and `Exchange Request`;
- the workbook has `serious_product_quality_issue`, while the agent uses `Serious Health/Allergic Reaction` and a separate `Injury or Safety Issue`;
- `Serious Reputational Risk` appears in the agent prompt but not as a workbook row.

Because the workflow returns the agent's title-cased labels, the prompt taxonomy is treated as the current implementation. The workbook is retained as design evidence, not as the runtime schema. The supplied files do not include a dated change log that explains when or why these labels changed.
