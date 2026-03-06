# Evidence of Workflow: Agentic Methodology + Project Progression

## Purpose
This document provides evidence of how the project was organized and progressed through stages using an agent-assisted workflow. It combines interaction logging and decision tracking in one place.

## Agentic Methodology Used
I used a **human-in-the-loop agentic workflow** with four repeated steps:

1. Plan a stage objective and ask the agent for draft implementation.
2. Run outputs in the local environment.
3. Verify correctness manually (data constraints, leakage, metrics, consistency).
4. Accept, modify, or reject the agent output with evidence.

This cycle was repeated across all project stages to ensure the final artifacts remained accurate, reproducible, and aligned with the brief.

## Stage-by-Stage Progress Evidence

### Stage 1: Problem framing and dataset selection
- Agent task: propose a classification dataset meeting the required original size range (50k-100k).
- Output: APSFailure (OpenML), original size 76,000 rows.
- Manual verification: checked dataset shape and source metadata.
- Decision: accepted APSFailure; rejected alternatives that were class-example-like or did not fit constraints.
- Artifacts: `output-revised/summary_aps_failure.txt`, `README.md` dataset link.

### Stage 2: EDA and risk identification
- Agent task: scaffold concise EDA and identify likely pitfalls.
- Output: class distribution and missingness analysis workflow.
- Manual verification: confirmed imbalance counts and added explicit missingness plot (top 20 features by missing percentage).
- Decision: accepted EDA direction, modified to include stronger missingness evidence.
- Artifacts: `output-revised/aps_failure_classification_rubric_aligned.ipynb` (EDA cells).

### Stage 3: Data preparation pipeline
- Agent task: propose reproducible preprocessing with split discipline.
- Output: numeric coercion, imputation/scaling pipeline, stratified split logic.
- Manual verification: ensured transformations were fit only on training data; checked shape and class-ratio preservation.
- Decision: accepted pipeline pattern, modified to use all 76,000 rows (no reduced sample in final notebook).
- Artifacts: notebook preparation section; `output-revised/summary_aps_failure_full76000.txt`.

### Stage 4: Model exploration and shortlist
- Agent task: build baseline and compare alternatives.
- Output: logistic baseline, decision tree, and random forest comparison blocks.
- Manual verification: confirmed same split and metric logic for fair comparison.
- Decision: accepted model comparison block, retained recall-first ranking policy.
- Artifacts: notebook sections `4` and `4B`.

### Stage 5: Fine-tune and evaluate
- Agent task: add tuning strategy and robust evaluation.
- Output: CV-based tuning (`RandomizedSearchCV`), confusion matrix, calibration, Brier score, failure-mode counts.
- Manual verification: checked objective-aligned scoring and interpreted recall/precision trade-off.
- Decision: accepted and integrated as required rubric section.
- Artifacts: notebook section `5`, report section `5`.

### Stage 6: Final presentation and packaging
- Agent task: align report structure to rubric and produce final deliverables.
- Output: revised report, PDF regeneration, appendix table, README/requirements updates.
- Manual verification: checked file consistency, word count target, and section mapping.
- Decision: accepted final package, removed superseded artifacts.
- Artifacts: `output-revised/aps_failure_report_revised.md`, `.pdf`, appendix files, `README.md`, `requirements.txt`.

## Consolidated Decision Register

| ID | Agent Contribution | Manual Verification | Decision | Final Outcome |
|---|---|---|---|---|
| D01 | Proposed APSFailure dataset | Verified shape and source (76,000 x 170) | Accepted | Used as final dataset |
| D02 | Proposed MNIST-family route earlier | Checked originality against class examples | Rejected | Removed from final workflow |
| D03 | Suggested accuracy-heavy framing in draft | Checked against imbalance objective | Modified | Reframed to recall-first + precision/macro-F1 |
| D04 | Suggested recall-priority metric set | Validated against failure-screening objective | Accepted | Used for ranking and interpretation |
| D05 | Suggested runtime subset in earlier phase | Re-checked final requirement consistency | Modified | Final notebook uses all 76,000 rows |
| D06 | Suggested numeric coercion (`errors='coerce'`) | Verified safe conversion to `NaN` | Accepted | Kept in data prep |
| D07 | Suggested median imputation in pipeline | Verified leakage-safe preprocessing order | Accepted | Kept in final pipeline |
| D08 | Suggested missingness visualization | Confirmed with computed percentages | Accepted | Added top-20 missingness plot |
| D09 | Suggested dropping high-missing columns | Tested vs all-feature baseline | Modified | Kept as comparative strategy |
| D10 | Suggested logistic baseline | Compared against tree/forest alternatives | Accepted | Retained as benchmark/final candidate |
| D11 | Suggested random forest comparison | Verified same-split metric comparability | Accepted | Included in model-family block |
| D12 | Suggested CV tuning | Verified with stratified CV + recall scoring | Accepted | Added as section 5 tuning step |
| D13 | Suggested robust evaluation add-ons | Verified confusion/calibration/Brier outputs | Accepted | Included in final notebook |
| D14 | Suggested explicit agent-mistake documentation | Checked brief requirement | Accepted | Added correction narrative |
| D15 | Suggested report restructuring | Verified one-to-one rubric mapping | Accepted | Final report aligned to rubric |
| D16 | Suggested README + requirements updates | Verified run instructions and artifact paths | Accepted | Reproducibility docs updated |

## Explicit Agent-Mistake Example (Required Evidence)
- Mistake detected: earlier narrative over-emphasized accuracy despite severe class imbalance.
- Why incorrect: accuracy can mask poor minority-class failure detection.
- Correction applied: switched to recall-first evaluation, required precision/macro-F1, and added confusion/failure-mode analysis.
- Evidence: notebook section `5` and report section `5`.

## Evidence Artifact Index
- Notebook: `output-revised/aps_failure_classification_rubric_aligned.ipynb`
- Report: `output-revised/aps_failure_report_revised.md` and `.pdf`
- Metrics summaries: `output-revised/summary_aps_failure.txt`, `output-revised/summary_aps_failure_full76000.txt`, `output-revised/test_metrics_aps_failure.csv`
- Appendix table files: `output-revised/appendix_agent_usage_log_decision_register.*`
- Project setup docs: `README.md`, `requirements.txt`

## Conclusion
This merged evidence log shows stage-by-stage project progression, concrete agent contributions, manual verification actions, and final acceptance decisions. It demonstrates that the project used agentic support in a controlled way, with the student retaining responsibility for validation and final technical judgement.
