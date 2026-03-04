# Workflow Log

## Purpose
Chronological log of what was done with agent assistance and what was manually verified.

## Entry Template
- Date/Time:
- Step:
- Agent action requested:
- Output produced:
- Manual verification performed:
- Evidence artifact(s):
- Notes:

## Entries

### Entry 1
- Date/Time: [fill]
- Step: Dataset selection
- Agent action requested: Find classification dataset with original size 50k-100k.
- Output produced: APSFailure selected (OpenML), original size 76,000.
- Manual verification performed: Confirmed row count and target labels from load output.
- Evidence artifact(s): `output-revised/summary_aps_failure.txt`, dataset link in README.
- Notes: Replaced classroom-style dataset with APSFailure for originality.

### Entry 2
- Date/Time: [fill]
- Step: Notebook scaffolding
- Agent action requested: Generate rubric-aligned notebook pipeline.
- Output produced: `output-revised/aps_failure_classification_revised.ipynb`.
- Manual verification performed: Checked target encoding, split discipline, and pipeline order.
- Evidence artifact(s): notebook cells, `output-revised/test_metrics_aps_failure.csv`.
- Notes: Confirmed recall-focused evaluation was included.

### Entry 3
- Date/Time: [fill]
- Step: Report drafting and revision
- Agent action requested: Create report, then align wording/structure to rubric.
- Output produced: `output-revised/aps_failure_report_revised.md` + PDF.
- Manual verification performed: Checked metric consistency and rubric section mapping.
- Evidence artifact(s): report files, metrics CSV, summary files.
- Notes: Converted style to continuous prose per requirement.

### Entry 4
- Date/Time: [fill]
- Step: Artifact cleanup
- Agent action requested: Remove superseded non-APS outputs.
- Output produced: `output-revised` now contains only APS-related deliverables.
- Manual verification performed: Reviewed file listing after cleanup.
- Evidence artifact(s): terminal listing snapshot.
- Notes: Keeps audit trail focused and clear.
