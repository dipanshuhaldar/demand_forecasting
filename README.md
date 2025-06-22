# Demand Forecasting

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

Approached to real life Demand Forecasting scenarios, with varying volume lined with seasonalities and anomalies due to events and activities in the product lifecycle.

## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         demand_forecasting and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── demand_forecasting   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes demand_forecasting a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

## ⏳ Time Series Forecasting Approach

This repository applies time series forecasting to model and predict demand, with real-world considerations like:

- 📈 **Seasonality and Trends:** Weekly/monthly cycles, upward/downward long-term movements.
- 🎯 **Anomalies and Events:** Spikes due to marketing campaigns, outages, product releases, etc.
- 🔧 **Preprocessing:** 
  - Time indexing and resampling.
  - Holiday/event feature engineering.
  - Lag features, rolling stats, and Fourier terms.

## 🔍 Models Explored

| Model                  | Highlights                                       |
|------------------------|--------------------------------------------------|
| `ARIMA`               | Classical baseline for trend + seasonality       |
| `Prophet`             | Handles holidays and multiple seasonalities      |
| `XGBoost / LightGBM`  | Tree-based regressors on lag features            |
| `LSTM`                | Deep learning model for sequential patterns      |
| `Ensembles`           | Weighted average or stacking across models       |

## 📊 Evaluation Metrics

- **MAE (Mean Absolute Error)**
- **RMSE (Root Mean Squared Error)**
- **MAPE (Mean Absolute Percentage Error)**

## 📁 Example Notebooks

- `notebooks/1.0-ed-data-overview.ipynb`: Data structure and EDA.
- `notebooks/2.0-ts-trend-seasonality.ipynb`: Decomposition and visualization.
- `notebooks/3.0-arima-prophet-models.ipynb`: Baseline statistical models.
- `notebooks/4.0-xgb-lstm.ipynb`: ML and DL-based forecasting.

## 🧠 Forecasting Tips

> Good forecasts are interpretable, robust to anomalies, and regularly retrained with new data.

## ✅ Run Forecasting Pipeline

```bash
make data       # Fetch and preprocess data
make features   # Generate time series features
make train      # Train the forecasting models
make predict    # Run prediction on future periods
```

---

Happy Forecasting! 🎯📈
