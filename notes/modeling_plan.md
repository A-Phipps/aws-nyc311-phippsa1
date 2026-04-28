# NYC 311 Modeling Plan

**Date created:** April 28, 2026

## Business question
Predict high-volume complaint agencies by borough

## Data source
- **S3 path:** s3://phippsa1-nyc311-data/processed/modeling_data/
- **Records:** [number from df.shape[0]]
- **Athena query:** sql/athena_to_modeling.sql

## Features
- borough (string): The geographic location of the complaint.
- complaint_type (string): Specifically filtering for "Noise" categories.
- hour_of_day (numeric): Extracted from the created date to find peak times.
- day_of_week (numeric): To identify weekend vs. weekday patterns.
- latitude/longitude (numeric): For spatial density analysis.

## Target
- **Name:** is_high_volume
- **Type:** 1 = High volume / Cluster, 0 = Standard volume
- **Balance/Distribution:** 15% High Volume, 85% Standard Volume (Imbalanced)

## Modeling approach
- **Baseline:** Logistic regression (interpretable, fast to train)
- **Metrics:** Accuracy, precision, recall
- **Train/test split:** 80/20

## Data quality notes
- [Any missing values, outliers, or issues to watch for]

## Next steps 
- Train/test split
- Fit baseline logistic regression
- Evaluate and interpret results
