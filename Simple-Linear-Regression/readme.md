### Linear Regression

Linear regression is a type of supervised machine-learning algorithm that learns from the labelled datasets and maps the data points with most optimized linear functions which can be used for prediction on new datasets. It assumes that there is a linear relationship between the input and output, meaning the output changes at a constant rate as the input changes. This relationship is represented by a straight line.

#### Best Fit Line in Linear Regression
In linear regression, the best-fit line is the straight line that most accurately represents the relationship between the independent variable (input) and the dependent variable (output). It is the line that minimizes the difference between the actual data points and the predicted values from the model.

- For simple linear regression (with one independent variable), the best-fit line is represented by the equation
```
y=mx+b
```

- To find the best-fit line, we use a method called Least Squares. The idea behind this method is to minimize the sum of squared differences between the actual values (data points) and the predicted values from the line. These differences are called residuals.


#### Types of Linear Regression
When there is only one independent feature it is known as Simple Linear Regression or Univariate Linear Regression and when there are more than one feature it is known as Multiple Linear Regression or Multivariate Regression.

1. Simple Linear Regression
Simple linear regression is used when we want to predict a target value (dependent variable) using only one input feature (independent variable). It assumes a straight-line relationship between the two.
2. Multiple Linear Regression
Multiple linear regression involves more than one independent variable and one dependent variable. The equation for multiple linear regression

#### Cost function for Linear Regression
In Linear Regression, the cost function measures how far the predicted values  are from the actual values (Y). It helps identify and reduce errors to find the best-fit line. The most common cost function used is Mean Squared Error (MSE), which calculates the average of squared differences between actual and predicted values:
Gradient Descent for Linear Regression
Gradient descent is an optimization technique used to train a linear regression model by minimizing the prediction error. It works by starting with random model parameters and repeatedly adjusting them to reduce the difference between predicted and actual values.
![alt text](image.png)

How it works:

Start with random values for slope and intercept.
Calculate the error between predicted and actual values.
Find how much each parameter contributes to the error (gradient).
Update the parameters in the direction that reduces the error.
Repeat until the error is as small as possible.