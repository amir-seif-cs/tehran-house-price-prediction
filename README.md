# Tehran House Price Prediction

A machine learning regression project for predicting residential property prices in Tehran using property characteristics and location information.

## Project Overview

This project uses a real-world dataset of Tehran residential properties to predict house prices in USD.

The main features include:

* Area
* Number of rooms
* Parking
* Warehouse
* Elevator
* Address

Several regression models were trained and evaluated to identify the best-performing model.

## Dataset

The dataset was provided as part of the following Maktabkhooneh course:

[Machine Learning with Python — Maktabkhooneh](https://maktabkhooneh.org/course/%DB%8C%D8%A7%D8%AF%DA%AF%DB%8C%D8%B1%DB%8C-%D9%85%D8%A7%D8%B4%DB%8C%D9%86-%D9%BE%D8%A7%DB%8C%D8%AA%D9%88%D9%86-mk1318/)

The original dataset source was identified as Kaggle:

[House Price (Tehran, Iran)](https://www.kaggle.com/datasets/mokar2001/house-price-tehran-iran)

The course version of the dataset intentionally contained missing and invalid values for data cleaning and preprocessing practice.

The dataset contains approximately 3,500 residential property records collected from Tehran.

During data preprocessing:

* Invalid area values were removed.
* Missing addresses were removed.
* Unrealistically large area values were removed.
* Boolean features were converted to numerical values.
* The `Address` feature was encoded using median target-based ranking calculated only from the training data.

## Models

The following regression models were evaluated:

* Linear Regression
* Ridge Regression
* Decision Tree
* Random Forest
* Gradient Boosting
* XGBoost

## Results

XGBoost achieved the best overall performance on the test set.

| Model             | MAE (USD) | RMSE (USD) |    R² |
| ----------------- | --------: | ---------: | ----: |
| XGBoost           |    36,048 |     85,978 | 0.854 |
| Random Forest     |    36,852 |     90,770 | 0.837 |
| Gradient Boosting |    39,723 |     92,851 | 0.829 |
| Ridge Regression  |    66,482 |    125,558 | 0.688 |
| Linear Regression |    66,488 |    125,565 | 0.688 |
| Decision Tree     |    45,811 |    128,405 | 0.673 |

## Feature Importance

According to the XGBoost model, the most important features were:

1. Area — 55.3%
2. Address — 30.7%
3. Room — 6.4%
4. Elevator — 4.5%
5. Parking — 2.2%
6. Warehouse — 0.9%

Area and location were the two most influential features in the model.

## Prediction Analysis

The actual vs. predicted price analysis showed that most predictions were reasonably close to the ideal prediction line.

Residual analysis showed that prediction errors generally increased for higher-priced properties, while lower-priced properties tended to have smaller errors.

## Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* XGBoost
* Jupyter Notebook

## Project Structure

```text
tehran-house-price-prediction/
│
├── housePrice.csv
├── house_price_prediction.ipynb
├── .gitignore
└── README.md
```

## Author

Amirhossein Seifizadeh

GitHub: [amir-seif-cs](https://github.com/amir-seif-cs)
