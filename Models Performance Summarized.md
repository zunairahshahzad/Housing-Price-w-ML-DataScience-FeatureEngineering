**Initial Models (Baseline)**

- Random Forest achieved a strong RMSE of 0.154, showing robustness to raw, non-linear data.
- XGBoost performed best at this stage with an RMSE of 0.131, benefiting from boosting and regularization.
- MLP underperformed with a test RMSE of 0.232, likely due to noisy and high-dimensional input features.
- Linear Regression failed with an extremely high RMSE (35,351,564,048), caused by unscaled features and multicollinearity.


**After PCA**

- Random Forest showed marginal improvement to 0.152, since PCA offers limited benefit for tree-based models.
- XGBoost slightly declined to 0.137, suggesting PCA removed useful feature interactions.
- MLP improved to 0.202, indicating reduced overfitting after dimensionality reduction.
- Linear Regression improved drastically to an RMSE of 0.163, as PCA reduced multicollinearity and stabilized variance.


**After Feature Engineering**

- Random Forest reached its best performance with an RMSE of 0.151, benefiting from richer feature splits.
- XGBoost remained competitive at 0.137, but did not surpass its baseline result.
- MLP achieved its best result with an RMSE of 0.130, showing the strongest response to feature engineering.
- Linear Regression remained stable at an RMSE of 0.164, showing limited gains from engineered features.


**Overall:**

- Random Forest - Most stable Model (RMSE ≈ 0.15) as it is robust to feature scaling and correlations, so its performance stayed consistent regardless of PCA or feature engineering.
  
- XGBoost - Strong mostly throughout (best RMSE ≈ 0.137), slightly better with feature engineering. Its boosting and regularization made it effective even without PCA or extensive feature engineering, though engineered features slightly helped it capture additional predictive patterns.
  
- MLP - Best overall performance after feature engineering (RMSE = 0.130) as new features helped neaural network learn complex patterns.
  
- Linear Regression - Biggest improved a lot after PCA (35B → 0.163 RMSE) since PCA removed correlated features, allowing Linear Regression to make more reliable predictions on transformed, uncorrelated components.
