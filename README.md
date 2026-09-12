# House Price Prediction

Predicting residential home sale prices from property characteristics, using the Ames Housing dataset.

## Problem Statement

<!-- 1-2 sentences: what are you predicting, and why does it matter? -->
Given features of a house (size, location, quality, age, etc.), predict its sale price. This kind of model is useful for buyers, sellers, and lenders trying to estimate fair market value.

## Data Source

- **Dataset:** Ames Housing dataset (via `sklearn.datasets.fetch_openml`, OpenML ID 42165)
- **Size:** 1,460 rows, 81 features
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

- Overall material/finish quality (`OverallQual`) and total square footage (`TotalSF`, an engineered feature) are by far the strongest predictors of sale price, together accounting for roughly a third of the model's decision-making.
- XGBoost outperformed both a linear baseline and a Random Forest, achieving an R² of 0.91 — it explains about 91% of the variation in sale prices.
- The best model's predictions are typically within about $26,300 of the true sale price (RMSE), and this held up in 5-fold cross-validation ($27,357 ± $4,972), so the result isn't just a lucky train/test split.
- Secondary factors — garage finish, kitchen/basement quality, and house age — matter but contribute far less than overall quality and size.

## Results Summary

| Model | RMSE | R² |
|---|---|---|
| Linear Regression | $29,741 | 0.885 |
| Random Forest | $29,342 | 0.888 |
| XGBoost | $26,343 | 0.910 |

*XGBoost 5-fold CV RMSE: $27,357 ± $4,972 — confirms the result is stable across folds, not just a favorable train/test split.*

<img width="790" height="590" alt="Unknown" src="https://github.com/user-attachments/assets/0b7f2fd9-67bb-4146-8ac1-500f1f47774d" />


## Limitations

- Dataset is specific to Ames, Iowa (2006–2010); may not generalize to other markets or time periods.
- With only 1,460 rows, some categorical values (e.g. rare garage or roof types) have very few examples, which limits how confidently the model can weigh them.
- The model was not tuned extensively (default/lightly-set hyperparameters for Random Forest and XGBoost); further tuning could likely close some of the remaining error.

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
