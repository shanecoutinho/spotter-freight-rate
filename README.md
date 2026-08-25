# Spotter Freight Rate Prediction

Machine learning solution developed for the Spotter.AI Machine Learning Engineer assessment.

## Overview

This project develops a machine learning model to predict freight load rates using historical labelled freight data.

The project covers the complete machine learning workflow:

- Exploratory data analysis
- Data quality assessment
- Data preprocessing
- Feature engineering
- Model development
- Time-based validation
- Model comparison
- Final model training
- Validation predictions
- December forecasting
- Model evaluation and reporting

## Dataset

The development dataset contains historical freight loads with information including:

- Pickup and delivery locations
- Pickup and delivery coordinates
- Distance
- Equipment type
- Weight
- Date
- Market index
- Quote signal
- Posted freight rate

The target variable is:

`posted_rate`

The supplied validation dataset contains future loads for which predictions must be generated.

## Project Structure

```text
spotter-freight-rate/
├── data/
├── notebooks/
├── src/
├── outputs/
├── reports/
├── score.py
├── requirements.txt
├── .gitignore
└── README.md