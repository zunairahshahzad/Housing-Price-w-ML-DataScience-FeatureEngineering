## 🔍 Project Overview:
This project focuses on predicting residential home sale prices in Ames, Iowa, using the Kaggle House Prices: Advanced Regression Techniques dataset. The dataset contains **1,460 observations** and **79 explanatory variables** describing nearly every aspect of a home, including location, size, quality, condition, and amenities.

## 🔍 Objective:
The primary objective was to build an end‑to‑end **machine learning pipeline** that demonstrates strong data science fundamentals: data cleaning, exploratory data analysis (EDA), feature engineering, model development, and evaluation. This project also emphasizes reproducibility and good ML practices.

## 🔍Key Notes:
- **Tools:** 

  Python/Visualization
      Pandas, NumPy – data manipulation 
      Matplotlib, Seaborn, Plotly – data visualization

  Machine Learning
      Scikit-learn – preprocessing, modeling, evaluation (Linear Regression, LASSO, Ridge, Random Forest)
      XGBoost – gradient boosting models

- **Techniques**: EDA, feature engineering, regression modeling, hyperparameter tuning, ensemble learning
- **Goal**: Predict housing sale prices and compare classical regression with tree‑based and ensemble models

## 🔍 Problem Statement & Motivation:
Accurately estimating home prices is a core problem in real estate analytics. Prices are influenced by a mix of numerical and categorical features, often with non‑linear relationships and missing data. The challenge is to:
Prepare a complex real‑world dataset for modeling
Engineer meaningful features
Compare multiple regression approaches
Improve predictive performance using ensemble methods
Machine Learning Workflown:
This project follows a structured, end-to-end ML pipeline:
EDA → Data Cleaning → Feature Engineering → Modeling → Evaluation → Insights
Each stage is explained in detail below.
Data Exploration & Cleaning
Initial Data Inspection:
Examined dataset shape and structure
Reviewed summary statistics for numerical and categorical features
Identified skewness in the target variable (SalePrice)
Missing Values Analysis 
Computed both raw counts and percentages of missing values
Identified both true missing values (data not recorded) and structural missing values (e.g., no basement or garage)
Data Cleaning Strategy
Numerical features:
Imputed using median values to reduce sensitivity to outliers
Categorical features:
Imputed using the most frequent category or explicit labels such as None
Ensured consistency between training and test data preprocessing
This ensured data consistency while preserving meaningful information.

Exploratory Data Analysis (EDA)
Key EDA Steps
Inspected dataset shape, data types, and summary statistics
Analyzed the distribution of the target variable (SalePrice)
Identified skewness and outliers in numerical features
Explored correlations between numerical variables and sale price
Insights from EDA
Observed that SalePrice is right-skewed and applied log transformation to stabilize variance. 
Visualization showed that strong predictors (numerical) include OverallQual (overall material and finish quality), GrLivArea (above-ground living area), Garage and basement-related features
Location-based features (e.g., Neighborhood, lot shape, land contour) show large price differences
EDA informed feature transformations and model selection later in the pipeline.
Feature Engineering
Feature engineering was a core component of this project.
Feature Preparation
Separating numerical and categorical features
Encoding categorical variables using One‑Hot Encoding
Handling skewed numerical features using transformations
Aligning training and test datasets after encoding
Building reusable preprocessing pipelines
This step ensured that all models received clean, consistent, and ML‑ready input data.
Why Feature Engineering Matters
Enables ML models to work with categorical data
Improves model performance and generalization
Reduces noise and multicollinearity

Machine Learning Models
Multiple regression models were trained and compared to understand trade-offs between interpretability and performance.
Models Implemented
1. Linear Regression
Served as a baseline model for comparison 
Easy to interpret but limited in capturing non‑linear relationships
2. Regularized Regression (LASSO / Ridge)
Reduced multicollinearity
Helped with feature selection
Improved generalization over basic linear regression
3. Random Forest Regressor (decision tree)
Captured non‑linear interactions
Robust to outliers and feature scaling
Provided feature importance rankings
4. XGBoost Regressor
Gradient‑boosted trees for high predictive power
Hyperparameter tuning used to optimize performance
Best overall model in terms of predictive accuracy – as observed in this project 

Model Evaluation
Models were evaluated using validation techniques and regression metrics.
Used train‑validation splits
Evaluated models using metrics such as:
Root Mean Squared Error (RMSE)
Penalizes large prediction errors
Standard metric for regression problems
Compared model performance side‑by‑side
Tree‑based and ensemble models significantly outperformed linear baselines
Results
Linear models performed adequately but underfit complex patterns
Tree-based models significantly improved performance
XGBoost achieved the lowest RMSE and strongest generalization

Key Insights
Overall quality and living area are the strongest predictors of sale price
Location (neighborhood) has a major impact on valuation
Non‑linear models capture complex interactions better than linear models
Feature engineering and proper handling of missing values are critical for performance

Business & Practical Impact:
This project demonstrates how machine learning can be applied to real estate valuation:
Enables more accurate home price predictions
Supports data‑driven pricing strategies
Highlights the importance of property features and location using data 
The workflow mirrors real-world ML pipelines used in industry.
Conclusion:
This side project showcases end‑to‑end data science, machine learning, and analytics, including:
Data cleaning and EDA
Feature engineering at scale
End-to-end machine learning development
Model comparison and tuning
Interpreting results and communicating insights
Future Improvements
Cross-validation for more robust evaluation
Advanced feature selection
Model ensembling
SHAP values for model interpretability
