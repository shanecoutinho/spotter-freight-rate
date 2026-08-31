# Spotter Freight Rate Prediction

Final machine-learning solution for the Spotter.AI Machine Learning Engineer assessment.

## Approach

- Cleaned invalid/missing values without target leakage.
- Converted dates into calendar and cyclic seasonal features.
- Created route features.
- Used a chronological validation split: January-August 2025 for training and September-October 2025 for holdout evaluation.
- Used CatBoost regression for nonlinear freight-rate relationships and categorical variables.
- Retrained the final validation model on all January-October labelled data.
- Generated predictions for all 12,000 validation loads.
- Used a separate schema-compatible December model because the supplied December chart input contains only:
  `pickup, delivery, distance, equipment, weight, date, predicted_rate`.
- Ran the provided scorer successfully.

## Run

From the project root:

```bash
python -m pip install -r requirements.txt
jupyter notebook notebooks/01_spotter_freight_rate_final.ipynb
```

Run all cells from top to bottom.

The notebook creates:

- `validation_predictions.csv`
- completed `data/december-chart-inputs.csv`
- `scorer_results/candidate_december.png`

The supplied scorer can also be run manually:

```bash
python score.py   --predictions validation_predictions.csv   --december-predictions data/december-chart-inputs.csv
```

## Important

Do not add `rate_per_mile` or any other feature derived from `posted_rate`; that would leak the target.

The assessment requires the repository, `validation_predictions.csv`, a PDF/DOCX report containing the validation/split approach and December chart, and a 2–3 minute Loom walkthrough.
