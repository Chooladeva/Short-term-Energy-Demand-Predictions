# Regional Short-Term Energy Demand Prediction System

A comprehensive machine learning framework for analysing weather-driven regional energy demand patterns and building high-performance predictive models.

This project integrates cloud-based analytics, statistical feature engineering, and ensemble machine learning techniques to forecast short-term energy consumption across multiple regions with high accuracy and robustness.

# Project Objectives
- Perform in-depth descriptive analysis of weather and seasonal drivers of energy demand
- Engineer statistically relevant predictive features
- Train and compare advanced ensemble machine learning models
- Evaluate regional model performance with granular metrics
- Optimise the best-performing model using systematic hyperparameter tuning
- Improve forecasting accuracy using stacked ensemble learning

## Descriptive Analysis

### Overview

The descriptive analysis phase involved a detailed assessment of:
- Weather variables
- Temporal features
- Seasonal patterns
- Regional energy demand behaviour

All analytics were conducted using AWS SageMaker Notebooks, enabling scalable, cloud-based data processing and experimentation.

### Tools & Libraries Used

| Tool          | Purpose                              |
| ------------- | ------------------------------------ |
| AWS SageMaker | Cloud notebook environment           |
| Pandas        | Data manipulation                    |
| NumPy         | Numerical computation                |
| Matplotlib    | Data visualization                   |
| Seaborn       | Statistical visualization            |
| Joypy         | Joy (ridge) plots                    |
| SciPy         | Statistical testing                  |
| Scikit-learn  | Mutual Information feature selection |

### Key Analysis Activities
- Regional demand distribution analysis
- Seasonal consumption pattern detection
- Weather-energy correlation exploration
- Statistical relationship validation using SciPy
- Feature importance extraction via Mutual Information Regression

Joy plots were used to visualise regional distribution shifts across seasons, allowing intuitive comparison of demand density patterns.

## Predictive Modeling Framework

Energy consumption forecasting was performed region-wise, ensuring each region had a dedicated trained model.

### Machine Learning Algorithms Evaluated

The following models were trained and compared:
- Extra Trees Regressor
- Gradient Boosting Regressor
- XGBoost Regressor
- LightGBM Regressor
- CatBoost Regressor
- AdaBoost Regressor
- Stacked Ensemble Meta Model

Each algorithm was independently trained and evaluated per region.

### Model Training Workflow

For every algorithm:

1. Training
- Input and output data separated by region
- Models trained region-wise
- Stored in dictionaries indexed by region

2️. Prediction
- Predictions generated on region-specific test data
- Stored in structured dictionaries

3️. Evaluation

Predictions were evaluated using:
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- R-Squared (R²)
- Adjusted R-Squared

The evaluation process ensures:
- Regional granularity
- Robust handling of mismatched prediction lengths
- Fair comparison across models

### Model Performance Comparison

Model comparison is critical for determining real-world forecasting suitability.

Key Observations:
- Tree-based ensemble models significantly outperformed traditional boosting methods
- Region-specific training improved generalization
- Ensemble approaches reduced variance across regions
- LightGBM achieved the best trade-off between speed and predictive accuracy

### Stacked Ensemble Modeling

To further enhance prediction accuracy:
- Base Models:
  - XGBoost
  - LightGBM

- Meta-Model:
  - Random Forest Regressor

The stacked ensemble combines predictions from the two gradient boosting models, allowing the meta-model to learn residual correction patterns.

This technique improved:

- Stability across regions
- Generalization on unseen data
- Overall predictive consistency

### Hyperparameter Tuning

Hyperparameter tuning was conducted to optimise model performance and avoid overfitting.

**Best Performing Model: LightGBM Regressor**

Based on model comparison results, LightGBM demonstrated:
- Lowest RMSE
- Highest R²
- Strong generalization
- Fast training time

Grid search / parameter optimisation strategies were applied to tune:
- Number of estimators
- Learning rate
- Maximum depth
- Feature fraction

Regularization parameters

This tuning significantly improved validation performance.

## Evaluation Strategy

Models were evaluated region-wise using structured test datasets.

The evaluation ensured:
- Predictions aligned with actual sample sizes
- Metrics were computed safely under mismatch scenarios
- Fair algorithm comparison across geographic segments

This approach provides a granular understanding of forecasting behaviour across different energy consumption zones.

## Technology Stack
- Python
- AWS SageMaker
- Pandas / NumPy
- SciPy
- Scikit-learn
- XGBoost
- LightGBM
- CatBoost
- Matplotlib / Seaborn / Joypy

## Conclusion

This project delivers a complete, production-ready regional short-term energy demand forecasting system built on:
- Strong exploratory analytics
- Statistically validated feature selection
- Advanced ensemble machine learning
- Rigorous region-level evaluation
- Systematic hyperparameter optimization

It demonstrates end-to-end capability in data science, cloud analytics, and predictive modeling for energy systems.
