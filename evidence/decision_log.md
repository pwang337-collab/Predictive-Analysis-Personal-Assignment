# Decision Log

## Purpose
Record key modelling and workflow decisions, rationale, alternatives considered, and verification status.

## Decision Template
- Decision ID:
- Date:
- Decision:
- Options considered:
- Chosen option:
- Rationale:
- Risks/Trade-offs:
- Verification evidence:
- Status:

## Decisions

### D-01 Dataset choice
- Date: [fill]
- Decision: Select dataset with original size in 50k-100k range.
- Options considered: Covertype (too large original), Fashion-MNIST (class example overlap), APSFailure.
- Chosen option: APSFailure (OpenML, 76,000 rows).
- Rationale: Meets size constraint directly and is domain-relevant for predictive maintenance.
- Risks/Trade-offs: Strong class imbalance complicates evaluation.
- Verification evidence: dataset shape output and OpenML reference.
- Status: Final.

### D-02 Primary metric selection
- Date: [fill]
- Decision: Prioritize positive-class recall over raw accuracy.
- Options considered: Accuracy-first, macro-F1-first, recall-first with supporting precision/F1.
- Chosen option: Recall-first with precision and macro F1 as companion metrics.
- Rationale: Missing failures is costlier than false alarms in screening context.
- Risks/Trade-offs: Higher recall can reduce precision and increase false positives.
- Verification evidence: `test_metrics_aps_failure.csv`, confusion matrix in notebook.
- Status: Final.

### D-03 Preprocessing strategy
- Date: [fill]
- Decision: Use pipeline with median imputation + scaling.
- Options considered: row deletion, mean imputation, external preprocessing scripts.
- Chosen option: median imputation + scaling in sklearn pipeline.
- Rationale: Robust handling of missing values and leakage-safe transform discipline.
- Risks/Trade-offs: Median imputation may underuse feature interactions.
- Verification evidence: notebook pipeline cell and reproducible outputs.
- Status: Final.

### D-04 Model selection
- Date: [fill]
- Decision: Keep balanced logistic regression as final reproducible model.
- Options considered: tree ensembles, logistic baseline.
- Chosen option: class-balanced logistic regression pipeline.
- Rationale: Strong recall, interpretability, and reliable runtime in environment.
- Risks/Trade-offs: Potentially lower precision and lower nonlinearity capture vs ensembles.
- Verification evidence: test metrics and report interpretation.
- Status: Final.

### D-05 Agent mistake correction
- Date: [fill]
- Decision: Correct accuracy-heavy narrative.
- Options considered: keep draft, revise evaluation framing.
- Chosen option: revise to recall/precision/macro-F1 framing.
- Rationale: Accuracy alone is misleading for imbalanced failure detection.
- Risks/Trade-offs: More nuanced narrative required in report.
- Verification evidence: revised report Section 5 and metrics table.
- Status: Final.
