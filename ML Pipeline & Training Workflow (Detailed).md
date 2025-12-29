This section explains, in detail, how the machine learning pipeline was constructed, how models were trained, and how performance was evaluated. 

**What I’ve Done**

I built an end-to-end ML pipeline where preprocessing and modeling were combined using scikit-learn pipelines. The data was split into training and validation sets, preprocessing was fit only on training data to avoid leakage, and multiple regression models were trained and evaluated using RMSE. Tree-based ensemble models like Random Forest and XGBoost significantly outperformed linear baselines due to their ability to capture non-linear relationships.

**Why Build an ML Pipeline?**

In real-world machine learning, preprocessing must be applied **consistently** to both training and test data and pipelines also ensure reproducibility. Performing preprocessing outside a pipeline can lead to:

- Data leakage
- Inconsistent feature transformations
- Inflated performance metrics

To avoid these issues, this project uses **Scikit-learn Pipelines**, which bundle preprocessing and modeling into a single, reusable object.

**Pipeline Architecture (High Level):**
	
  The project follows this structure:
  
  <img width="533" height="220" alt="image" src="https://github.com/user-attachments/assets/56277132-0c6f-47e5-ae2e-3fc169c3addb" />


Each step is **fit only on the training data**, then **applied to unseen data**.


**STEPS**

**1. Preprocessing Pipeline:**

  **Numerical Features**

 For numerical columns:
 
- Missing values are imputed using the **median**
- Median is chosen as it is robust to outliers and skewed distributions

**Categorical Features** 

  For categorical columns: 
  
  - Missing values are filled using the most frequent category or explicit None labels
  - Categorical variables are transformed using One-Hot Encoding
      - *Why One-Hot Encoding?* One-hot encoding converts categorical values into binary features, allowing models to process non-numeric data without introducing ordinal bias
   

**ColumnTransformer**

A ColumnTransformer is used to apply different preprocessing steps to numerical and categorical columns:

- Numerical columns → Median imputer
- Categorical columns → Mode imputer → One-hot encoder

This design keeps preprocessing modular, scalable, and consistent across all models.


**2. Train–Test Split**

Before training any model:

- The dataset is split into **training** and **validation** sets
- Models are trained **only on training data**
- Performance is evaluated on **unseen validation data** 

*Why?* This setup provides a realistic estimate of model performance on new data, preventing overfitting. 

**3. Model Training Process**

Each regression model is wrapped inside the same preprocessing pipeline:

Pipeline = Preprocessing + Model

This ensures that every model receives identical feature transformations, allowing for fair comparison. 

We trained for different models for practice and experimentation. These models included linear regression model, regularized regression (LASSO/Ridge), Random Forest Regressor, XGBoost Regressor. 
 
 
**4. Model Evaluation**

**Metric Used:** Root Mean Squared Error (RMSE)

*Why?*

- RMSE penalizes large prediction errors
- It is the standard metric for regression tasks
- Directly interpretable in the same units as price

**Evaluation Process**

- Predict on validation data
- Compute RMSE for each model
- Compare results consistently across pipelines

**Outcome**

- Linear models underfit complex relationships
- Random Forest improved performance significantly
- **XGBoost** achieved the **lowest RMSE**, showing strongest generalization
