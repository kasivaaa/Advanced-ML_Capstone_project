
---

# Advanced ML Capstone Project

## Predicting Menstrual Cycle Length Using Time-Series and Machine Learning Models

### Project Overview

Menstrual cycle length varies both between individuals and across successive cycles. Traditional menstrual tracking often relies on historical averages or calendar-based estimates, which may not capture individual cycle variability.

This project investigates whether **historical menstrual-cycle patterns, hormonal measurements, physiological signals, and self-reported characteristics** can be used to predict the length of a subsequent menstrual cycle.

The project uses the **mcPHASES dataset from PhysioNet**, a longitudinal multimodal dataset containing menstrual, hormonal, physiological, and self-reported data from 42 young adult participants. Participants were monitored during an initial three-month period, with 20 participants completing a second three-month period.

**Project Type:** Regression & Time-Series Forecasting

---

## Problem Statement

Menstrual cycle length is not constant for every individual or from one cycle to another. Factors such as previous cycle patterns, hormonal changes, physiological measurements, sleep, activity, stress, and other menstrual characteristics may provide useful information for predicting future cycle length.

However, the temporal nature of these variables means that observations cannot always be treated as independent records.

This project therefore investigates whether **time-series models and machine-learning techniques can learn temporal patterns and improve prediction of subsequent menstrual cycle length.**

---

## Prediction Target

The target variable is:

> **Menstrual Cycle Length — measured in days**

The target will be derived from consecutive menstrual events where sufficient information is available.

The prediction task will be structured so that information available **before the target cycle** is used to predict its cycle length.

This is important for preventing **data leakage**.

---

## Dataset and Time Frame

The mcPHASES dataset contains 23 structured tables linked primarily through participant ID and `day_in_study`. It combines daily self-reported information with high-frequency wearable, hormonal, and metabolic measurements.

### Study periods

* **Interval 1:** approximately 3 months in 2022
* **Interval 2:** approximately 3 months in 2024
* **42 participants** contributed to the released dataset.
* **20 participants** completed the second interval.

The exact usable modelling period will be established after inspecting the downloaded data and determining the available observations for each participant.

---

## Project Objectives

* Understand and clean the longitudinal dataset.
* Derive menstrual cycle length as the prediction target.
* Identify the available temporal range and observation frequency.
* Perform exploratory time-series analysis.
* Engineer lagged and rolling features.
* Develop classical time-series forecasting models.
* Develop traditional machine-learning regression models.
* Develop an LSTM neural network for sequential prediction.
* Investigate dimensionality-reduction techniques.
* Tune model hyperparameters.
* Compare model performance using consistent evaluation metrics.
* Perform residual and error analysis.
* Interpret important predictive features.
* Assess limitations and generalizability.

---

# Models and Advanced ML Concepts

## 1. Classical Time-Series Models

Because the project is fundamentally a forecasting problem, several classical time-series approaches will be investigated.

### ARIMA

**ARIMA (AutoRegressive Integrated Moving Average)** will provide a classical statistical forecasting baseline.

It will allow us to model relationships between previous cycle-length observations and future values.

### SARIMA

**SARIMA (Seasonal ARIMA)** will be investigated if exploratory analysis identifies meaningful seasonal or repeating patterns.

Because menstrual cycles do not necessarily follow a fixed seasonal period, SARIMA will only be retained if the data provides evidence that a seasonal component is appropriate.

### Other Time-Series Approaches

Depending on the structure and number of observations available, additional approaches may include:

* Exponential Smoothing
* Auto-ARIMA
* Moving-average forecasting
* Naive/seasonal-naive baseline

These models will provide increasingly sophisticated forecasting baselines against which machine-learning and LSTM models can be compared.

---

# 2. Machine-Learning Regression

Three regression models will provide a machine-learning comparison:

### Linear Regression

Baseline model for estimating relationships between engineered predictors and cycle length.

### Ridge Regression

Regularized regression model designed to handle correlated predictors and higher-dimensional feature spaces.

### Random Forest Regression

Nonlinear ensemble model capable of modelling interactions and nonlinear relationships.

---

# 3. LSTM Neural Network

The main deep-learning model will be an:

> **LSTM — Long Short-Term Memory Neural Network**

LSTM is appropriate because menstrual-cycle data is longitudinal.

