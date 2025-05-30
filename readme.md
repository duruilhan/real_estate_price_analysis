# DSA210 Final Project – Real Estate Price Analysis

## Motivation

The real estate market in Istanbul has become increasingly dynamic, driven by macroeconomic shifts, urbanization, and infrastructure development. Predicting housing prices is essential for home buyers, investors, and urban planners. This project aims to explore which factors most influence housing prices in Istanbul and build a solid foundation for future predictive modeling.

---

## Data Source

We used a publicly available dataset scraped from [Emlakjet](https://www.emlakjet.com/), a major Turkish real estate listing site. The dataset contains structured listings for properties in Istanbul, including:

- Location: city, district, neighborhood
- Structural details: number of rooms, area (sqm), number of bathrooms, floor level
- Metadata: price, building age

There are no personally identifiable data, and the dataset complies with data privacy standards.

---

## Tools & Libraries

- Python 3
- pandas, numpy
- matplotlib, seaborn
- scipy.stats

---

## Methodology

### 1. Data Cleaning & Feature Engineering
- Removed missing and inconsistent entries
- Extracted numerical values from text-based fields (e.g., `room_numeric`)
- Created new variables:
  - `price_per_sqm` = price / area
  - `log_price`, `log_area` (log-transformed variables)
  - One-hot encoded `district` values
- Cleaned and grouped floor-level and building age categories

### 2. Exploratory Data Analysis (EDA)
- Visualized distributions (price, area, room count, bathrooms)
- Identified outliers and skewness
- Compared average price across categorical variables
- Examined correlation matrix for numeric features

### 3. Hypothesis Testing
We tested several real-world hypotheses using statistical methods:

#### 🟠 Hypothesis 1 – District vs Price per sqm
- **Test**: One-way ANOVA
- **Hypothesis**: The average price per sqm is equal across selected districts.
- **Result**: Not significant (p = 0.5743) → No strong evidence of difference.

#### 🔵 Hypothesis 2 – Number of Bathrooms vs Price
- **Test**: Welch’s t-test
- **Hypothesis**: Homes with 1 vs 2 bathrooms have the same average price.
- **Result**: Significant (p < 0.0001) → Homes with 2 bathrooms are more expensive.

#### 🟣 Hypothesis 3 – Floor Level vs Price
- **Test**: Mann-Whitney U Test (non-parametric)
- **Hypothesis**: Ground floor homes and upper floor homes have the same price.
- **Result**: Significant (p < 0.0001) → Ground floor prices differ significantly.

#### 🟢 Hypothesis 4 – Building Age vs Price
- **Test**: One-way ANOVA on grouped age ranges
- **Hypothesis**: New and old buildings have the same average price.
- **Result**: Significant → Newer buildings tend to be more expensive.

#### 🟡 Hypothesis 5 – Number of Rooms vs Price
- **Test**: Pearson correlation
- **Hypothesis**: There is a linear correlation between room count and price.
- **Result**: Moderate positive correlation → More rooms tend to mean higher prices.

---

## Key Takeaways

- Housing price in Istanbul is positively associated with:
  - Total area
  - Number of bathrooms
  - Number of rooms
  - Being on an upper floor
  - Newer building age
- District alone does not significantly explain price per sqm variation.
- These factors are suitable inputs for regression models in future prediction tasks.

---

## Next Steps (Modeling Plan)

- Use `price` as the target variable
- Use numerical and encoded features (`area_sqm`, `room_numeric`, `bathrooms`, encoded `district`, etc.) as predictors
- Try Linear Regression, Decision Trees, and XGBoost
- Evaluate using RMSE and R²