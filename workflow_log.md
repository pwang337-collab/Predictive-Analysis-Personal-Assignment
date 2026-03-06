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
- Agent task: propose a classification dataset meeting a reasonable size range (50k-100k).
- Output: APSFailure (OpenML), original size 76,000 rows.
- Manual verification: checked dataset shape and source metadata.
- Decision: accepted APSFailure; rejected alternatives that were class-example-like or did not seem appropriate (insufficient data).
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
