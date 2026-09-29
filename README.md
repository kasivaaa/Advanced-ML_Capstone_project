
---

# Advanced ML Capstone Project

## Predicting Menstrual Cycle Length Using Machine Learning and LSTM

### Project Overview

This project investigates whether **machine learning and time-series techniques** can be used to predict menstrual cycle length using demographic, reproductive, menstrual, and physiological data.

The project uses the **mcPHASES dataset from PhysioNet**, which contains longitudinal menstrual-health and physiological information.

**Project Type:** Regression & Time-Series Prediction

### Objectives

* Clean and explore the menstrual-health dataset.
* Perform feature engineering and data preprocessing.
* Identify features associated with menstrual cycle length.
* Develop and compare regression models.
* Investigate temporal patterns in menstrual-cycle data.
* Develop an **LSTM neural network** for sequential prediction.
* Apply dimensionality reduction and hyperparameter tuning.
* Evaluate model performance and analyze prediction errors.

### Dataset

The primary dataset being investigated is the mcPHASES dataset, a longitudinal menstrual-health dataset containing multiple sources of information collected from participants.

The dataset contains information relating to:

Menstrual events Hormonal measurements Sleep Stress Mood Menstrual symptoms Physical activity Heart rate Heart-rate variability Skin temperature Respiratory rate Other physiological measurements

The dataset contains multiple interconnected tables, allowing the project to investigate relationships between menstrual characteristics and physiological or behavioral measurements.

Dataset source: PhysioNet — mcPHASES

### Models & Techniques

**Regression Models**

* Linear Regression
* Ridge Regression
* Random Forest Regression

**Advanced ML**

* PCA
* Isomap
* UMAP
* Feature Engineering
* Hyperparameter Optimization
* Isolation Forest

**Time-Series & Deep Learning**

* Lag Features
* Rolling Statistics
* Time-Based Validation
* **LSTM (Long Short-Term Memory)**

### Model Evaluation

Models will be evaluated using:

* MAE
* MSE
* RMSE
* R² Score

Residual analysis and error analysis will also be performed to understand model performance.

### Expected Outcome

The project aims to determine whether machine learning and **LSTM-based time-series modelling** can effectively predict menstrual cycle length and whether historical cycle information improves prediction.

### Technologies

Python • Pandas • NumPy • Scikit-learn • TensorFlow/Keras • Matplotlib • Seaborn • SciPy • UMAP • Jupyter Notebook

### Limitations

Results will depend on data quality, sample size, missing observations, and the availability of sufficient longitudinal data. Model findings represent **predictive associations and not causal relationships or medical diagnoses**.


