# Istanbul Real Estate Price Analysis

This project analyzes a dataset of housing listings from Istanbul, collected from the Emlakjet real estate platform. It includes data cleaning, exploratory data analysis (EDA), statistical hypothesis testing, and predictive modeling using linear regression.

## Project Structure

- `Real Estate in ISTANBUL.csv`: Raw dataset collected from Emlakjet
- `eda.ipynb`: Data cleaning, visualization, feature engineering, and linear regression model
- `hypothesis_tests.ipynb`: Statistical hypothesis tests (t-tests, ANOVA, Mann-Whitney U)
- `requirements.txt`: Python dependencies
- `readme.md`: Project documentation

## Objective

The main goals of this project are:
- To understand the relationship between housing features (such as area, number of rooms, location) and prices
- To test hypotheses about price differences across groups
- To build a model that predicts prices using selected features

## Data Preprocessing

The raw dataset was cleaned and transformed:
- Removed missing and invalid values
- Standardized column names
- Converted text-based numeric fields (e.g., room counts)
- Cleaned building age entries and grouped them
- Created new variables:
  - `room_numeric`: number of rooms as numeric
  - `price_per_sqm`: price divided by area
  - `log_price`: log-transformed price

## Exploratory Data Analysis

The following were included in the EDA:
- Descriptive statistics
- Distribution of price and area
- Correlation heatmap of numeric variables
- Bar plots by number of rooms, number of bathrooms, and districts
- Boxplots and scatter plots for visualizing price patterns

## Hypothesis Testing

Five hypothesis tests were conducted:

1. Two-sample t-test: price difference between houses with 1 vs 2 bathrooms  
2. ANOVA: price differences between districts  
3. Mann-Whitney U Test: price differences between ground floor and upper floors  
4. Two-sample t-test: price difference between small and large houses based on median area  
5. One-sample t-test: whether the average log price differs from log(1,000,000 TL)

### Test Results

| Test | Description | p-value | Decision |
|------|-------------|---------|----------|
| Two-sample t-test | Price: 1 vs 2 bathrooms | 0.007 | Reject H₀ |
| ANOVA | Price ~ district | < 0.001 | Reject H₀ |
| Mann-Whitney U | Ground floor vs others | 0.004 | Reject H₀ |
| Two-sample t-test | Small vs large area | 0.013 | Reject H₀ |
| One-sample t-test | log(price) vs log(1M TL) | 0.000 | Reject H₀ |

All tests were statistically significant at the 0.05 level, indicating meaningful differences across housing characteristics.

## Predictive Modeling

A linear regression model was built to predict housing prices.

Features:
- `area_sqm`
- `room_numeric`
- `number_of_bathrooms`
- One-hot encoded `district` variables

Target:
- `price`

The model was trained on 80% of the data and tested on the remaining 20%.

Results:
- Root Mean Squared Error (RMSE): approximately 485,546 TL
- R² Score: 0.3157

The model provides a baseline and can be improved with additional features.

## Requirements

To run the project, install the following Python libraries:

```
pandas
numpy
matplotlib
seaborn
scikit-learn
scipy
```

Install them using:

```bash
pip install -r requirements.txt
```

## Notes

This project was completed as part of the DSA 210: Introduction to Data Science course. Some parts of the documentation were generated with the help of ChatGPT, with final review and implementation completed by the student.