The model will receive sequences of historical observations and attempt to predict the subsequent cycle length.

For example:

```text
Cycle 1 → Cycle 2 → Cycle 3 → Cycle 4
                         ↓
                       LSTM
                         ↓
              Predicted Cycle 5
```

The LSTM will be compared against the classical time-series and machine-learning models.

---

# 4. Dimensionality Reduction

The mcPHASES dataset contains many physiological and wearable measurements. Dimensionality reduction will therefore be investigated to determine whether a smaller representation of the data can preserve useful predictive information.

### PCA

**Principal Component Analysis (PCA)** will be used to:

* Reduce highly correlated features.
* Compress the feature space.
* Visualize major patterns.
* Investigate whether fewer components can maintain predictive information.

### Isomap

**Isomap** will be investigated as a nonlinear dimensionality-reduction technique.

It will be used to determine whether the physiological and behavioral data contain nonlinear structures that conventional PCA may not capture.

### UMAP

**UMAP** will be used primarily for nonlinear exploratory visualization and potentially feature-space analysis.

The objective is not to assume that dimensionality reduction will improve the model, but to experimentally determine whether it provides useful representations.

---

# 5. Feature Engineering

Temporal features will be particularly important.

Potential features include:

* Previous cycle length
* Previous two or three cycle lengths
* Rolling mean cycle length
* Rolling standard deviation
* Cycle-to-cycle change
* Historical symptoms
* Previous hormone measurements
* Sleep measures
* Activity measures
* Heart-rate measures
* Temperature measures
* Stress-related variables

Features will only use information that would have been available **before the prediction point**.

---

# 6. Time-Series Validation

Random train/test splitting can lead to leakage in temporal data.

Therefore, the project will use time-aware validation techniques such as:

* Chronological train/test split
* TimeSeriesSplit
* Walk-forward validation
* Expanding-window validation where appropriate

The models will therefore be evaluated under a realistic forecasting scenario:

> **Past → Training → Future → Prediction**

rather than randomly mixing past and future observations.

---

# 7. Model Evaluation

Models will be compared using:

* **MAE** — Mean Absolute Error
* **MSE** — Mean Squared Error
* **RMSE** — Root Mean Squared Error
* **R²** — coefficient of determination

For forecasting models, we will also examine performance across different participants and prediction periods where the data allows.

---

# 8. Model Comparison

The main comparison will be:

| Category              | Model                      |
| --------------------- | -------------------------- |
| Baseline              | Naive / historical average |
| Classical Time Series | ARIMA                      |
| Classical Time Series | SARIMA                     |
| Classical Time Series | Exponential Smoothing      |
| Machine Learning      | Linear Regression          |
| Machine Learning      | Ridge Regression           |
| Machine Learning      | Random Forest              |
| Deep Learning         | **LSTM**                   |

The goal is to determine how different modelling approaches handle the temporal structure of menstrual-cycle data.

The project will **not assume beforehand that LSTM will perform best**. Performance will be determined experimentally using the same appropriate evaluation framework.

---

# 9. Residual and Error Analysis

After model evaluation, prediction errors will be investigated through:

* Residual plots
* Actual vs predicted cycle length
* Error distributions
* Under-prediction and over-prediction
* Errors across participants
* Errors across shorter and longer cycles
* Temporal patterns in prediction errors

This will help identify where the models perform well and where they struggle.

---

# Expected Outcome

The project aims to determine:

1. Whether menstrual cycle length can be predicted using available historical and physiological information.
2. Whether classical time-series models can provide useful forecasting baselines.
3. Whether machine-learning regression improves prediction.
4. Whether LSTM can capture useful temporal relationships.
5. Whether dimensionality reduction provides useful representations of the high-dimensional physiological data.
6. Which modelling approach provides the most useful predictive performance under the selected evaluation framework.

---

## Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Statsmodels
* TensorFlow / Keras
* SciPy
* UMAP
* Jupyter Notebook

---

## Limitations

The dataset contains a relatively small number of participants, and individual participants have different amounts of longitudinal data. Missing observations and irregular sampling may also affect modelling.

The second study interval is separated from the first by a substantial period, so it should not automatically be treated as one continuous uninterrupted time series.

The results represent **predictive associations rather than causal relationships** and should not be interpreted as medical diagnoses.

