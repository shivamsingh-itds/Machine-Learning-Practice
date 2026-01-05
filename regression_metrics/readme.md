#### Evaluation Metrics for Linear Regression
A variety of evaluation measures can be used to determine the strength of any linear regression model. These assessment metrics often give an indication of how well the model is producing the observed outputs.

#### The most common measurements are:

1. Mean Square Error (MSE)
Mean Squared Error (MSE) is an evaluation metric that calculates the average of the squared differences between the actual and predicted values for all the data points. The difference is squared to ensure that negative and positive differences don't cancel each other out.
```
MSE = (1/n) * Σ(y_i - ŷ_i)²
```
MSE is a way to quantify the accuracy of a model's predictions. MSE is sensitive to outliers as large errors contribute significantly to the overall score.

2. Mean Absolute Error (MAE)
Mean Absolute Error is an evaluation metric used to calculate the accuracy of a regression model. MAE measures the average absolute difference between the predicted values and actual values.

Mathematically MAE is expressed as:
```
MAE = (1/n) * Σ|y_i - ŷ_i|
```
Lower MAE value indicates better model performance. It is not sensitive to the outliers as we consider absolute differences.

3. Root Mean Squared Error (RMSE)
The square root of the residuals' variance is the Root Mean Squared Error. It describes how well the observed data points match the expected values or the model's absolute fit to the data. In mathematical notation, it can be expressed as:
```
RMSE = √(MSE) = √[(1/n) * Σ(y_i - ŷ_i)²]
```
RMSE is in the same unit as the target variable and highlights larger errors more clearly.

4. Coefficient of Determination (R-squared)
R-Squared is a statistic that indicates how much variation the developed model can explain or capture. It is always in the range of 0 to 1. In general, the better the model matches the data, the greater the R-squared number.
In mathematical notation, it can be expressed as:
```
R² = 1 - [Σ(y_i - ŷ_i)² / Σ(y_i - ȳ)²]
```
R squared metric is a measure of the proportion of variance in the dependent variable that is explained the independent variables in the mode

5. Adjusted R-Squared Error
Adjusted R^2measures the proportion of variance in the dependent variable that is explained by independent variables in a regression model. Adjusted R-square accounts the number of predictors in the model and penalizes the model for including irrelevant predictors that don't contribute significantly to explain the variance in the dependent variables.

Mathematically, adjusted is expressed as:
```
Adjusted R² = 1 - [(1 - R²) * (n - 1) / (n - p - 1)]
```