# Assignment 8 — Submission Pack

**Name:** Tanmay Shinde  
**Subject:** MLOps PBA2  
**Enrollment No.:** ADT23SOCB1617  
**Class:** LY-SMAD  
**Title:** Automated Re-Training Pipeline Triggered by Data Drift  
**Domain:** Demand Forecasting  

## Submission PDF (upload this)

`submission/ADT23SOCB1617_TanmayShinde_MLOps_PBA2_Submission.pdf`

## GitHub repository

https://github.com/tanmays0/ADT23SOCB1617-drift-retraining-pipeline

## Live / local check links

| What | URL / path |
|------|------------|
| GitHub | https://github.com/tanmays0/ADT23SOCB1617-drift-retraining-pipeline |
| MLflow Models UI | http://127.0.0.1:5000/#/models |
| Evidently drift report | http://127.0.0.1:8765/drift_report.html |
| Alert file | `outputs/alerts/alert_*.txt` |

## How to reproduce

```bash
uv venv --python 3.12 .venv
source .venv/bin/activate
uv pip install -r requirements.txt
python scripts/run_demo.py
```

## Screenshot index

| File | Evidence |
|------|----------|
| `screenshots/05_github_repo.png` | GitHub repository page |
| `screenshots/04_prefect_flow_success.png` | Prefect flow completed (drift → retrain → alert) |
| `screenshots/02_evidently_drift_report.png` | Evidently AI drift report (Wasserstein / dataset drift detected) |
| `screenshots/01_mlflow_model_registry.png` | MLflow Model Registry — `demand-forecast-model` v1 `@champion` |
| `screenshots/03_email_alert.png` | Email alert notification (local file channel) |
| `screenshots/alert_20261022T083002Z.txt` | Raw email alert text |
| `screenshots/run_summary.json` | Machine-readable run summary |

## Key run results

- **Drifted:** `true`
- **Max Wasserstein:** `8.7455` (threshold `0.1`)
- **Model:** `demand-forecast-model` version `1`
- **Metrics:** MAE ≈ `3.52`, R² ≈ `0.95`
