# AI Usage Declaration

## Purpose

DineIQ Analytics was developed with AI-assisted tools used for research,
debugging, code suggestions, documentation drafting, and interface review.
This declaration is retained because the supplied SRS requires it.

## Team Responsibility

The project team is responsible for reviewing, understanding, testing, and
approving every committed change. AI assistance did not supply a runtime
decision service: forecasts, classifications, recommendations, and analytical
results are produced by the repository's Spark-compatible and Python
pipelines.

## Reviewed Areas

| Area | Repository modules |
|---|---|
| Data generation and cleaning | `data_generator/`, `python_pipeline/cleaning/` |
| Processing and analytics | `python_pipeline/processing/`, `python_pipeline/analytics/` |
| Spark-compatible pipeline | `spark_jobs/`, `spark_sql/` |
| Model scoring | `models/`, `src/services/scoring_service.py` |
| Web application | `src/`, `templates/`, `static/` |
| Tests and documentation | `tests/`, `documentation/`, `README.md` |

## Verification

The team should rerun the required checks before delivery:

```powershell
python -m pytest tests -q
python python_pipeline/run_pipeline.py --skip-generation
python -m spark_jobs.run_all --engine auto
```

Generated outputs and performance evidence must be interpreted against the
dataset and execution environment recorded in the repository documentation.
