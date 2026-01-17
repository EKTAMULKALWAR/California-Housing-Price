# California-Housing-Price
Linear Regression • Ridge • Lasso • Assumption-Driven Modeling

This project predicts median house prices for California neighborhoods using a Linear Regression pipeline built from scratch and improved with regularization.

The dataset is the well-known California Housing Prices dataset from Kaggle, derived from the 1990 California census.
Each row represents a census block group, and the target variable is the median house value for that neighborhood.

📌 Dataset Overview
<img width="1280" height="248" alt="Screenshot 2026-01-16 at 5 33 29 PM" src="https://github.com/user-attachments/assets/0cfc12db-0562-4f97-9c26-fa1beccbeceb" />

The dataset contains features that describe:

- Location → longitude, latitude

- Income level → median_income

- Housing density & size → total_rooms, households, population

- Neighborhood type → ocean_proximity

- Target → median_house_value

Although this dataset does not reflect current housing prices, it is widely used for learning and demonstrating Regression Modeling and ML Fundamentals.

# 🧠 Workflow

- Loaded and explored the dataset
- Built a simple linear regression from scratch
- Applied log transformation on the target
- Engineered better features
- Built multiple linear regression
- Improved the model using Ridge and Lasso



# 📐 Linear Regression Assumptions

To apply Linear Regression properly, we ensured the five core assumptions were reasonably satisfied:

1) Linearity
The relationship between median_income and house price was strongly linear.
Scatter plots confirmed this.

2) Independence of Errors
Each data row represents a different neighborhood → errors are independent.

3) Homoscedasticity
Residual plots revealed increasing variance at higher price levels.
To fix this, we transformed the target:

y = \log(1 + \text{median_house_value})

4) Normality of Errors
Log-transformation produced a more symmetric error distribution.

5) No Multicollinearity
Raw features like total_rooms, total_bedrooms, households, and population were highly correlated.
So we engineered:

1) rooms_per_household

2) bedrooms_per_household

3) population_per_household

These features capture the same information in a more stable and interpretable way.

# 🏗️ Final Features Used
Feature	Why it matters
- median_income	Strongest economic predictor of housing value
- latitude, longitude	Captures geographic pricing patterns
- ocean_proximity (encoded)	Reflects regional housing demand
- rooms_per_household	Measures home size & density
- population_per_household	Measures neighborhood crowding

# ⚙️ Model Training

We implemented:

- Simple Linear Regression (from scratch)
to understand weight, bias, gradient descent, and cost minimization.

 - Multiple Linear Regression (from scratch)
to learn matrix-based training and prediction.

- Ridge Regression
to reduce multicollinearity and stabilize model coefficients.

- Lasso Regression
to automatically select the most impactful features.

# 📊 Results
Model	RMSE (log scale)	R² (log scale)
- Linear Regression (GD)	~0.35	~0.61
- Ridge Regression	~0.15	~0.52
- Lasso Regression	~0.15	~0.54

# ➡️ Lasso performed best and selected the most meaningful features.
