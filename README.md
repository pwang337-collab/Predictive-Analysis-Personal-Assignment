# APS Failure Predictive Analytics Coursework

This repository contains my MSIN0097 predictive analytics individual coursework project.

## Project Summary
The project builds a binary classification model to predict APS system failure (`pos`) vs non-failure (`neg`) using the OpenML APSFailure dataset.

## Dataset
- Name: APS Failure at Scania Trucks (`APSFailure`)
- Source: OpenML
- Original size: 76,000 rows, 170 features
- Task type: Binary classification

## Objective
Develop a reproducible predictive pipeline with evaluation focused on imbalanced-class performance, especially positive-class recall for failure detection.

## Repository Structure
- `output-revised/`: final notebook, report, and metrics artifacts
- `evidence/`: workflow and decision audit trail for agent-assisted work

## Final Deliverables
- Notebook: `output-revised/aps_failure_classification_revised.ipynb`
- Report (PDF): `output-revised/aps_failure_report_revised.pdf`
- Report (Markdown): `output-revised/aps_failure_report_revised.md`
- Metrics: `output-revised/test_metrics_aps_failure.csv`

## Workflow Evidence
- `evidence/workflow_log.md`
- `evidence/decision_log.md`

## Reproducibility Notes
- Random seed: 42
- Preprocessing includes numeric coercion, median imputation, and scaling
- Model: class-balanced logistic regression pipeline

## Dataset Link
- https://www.openml.org/search?type=data&sort=runs&id=41138
