# House-Price-Prediction

Predicting residential home sale prices from property characteristics, using the Ames Housing dataset.

## Problem Statement

<!-- 1-2 sentences: what are you predicting, and why does it matter? -->
Given features of a house (size, location, quality, age, etc.), predict its sale price. This kind of model is useful for buyers, sellers, and lenders trying to estimate fair market value.

## Data Source

- **Dataset:** Ames Housing dataset (via `sklearn.datasets.fetch_openml`, OpenML ID 42165)
- **Size:** ~2,900 rows, ~80 features
- **Target variable:** `SalePrice`

> Swap this section out if you end up scraping your own listings — note the source, collection date, and any known biases (e.g. "only listings from Zillow in [city], collected [date]").

## Approach

1. Exploratory data analysis — distributions, correlations, outliers
2. Missing value handling and feature engineering
3. Baseline model: Linear Regression
4. Comparison models: Random Forest, XGBoost
5. Model evaluation via cross-validated RMSE and R²
6. Feature importance / SHAP analysis to interpret what drives price

## Key Findings

<!-- Fill in after you run the notebook. Write this for a non-technical reader. -->
- *(e.g. "Overall quality rating and above-ground living area were the two strongest predictors of price.")*
- *(e.g. "The best model (XGBoost) achieved an RMSE of $X, meaning predictions are typically within $X of the true sale price.")*
- *(e.g. "The model underperforms on luxury homes above $500K due to few examples in that price range.")*

## Results Summary

| Model | RMSE | R² |
|---|---|---|
| Linear Regression | — | — |
| Random Forest | — | — |
| XGBoost | — | — |

## Limitations

<!-- Be honest here — this signals maturity to reviewers -->
- Dataset is specific to Ames, Iowa (2006–2010); may not generalize to other markets or time periods.
- *(add your own findings, e.g. sparse data for certain property types)*

## How to Run

```bash
git clone https://github.com/<your-username>/house-price-prediction.git
cd house-price-prediction
pip install -r requirements.txt
jupyter notebook notebooks/house_price_prediction.ipynb
```

Or open directly in Google Colab: *(paste your Colab share link here)*

## Project Structure

```
house-price-prediction/
├── README.md
├── requirements.txt
├── notebooks/
│   └── house_price_prediction.ipynb
├── src/                  # optional: reusable functions
└── images/               # charts referenced in this README
```
