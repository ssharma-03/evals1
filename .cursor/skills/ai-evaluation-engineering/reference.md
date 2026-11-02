# Specialized Evaluation Modules

## Model evaluation

Evaluate task correctness, instruction following, output quality, consistency, robustness, and relevant safety properties. Select metrics appropriate to the task; do not apply one universal quality score.

## Prompt evaluation

Preserve prompt versions. Evaluate adherence, format, task success, edge cases, ambiguity, robustness, and regressions against the same cases. Do not infer improvement from length or confidence alone.

## RAG evaluation

Evaluate retrieval and generation separately.

Retrieval metrics can include recall@k, precision@k, MRR, nDCG, and relevant-document coverage. Generation metrics can include correctness, evidence-grounded faithfulness, relevance, citation correctness, and appropriate abstention.

Distinguish missing retrieval evidence from generation failures and do not apply metrics unsupported by references.

## Agent evaluation

Evaluate task completion, final-answer correctness, tool selection, tool arguments, execution success, action ordering, state transitions, recovery, retries, termination, authorization boundaries, side effects, trace completeness, latency, and cost.

A correct final answer does not prove intermediate actions were appropriate. Capture trace evidence and distinguish target failures from unavailable tools or external services.

## Safety and security evaluation

Use an explicit threat model and controlled environment. Measure observed violations against expected secure behavior. Separate false refusals from correct refusals and unauthorized-tool attempts from actual authorization violations.

Do not use attack-count-only rates unless attack coverage, denominator, and success criteria are explicit.

## Performance and cost evaluation

Measure the deployment dimensions that affect the decision:

- Latency distributions
- Throughput
- Timeout and error rates
- Resource consumption
- Token usage
- Cost per request
- Cost per completed task
- Cost per successful task

Define boundaries and units. Distinguish model latency from end-to-end application latency. Report sample sizes and percentiles when appropriate. Document configuration and workload differences before comparing systems or costs.

## Judge validation

When using an LLM judge, treat it as a component requiring validation. Define observable rubric criteria and explicit score meanings; require supporting evidence for material judgments.

Assess:

- Agreement with human judgments on a representative sample
- Repeatability
- Position and presentation bias
- Sensitivity to irrelevant wording
- Ambiguous-case handling
- False-positive and false-negative patterns
- Judge prompt and model version effects

Use deterministic validation for output schema and required fields. Do not treat persuasive explanations as proof of judge reliability.

## Regression evaluation

Preserve cases and results for future comparison. Compare baseline and candidate under equivalent conditions. Detect regressions in correctness, task completion, safety, latency, cost, format, and behavioral categories.

Report which cases improved, regressed, or remained unchanged. Use predefined tolerances when available. If tolerances do not exist, report observed changes without treating them as predefined acceptance rules.

## Metric and scoring rules

Do not collapse all dimensions into one aggregate score by default. Report mandatory criteria and diagnostic metrics separately.

If an aggregate is required:

1. Define component metrics.
2. Document normalization and weights.
3. Justify intended interpretation.
4. Preserve critical-failure rules separately.
5. Test sensitivity to reasonable weighting alternatives.

For comparisons, report absolute values, absolute differences, and relevant changes against baseline. Use confidence intervals or suitable uncertainty estimates when the design supports them. Do not claim significance without appropriate analysis, and do not confuse statistical significance with practical importance.
