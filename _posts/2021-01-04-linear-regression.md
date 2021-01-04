---
layout: post
title:  Linear Regression - Explained
cover-img: /assets/img/linear-regression.jpeg
thumbnail-img: /assets/img/linear-regression.jpeg
---


Linear Regression is a popular machine learning algorithm that is based on the concept of a line. The independent variable is represented as x and the dependent variable is represented as y. All the linear regression models go through the point where the mean of x and the mean of y meet. 

The general line equation is:  y = mx + c 
where m is the slope (ratio between the change of y to the change of x) and c is the intercept (the value of y when x = 0)

<h3>Basic Assumption</h3>

- Linearity: The relationship between X and the mean of Y is linear.
- Homoscedasticity: The variance of residual is the same for any value of X.
- Independence: Observations are independent of each other.
- Normality: For any fixed value of X, Y is normally distributed.

<h3>Covariance</h3>

- In statistics, a variance is the spread of a data set around its mean value, while a covariance is the measure of the directional relationship between two random variables.
- Covariance gives the direction of linear relationship.
- If increasing the independent variable results in an increase of a dependent variable, there exists a positive covariance.

<h3>Correlation Coefficient (-1 <= R <= +1)</h3>

- Correlation coefficients are used to measure how strong a relationship is between two variables. 
- If the correlation value is 0, there is no relationship between the variables.
- For an interval variable, pearson coefficient is used. 

<h3>Coefficient of Determination (0 <= R² <= 1)</h3>

- This value tells us how much variance in y has been explained by the model. 
- A value close to +1 is desired.

<h3>Cost Function</h3>
<img src = "https://lh3.googleusercontent.com/proxy/sPRy4VoR1BK9-vfeB2f5-5DtHBfKcsAeSpG1z3ik7W0_WQPZwgo9o1f13JbcanKAbs2vz6w6qU-f9PzEiDA8gRn1ZYNZxnsIiefYfCDIxPR4Frr8MXcTrw">

- The above is the square error function. It is the square of the difference between the predicted value and the actual value. 
- m is the size of the training set.
- The difference is squared because a negative value will be positive, and the deviation is amplified.
- For simplicity, we take half the average error (1/2m). 
- The objective is to minimize the cost function.
- The cost function is dependent on the slope of the line. 

- Let us take the points (1,1), (2,2), (3,3) and try to find the best line that fits all three points.
- The line equation is, y = (slope)*(independent variable) + (intercept)
- Let us take the slope as 0,
- When slope = 0 and intercept = 0
  - y1 = 0
  - y2 = 0
  - y3 = 0
  - The loss function = 2.3
  
- When slope = 0.5 and intercept = 0
  - y1 = 0.5
  - y2 = 1
  - y3 = 1.5
  - The loss function = 0.58
 
- When slope = 1 and intercept = 0
  - y1 = 1
  - y2 = 2
  - y3 = 3
  - The loss function = 0
  
 - Since the loss function is minimum for slope = 1,  <b>y = (1)(x) + 0 </b> is the best fit line.
 
