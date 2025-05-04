# Portfolio Part 4: Air Quality Analysis

## Overview
This project focuses on evaluating various classification models to predict air quality based on different features. Several machine learning algorithms, including Logistic Regression, Feature Selection, 1-Nearest Neighbour (1-NN), K-Nearest Neighbours (K-NN), and Decision Trees, were implemented and compared for their performance.

## Dataset

- **Source**: The dataset used for this project is obtained from Kaggle, specifically the "Air Quality Data Set" by Fedesoriano.
- **Description**: The dataset contains measurements of air quality, including concentrations of various pollutants, temperature, and humidity levels.

## Objectives

- Evaluate and compare the performance of different classification models.
- Optimise feature selection to improve model accuracy and effectiveness.
- Visualise model performance using metrics such as F1-Score, Accuracy, Precision, Recall, and Confusion Matrices.

## Features

The dataset includes the following features:

- `Date`: The date of the measurement.
- `Time`: The time of the measurement (hourly intervals).
- `CO(GT)`: Concentration of Carbon Monoxide in air (in mg/m³).
- `PT08.S1(CO)`: Sensor value for Carbon Monoxide.
- `NMHC(GT)`: Concentration of Non-Methane Hydrocarbons (in µg/m³).
- `C6H6(GT)`: Concentration of Benzene (in µg/m³).
- `PT08.S2(NMHC)`: Sensor value for Non-Methane Hydrocarbons.
- `NOx(GT)`: Concentration of Nitrogen Oxides (in µg/m³).
- `PT08.S3(NOx)`: Sensor value for Nitrogen Oxides.
- `NO2(GT)`: Concentration of Nitrogen Dioxide (in µg/m³).
- `PT08.S4(NO2)`: Sensor value for Nitrogen Dioxide.
- `PT08.S5(O3)`: Sensor value for Ozone.
- `T`: Temperature in degrees Celsius.
- `RH`: Relative Humidity (%).
- `AH`: Absolute Humidity.
- `AirQuality`: Target variable indicating air quality status (0 for poor, 1 for good).

## Methodology

The analysis is structured into several steps:

### 1. Data Exploration
- Identify the structure and distribution of the data.
- Combine `Date` and `Time` into a single datetime column for simplicity and future time series applications.
- Drop the original date and time columns after merging.

### 2. Classifying Air Quality
A custom function was defined to classify air quality:
- If `CO(GT)` ≤ 1.5 and `C6H6(GT)` ≤ 5.0 → classify as **Good (1)**
- Otherwise → classify as **Poor (0)**

### 3. Data Cleaning
- Handle missing values.
- Ensure the dataset is clean and ready for modeling.

### 4. Modeling and Feature Selection
Several models were implemented to compare performance:
- **Logistic Regression**
- **Feature Selection** using the following key features:
  - `CO(GT)`, `C6H6(GT)`, `PT08.S2(NMHC)`, `NOx(GT)`, `PT08.S3(NOx)`, `NO2(GT)`, `T`, `RH`, `AH`
- **1-NN (1-Nearest Neighbour)**
- **K-NN (K-Nearest Neighbours)**
- **Decision Tree**

### 5. Evaluation
- Assess model performance using:
  - Accuracy
  - F1-Score
  - Precision
  - Recall
  - Confusion Matrix
- Compare metrics across all models.

## Conclusion

The analysis demonstrated that both Logistic Regression and K-NN are effective models for air quality classification. Feature selection significantly improved model performance, highlighting the importance of selecting relevant variables. The findings offer valuable insights for public health and air quality management strategies.

## Future Work

- Explore advanced algorithms such as **Random Forest** or **Gradient Boosting** to enhance model robustness.
- Implement **Grid Search** or other hyperparameter tuning techniques for further optimisation.
- Develop a **real-time prediction system** using live air quality data streams.
- Incorporate **time-based features** (e.g., time of day, season) and external variables (e.g., weather conditions) to capture more complex environmental patterns.
