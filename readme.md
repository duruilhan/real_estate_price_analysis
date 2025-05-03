# DSA210 Project Proposal - Real Estate Price Analysis

## Motivation

The real estate sector is a vital part of the economy and is significantly influenced by factors such as economic trends, social behavior, and government regulations. In recent years, significant fluctuations in real estate prices have been observed, particularly influenced by macroeconomic changes and urban development trends. Analyzing the factors affecting these price changes and predicting future prices can offer valuable insights for investors, policymakers, and real estate professionals.

This project aims to explore the key determinants of housing prices and develop predictive models to forecast future prices.

---

## Data Source

The dataset used in this project is a **real-world dataset** collected from [Emlakjet](https://www.emlakjet.com/), a major real estate platform in Turkey. The data was originally compiled and shared on [Kaggle](https://www.kaggle.com/datasets/egeakyol/real-estate-in-istanbul-turkey-emlakjet), and contains detailed information about listings in Istanbul.

The dataset includes the following features:

- Location (city, district, neighborhood)
- Number of Rooms
- Area (square meters)
- Building Age
- Price
- Floor Information
- Number of Bathrooms

It does not contain any personal or sensitive data and complies with data privacy standards.

---

## Method and Plan

### Data Collection and Preparation
- Load and explore the real dataset to understand its structure.
- Clean the data: handle missing values, unify formats, drop or impute inconsistencies.
- Create additional features (e.g., numerical room count, grouped building age).

### Exploratory Data Analysis (EDA)
- Generate descriptive statistics and visualize key features of the data.
- Identify trends and patterns that may influence housing prices.
- Investigate correlations between variables to identify significant predictors.

### Hypothesis Testing
- Perform statistical tests to validate assumptions, including:
  - Is there a correlation between number of rooms and price?
  - Are newer buildings more expensive?
  - Does floor level affect price?

### Modeling Approach (Future Steps)
- Apply machine learning models such as:
  - Linear Regression
  - Random Forest
  - XGBoost
- Evaluate model performance using:
  - Mean Absolute Error (MAE)
  - Root Mean Squared Error (RMSE)
- Use hyperparameter tuning and cross-validation for optimization.

---

## Ethical Considerations

- The dataset is publicly available and contains no personal identifiers.
- The project adheres to ethical AI practices and responsible data use.
- All tools and models used will be transparently documented.

---

## Potential Challenges and Mitigations

| Challenge            | Mitigation                                                  |
|----------------------|-------------------------------------------------------------|
| Data Quality Issues  | Apply data cleaning and imputation where necessary          |
| Model Bias           | Use validation, avoid overfitting, test on diverse samples  |
| Interpretability     | Include interpretable models and visualizations             |

---

This project is expected to offer valuable insights into Istanbul’s real estate market and provide a strong foundation for predictive analytics in housing price estimation.

## Insights from EDA and Hypothesis Testing

## Exploratory Data Analysis (EDA)
- The distribution of real estate prices is highly right-skewed, indicating that most listings are concentrated at lower price ranges while a few extremely high-priced listings stretch the tail. To improve interpretability, a log transformation was applied.
- A positive correlation was observed between the size of the property (in square meters) and its price. Larger properties tend to have higher prices.
- Listings with more rooms generally exhibit higher average prices. In particular, 3+1 and 4+1 apartments are priced significantly higher than 1+1 or 2+1 units.
- Newer buildings (0–5 years old) are associated with noticeably higher prices compared to older properties. This trend suggests that buyers are willing to pay a premium for new construction.
- The number of bathrooms also shows a mild association with price, with homes featuring more bathrooms tending to be more expensive.
- However, floor level did not exhibit a clear visual pattern or correlation with price.

## Hypothesis Testing Results
- Number of Rooms vs. Price:
- - Pearson correlation test showed a statistically significant positive relationship (p < 0.05). As the number of rooms increases, so does the price.

- Building Age vs. Price:
- - ANOVA test results indicate that building age has a significant effect on housing prices (p < 0.05). There are meaningful differences in average prices across different building age groups.

- Floor Level vs. Price:
- - ANOVA test showed no statistically significant effect (p ≈ 0.85), suggesting that floor level does not significantly influence housing prices in this dataset.

## Summary
These findings help identify key factors influencing real estate prices in Istanbul. While features like size, number of rooms, building age, and bathrooms significantly affect price, floor level appears to have minimal impact. These insights can serve as a foundation for further predictive modeling and price estimation in real estate markets.
