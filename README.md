# Advanced-ML_Capstone_project
### Predicting Menstrual Cycle Length Using Machine Learning

##  Project Overview

Menstrual cycle length varies between individuals and between cycles. Understanding the factors associated with this variation can help researchers investigate patterns within menstrual-cycle data.

This project uses **machine learning regression techniques** to investigate whether demographic, reproductive, menstrual, and other available characteristics can be used to predict **menstrual cycle length**.



> **Project Type: Regression**

The project focuses on prediction and statistical association. The results should not be interpreted as evidence that any individual feature causes changes in menstrual-cycle length.

---

#  Project Objective

### Main Objective

To develop and evaluate machine-learning regression models for predicting menstrual cycle length using demographic, reproductive, menstrual, and related characteristics.

### Specific Objectives

* Understand and prepare the menstrual-cycle dataset for machine learning.
* Perform exploratory data analysis to identify patterns and relationships.
* Identify and handle missing values and potential outliers.
* Engineer meaningful features for regression modelling.
* Develop a suitable preprocessing pipeline.
* Investigate dimensionality-reduction techniques.
* Develop and compare  regression models.
* Perform cross-validation to obtain robust model-performance estimates.
* Optimize model hyperparameters.
* Evaluate model performance using appropriate regression metrics.
* Perform residual and error analysis.
* Interpret the contribution of important predictive features.
* Identify the limitations and potential generalizability of the model.

---

## Research Questions

1. Can machine-learning regression models predict menstrual cycle length from available demographic, reproductive, and menstrual characteristics?
2. Which features provide the most useful predictive information for cycle length?
3. How do linear and nonlinear regression models perform on the prediction task?
4. Does dimensionality reduction improve regression performance?
5. Does hyperparameter tuning improve the performance of the selected models?
6. What patterns can be identified from the models' prediction errors?
7. Which model provides the most reliable predictions based on the selected evaluation metrics?

---
### Dataset
The primary dataset being investigated is the mcPHASES dataset, a longitudinal menstrual-health dataset containing multiple sources of information collected from participants.

The dataset contains information relating to:

Menstrual events
Hormonal measurements
Sleep
Stress
Mood
Menstrual symptoms
Physical activity
Heart rate
Heart-rate variability
Skin temperature
Respiratory rate
Other physiological measurements

The dataset contains multiple interconnected tables, allowing the project to investigate relationships between menstrual characteristics and physiological or behavioral measurements.

Dataset source: PhysioNet — mcPHASES



#  Concepts used

The project will incorporate the following Advanced ML concepts:

### Feature Engineering

Development of meaningful features from the available menstrual-cycle variables.

### Data Preprocessing Pipelines

A unified preprocessing pipeline will be developed to handle:

* Missing values
* Numerical features
* Categorical features
* Encoding
* Feature scaling

### Dimensionality Reduction

The project will investigate:

* Principal Component Analysis (PCA)
* Isomap
* UMAP, where appropriate

The purpose is to determine whether lower-dimensional representations can preserve useful information while reducing feature complexity.

### Cross-Validation

Cross-validation will be used to obtain more reliable estimates of model performance rather than relying solely on one train/test split.

### Hyperparameter Optimization

The selected models will undergo hyperparameter tuning using techniques such as:

* Grid Search
* Randomized Search

### Model Interpretation

Feature importance and model coefficients will be examined to understand which variables contribute to predictions.

### Error Analysis

Residuals and prediction errors will be analyzed to identify systematic patterns and weaknesses in the models.

---

#  Regression Models

To keep the modelling process focused and meaningful, **three regression models** will be evaluated.

## 1. Linear Regression

Linear Regression will serve as the baseline model.

It will provide a simple reference point against which more complex models can be compared.

## 2. Ridge Regression

Ridge Regression will be used to investigate whether regularization improves performance when predictors are correlated or when feature engineering creates a larger feature space.

## 3. Random Forest Regression

Random Forest Regression will be used as a nonlinear ensemble model capable of capturing complex relationships and interactions between features.

The models will be compared using the same validation strategy and evaluation metrics.

---

## Model Evaluation

The regression models will be evaluated using:

### Mean Absolute Error (MAE)

Measures the average absolute difference between actual and predicted cycle length.

### Mean Squared Error (MSE)

Penalizes larger prediction errors more heavily.

### Root Mean Squared Error (RMSE)

Provides an error measure in the same units as cycle length.

### R² Score

Measures the proportion of variance in the target that is explained by the model.

Model performance will not be determined using a single metric alone. Multiple metrics will be considered together.

---

#  Residual Analysis

Residual analysis will be performed to investigate whether the models produce systematic errors.

The analysis will include:

* Residual plots
* Residual distribution
* Residuals against predicted values
* Identification of potential outliers
* Investigation of under-prediction and over-prediction

A key objective will be to determine whether the residuals show patterns that suggest the model is missing important relationships within the data.

---

#  Feature Importance and Interpretation

After model development, the project will investigate which features contribute most strongly to cycle-length predictions.

Depending on the final models, interpretation techniques may include:

* Linear model coefficients
* Ridge coefficients
* Random Forest feature importance
* Permutation importance

The interpretation will be used to identify **predictive associations**, not to establish causal relationships.

---



##  Technologies

The project will primarily use:

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* SciPy
* Jupyter Notebook
* UMAP, where applicable

---

## Expected Outcomes

The project aims to:

* Develop regression models capable of predicting menstrual cycle length.
* Determine which available features provide useful predictive information.
* Compare linear, regularized, and nonlinear ensemble regression approaches.
* Determine whether dimensionality reduction improves model performance.
* Evaluate the effect of hyperparameter tuning.
* Analyze prediction errors through residual analysis.
* Interpret important predictive features.
* Identify limitations affecting model reliability and generalization.

---

##  Limitations

Potential limitations include:

* Limited number of unique participants/users.
* Potentially synthetic or simulated aspects of the dataset.
* Self-reported variables may contain reporting inaccuracies.
* Missing values may affect model performance.
* Some features may contain information closely related to the target and therefore require careful consideration for data leakage.
* Relationships identified by the models represent predictive associations and should not be interpreted as causal effects.
* Results from this dataset may not generalize to all populations.

---





---

