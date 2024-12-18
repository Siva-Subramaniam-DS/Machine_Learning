### Project: **Movie Audience Rating Prediction**

This project uses machine learning models to predict audience ratings for movies based on various features such as genre, directors, runtime, and tomatometer ratings. Multiple regression models are evaluated to identify the best-performing model for this task.

---

### Table of Contents

1. [Introduction](#introduction)  
2. [Features and Target Variable](#features-and-target-variable)  
3. [Preprocessing](#preprocessing)  
4. [Model Training](#model-training)  
5. [Evaluation Metrics](#evaluation-metrics)  
6. [Performance Comparison](#performance-comparison)  
7. [Conclusion](#conclusion)  

---

### Introduction

This project aims to predict the audience ratings for movies using various regression models. The dataset includes both numerical and categorical features related to movies. By preprocessing the data and using a pipeline, we systematically evaluate different machine learning models and compare their performance.

---

### Features and Target Variable

#### Features:
1. **Categorical**:
   - `genre`: The genre of the movie.
   - `directors`: The director(s) of the movie.
   - `writers`: The writer(s) of the movie.
   - `studio_name`: The studio responsible for the movie.

2. **Numerical**:
   - `runtime_in_minutes`: The duration of the movie.
   - `tomatometer_rating`: The tomatometer rating score from Rotten Tomatoes.

#### Target:
- **`audience_rating`**: The audience rating score to be predicted.

---

### Preprocessing

The preprocessing stage involves handling both numerical and categorical features using a `ColumnTransformer`. 
- Numerical features (`runtime_in_minutes`, `tomatometer_rating`) are standardized using `StandardScaler`.  
- Categorical features (`genre`, `directors`, `writers`, `studio_name`) are encoded using `OneHotEncoder` to convert them into numerical formats.

The `preprocessor` is then integrated into a pipeline for seamless model training.

---

### Model Training

We implemented a pipeline that combines the preprocessing step with machine learning models. The following models were evaluated:
1. Random Forest Regressor
2. Gradient Boosting Regressor
3. Linear Regression
4. Lasso Regression
5. Support Vector Regressor

Each model is fitted on the training data (`X`, `y`), and predictions are made on the same dataset. Note: For best practices, testing should ideally be done on a separate validation or test set.

---

### Evaluation Metrics

To evaluate model performance, the following metrics were calculated:
1. **R² Score**: Measures the proportion of variance explained by the model. Higher is better.
2. **Root Mean Squared Error (RMSE)**: Indicates the average error magnitude. Lower is better.
3. **Mean Squared Error (MSE)**: The squared average error. Lower is better.
4. **Mean Absolute Error (MAE)**: Measures the average absolute difference between predictions and actual values. Lower is better.
5. **Explained Variance**: Indicates how much of the target variable’s variance is explained by the model. Higher is better.

---

### Performance Comparison

The performance of each model was summarized in a table for comparison. The model with the highest R² score and lowest error metrics (RMSE, MSE, MAE) was identified as the best-performing model. Example table:

| **Model**                |     **R² Score**     |       **RMSE**      |      **MSE**       |       **MAE**      | **Explained Variance** |
|--------------------------|----------------------|---------------------|--------------------|--------------------|------------------------|
| Random Forest            | 0.5399032148900288   | 13.229661034113064  | 175.02393107752957 | 10.220519053876478 |   0.5399032471286811   |
| Gradient Boosting        | 0.5680315132334677   | 12.81888201092687   | 164.32373601006452 | 10.271470519191245 |   0.5680563928909064   |
| Linear Regression        | -0.34930719502721064 | 22.655806967609344  | 513.2855893535761  | 16.379138251761265 |  -0.34921488265097644  |
| Lasso Regression         |  0.5262224456864176  | 13.424909246494215  | 180.22818827660586 | 10.834126100932135 |   0.5262814237097795   |
| Support Vector Regressor | 0.49064392502177534  | 13.919859853445526  | 193.76249833956453 | 10.600624724575018 |   0.4943837980921141   |

---

### Conclusion

The project demonstrates how preprocessing and model evaluation can be systematically integrated to predict audience ratings effectively. Random Forest and Gradient Boosting Regressors showed the best performance for this dataset, with high R² scores and low error metrics. Further steps include using cross-validation and testing the models on unseen data for more robust evaluation.

---

# Metrics:
**R² Score (Coefficient of Determination):**

- This score indicates how well the model’s predictions match the actual data.
Range: 0 to 1 (higher is better)
- 1 means the model perfectly fits the data.
- 0 means the model does not explain the variance of the target at all.
- Negative values could indicate a model that is worse than a simple mean-based model.

**RMSE (Root Mean Squared Error):**

- This measures the square root of the average squared differences between predicted and actual values.
- Lower is better.
- It gives an indication of how far off, on average, your predictions are from the actual values.

**MSE (Mean Squared Error):**

- This measures the average of the squared differences between predicted and actual values.
- Lower is better.

**MAE (Mean Absolute Error):**

- This calculates the average of the absolute differences between predicted and actual values.
- Lower is better.
- This gives a sense of how large the errors are in your predictions, without considering their direction (whether the prediction is higher or lower than the actual value).

**Explained Variance:**

- This shows how much of the variance in the target variable can be explained by the model.
- Higher is better.
If it is close to 1, the model is explaining most of the variance.


---


# How to Determine if the Output is Correct:
**Comparing R² scores:**

- A higher R² score means better predictive accuracy. If a model’s R² score is 
significantly higher than others, it is performing better.

**Evaluating RMSE, MSE, MAE:**

- Check which model has the lowest error values (RMSE, MSE, and MAE). Models with lower values for these metrics are making more accurate predictions.
- For example, a model with an RMSE of 1.24 is performing better than one with an RMSE of 1.76, so the first model is preferable.

**Explained Variance:**

- This should also be high for better models. If your model's explained variance is around 0.8 or higher, it is explaining a good portion of the target's variance.

**Conclusion:**
- The output is correct if you see reasonable values for these metrics, and if the models are performing similarly or better than simpler models (e.g., a random guess or the mean of the target variable).
- If your R² score is very low or negative, or if your error metrics (RMSE, MSE, MAE) are unusually high, the model is not performing well.

---

### Visualization

**Correlation Heatmap**
![Correlation Heatmap](https://github.com/user-attachments/assets/4b865151-0bfc-4bd6-a4e5-6533f610748b)

---

**PairPlot of Numerical Features and Target**
![PairPlot of Numerical Features and target](https://github.com/user-attachments/assets/6a7f4af0-968f-4dbc-b077-3443b78bcd9c)

---

**R2 Score comparison**
![R2 Score comparison](https://github.com/user-attachments/assets/c218a115-98e9-4573-92c0-7f984da0326c)

---

**RMSE Comparison**
![RMSE Comparison](https://github.com/user-attachments/assets/8dd801ab-cbd4-42f1-bbb6-47cefc9a5787)
