# MSIN0097 Predictive Analytics Coursework

This repository contains my individual coursework project using the APS Failure dataset.

## Final Deliverables
- Notebook: `output-revised/aps_failure_classification_rubric_aligned.ipynb`
- Report (Markdown): `output-revised/aps_failure_report_revised.md`
- Report (PDF): `output-revised/aps_failure_report_revised.pdf`

## Dataset
- Name: APS Failure at Scania Trucks (`APSFailure`)
- Source: OpenML
- Original size: 76,000 rows, 170 features
- Task: binary classification (`pos` vs `neg`)

Dataset link:
- https://www.openml.org/search?type=data&sort=runs&id=41138

## Environment
- Python 3.10+
- See `requirements.txt` for packages

## Setup
```bash
cd "/Users/godwpx/Desktop/Predictive Analysis/Personal Assignment"
python3 -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
python -m ipykernel install --user --name aps-coursework --display-name "Python (aps-coursework)"
```

## Run
```bash
cd "/Users/godwpx/Desktop/Predictive Analysis/Personal Assignment"
source .venv/bin/activate
jupyter lab
```

Open and run:
- `output-revised/aps_failure_classification_rubric_aligned.ipynb`

## Evidence Files
- `evidence/workflow_log.md`
- `evidence/decision_log.md`

## Notes
- The notebook includes missingness-based feature dropping (`>70%`), model family comparison, CV-based tuning, and robust evaluation.
****
