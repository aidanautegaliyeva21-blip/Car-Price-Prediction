# #  Car Price Prediction with Machine Learning



This project predicts **used car prices** based on various technical and categorical features using a variety of machine learning models. It includes **exploratory analysis, model evaluation, feature importance**, and **residual analysis** to build a robust solution.


##  Problem Statement

In the used car market, pricing is often inconsistent and lacks transparency. This project builds ML models to help:

-  **Buyers**: assess whether a car is fairly priced  
-  **Dealerships**: automate pricing decisions  
-  **Platforms**: recommend price ranges based on car specifications



##  Approach

The complete pipeline includes:

-  Exploratory Data Analysis (EDA)
-  Data Cleaning and Feature Engineering
-  Model Training (Linear & Tree-based regressors)
-  Evaluation using metrics (MAE, RMSE, R²)
-  Cross-validation
-  Residual and Feature Importance Analysis


##  Skills & Tools Used

- **Languages**: Python  
- **Libraries**: pandas, NumPy, matplotlib, seaborn, scikit-learn  
- **Techniques**:
  - Regression Modeling (Linear, Ridge, Lasso, Decision Tree, Random Forest, Gradient Boosting)
  - One-hot encoding
  - Feature correlation analysis
  - Cross-validation
  - Model interpretation



##  Models Trained & Evaluated

| Model                      | Test RMSE ↓ | R² Score ↑ |
|---------------------------|-------------|------------|
|  Random Forest           | **1879**     | **0.955**   |
| Gradient Boosting         | 2610        | 0.913      |
| Decision Tree             | 2721        | 0.906      |
| Linear Regression         | 3045        | 0.882      |
| Ridge Regression          | 3183        | 0.871      |
| Lasso Regression        | 155094      | -303.7     |

 **Cross-validated RMSE (Random Forest):** 2365 ± 610  
   **Best performance achieved by Random Forest Regressor**


## Key Features Influencing Price

| Feature       | Impact        |
|---------------|----------------|
| `enginesize`  | Strong positive |
| `curbweight`  | Strong positive |
| `horsepower`  | Strong positive |
| `brand`       | Luxury brands like BMW and Porsche increase price significantly |


##  Residual Analysis

- Residuals from the Random Forest model were centered around 0 and randomly distributed.
- Errors increased slightly for very high-priced cars due to fewer examples in the dataset.



##  Results Summary

-  **Goal**: Predict car prices based on specs and brand
-  **Best Model**: Random Forest Regressor
-  **Test RMSE**: ~$1879  
-  **R² Score**: 0.955  
-  **Cross-Validated RMSE**: $2365 ± $610  
-  Model generalizes well and is ready for production use



