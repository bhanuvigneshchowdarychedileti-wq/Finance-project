# Currency Exchange Rate Forecasting Using Machine Learning

This project explores **currency exchange-rate forecasting using machine learning**, with a focus on USD/INR and cross-currency exchange rates.

The project uses historical monthly exchange-rate data, performs market-based feature engineering, applies multiple forecasting models, compares their performance, and uses **SHAP explainability** to understand which features contribute most to the model predictions.

## Project Structure

The project contains two Jupyter notebooks:

### 1. USD/INR Forecasting

**Notebook:** `USDINR_Faculty_Demo(2).ipynb`

This notebook focuses specifically on forecasting the **USD/INR exchange rate** using historical monthly data.

**Data:**

* Source: FRED EXINUS
* Frequency: Monthly
* Period: January 2015 – August 2026
* Currency: INR per USD

### Methodology

The notebook follows these steps:

1. **Historical Data Preparation**

   * Loads monthly USD/INR exchange-rate data.
   * Organizes the data into a time-series format.

2. **Feature Engineering**

   The following market-based features are generated:

   * 1-month return
   * 3-month momentum
   * 6-month momentum
   * 3-month volatility
   * 6-month volatility
   * 12-month trend
   * 6-month moving-average gap
   * 12-month drawdown

3. **Forecasting Models**

   Four approaches are compared:

   * Random Walk benchmark
   * Ridge Regression
   * Elastic Net
   * XGBoost

4. **Out-of-Sample Evaluation**

   An expanding-window out-of-sample testing approach is used to reduce look-ahead bias.

   Models are evaluated using:

   * RMSE
   * MAE
   * Directional Accuracy

5. **Forecast Horizons**

   The project evaluates:

   * 3-month forward returns
   * 6-month forward returns

6. **SHAP Explainability**

   SHAP is used to identify the relative contribution of the engineered market features to the XGBoost predictions.

7. **Final Forecast**

   The notebook also generates model-based 3-month and 6-month USD/INR forecasts using the available observations through August 2026.

---

### 2. Four-Currency Cross-Rate Forecasting

**Notebook:** `Four_Currency_CrossRate_Faculty_Demo (3)(1).ipynb`

This notebook extends the forecasting framework to **cross-currency rates involving EUR, CHF, JPY and KRW**.

The analysis specifically focuses on cross-currency market movements and does **not use USD or INR** in this notebook.

### Methodology

1. **Cross-Rate Analysis**

   The notebook examines six cross-currency pairs involving:

   * EUR
   * CHF
   * JPY
   * KRW

   The rates are indexed to 100 at their first observation so that currencies with different numerical scales can be compared visually.

2. **Feature Engineering**

   For each cross-rate, the following features are calculated:

   * 1-month return
   * 3-month momentum
   * 6-month momentum
   * 3-month volatility
   * 6-month volatility
   * 12-month trend
   * Moving-average gap
   * 12-month drawdown

3. **Forecasting Models**

   The following models are evaluated:

   * Random Walk
   * Ridge Regression
   * Elastic Net
   * XGBoost

4. **Forecast Horizons**

   Forecasting is performed for:

   * 3-month returns
   * 6-month returns

5. **Model Evaluation**

   Model performance is compared using:

   * RMSE
   * MAE
   * R²
   * Directional Accuracy

   A chronological 80/20 train-test split is used.

6. **XGBoost Analysis**

   Actual future returns are compared with XGBoost predictions for both forecasting horizons.

7. **SHAP Explainability**

   SHAP feature importance is calculated to identify which engineered market features contribute most strongly to XGBoost predictions.

   SHAP values are used for **model interpretation and do not establish causality**.

---

## Technologies Used

* Python
* Jupyter Notebook
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* XGBoost
* SHAP

## Evaluation Metrics

| Metric               | Purpose                                                                 |
| -------------------- | ----------------------------------------------------------------------- |
| RMSE                 | Measures the magnitude of prediction errors                             |
| MAE                  | Measures average absolute prediction error                              |
| R²                   | Measures explained variance                                             |
| Directional Accuracy | Measures how often the predicted direction matches the actual direction |
| SHAP Importance      | Helps interpret feature contributions to model predictions              |

## Project Workflow

```text
Historical Exchange-Rate Data
            ↓
      Data Preparation
            ↓
      Feature Engineering
            ↓
   ┌────────┼──────────┐
   ↓        ↓          ↓
 Ridge   Elastic Net  XGBoost
   └────────┼──────────┘
            ↓
     Model Evaluation
            ↓
     Forecast Analysis
            ↓
     SHAP Explainability
            ↓
      Final Insights
```

## Key Objectives

* Study historical currency-market movements.
* Engineer meaningful time-series market features.
* Compare traditional regression models with XGBoost.
* Evaluate short- and medium-term forecasting performance.
* Use out-of-sample testing to evaluate model performance.
* Improve model transparency using SHAP explainability.

## Important Notes

* The project is intended for **academic and analytical purposes**.
* Forecasts are model outputs and should not be interpreted as guaranteed future exchange rates.
* SHAP measures model contribution and does not establish causal relationships.
* The USD/INR notebook uses monthly USD/INR data from January 2015 to August 2026.
* The cross-rate notebook separately analyzes EUR, CHF, JPY and KRW cross-rates and does not use USD or INR.

## Files

```text
Currency-Forecasting/
│
├── USDINR_Faculty_Demo(2).ipynb
├── Four_Currency_CrossRate_Faculty_Demo (3)(1).ipynb
└── README.md
```

## Author

**Bhanu Vignesh**

Computer Science and Engineering (Data Science)
Vellore Institute of Technology (VIT)
