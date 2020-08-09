---
layout: post
title: Novel Corona Virus Disease - Analysis and Forecasting
cover-img: /assets/img/covid-world.jpg
thumbnail-img: /assets/img/covid-world.jpg
---
### Overview
 2019 Novel Coronavirus (2019-nCoV) is a virus (more specifically, a coronavirus) identified as the cause of an outbreak of respiratory illness first detected in Wuhan, China. Early on, many of the patients in the outbreak in Wuhan, China reportedly had some link to a large seafood and animal market, suggesting animal-to-person spread. However, a growing number of patients reportedly have not had exposure to animal markets, indicating person-to-person spread is occurring. At this time, it’s unclear how easily or sustainably this virus is spreading between people - CDC. This dataset has daily level information on the number of affected cases, deaths and recovery from 2019 novel coronavirus. Please note that this is a time series data and so the number of cases on any given day is the cumulative number. The data is available from 22 Jan, 2020.

### Objective
  To predict the number of worldwide confirmed cases, active cases, recoveries and deaths by 14th May 2020.


### Workflow
- Step 1 : Problem definition
- Step 2 : Gathering information
- Step 3 : Preliminary (exploratory) analysis
- Step 4: Choosing and fitting models
- Step 5: Using and evaluating a forecasting mode

   
### Column Description
Sno - Serial number
ObservationDate - Date of the observation in MM/DD/YYYY
Province/State - Province or state of the observation (Could be empty when missing)
Country/Region - Country of observation
Last Update - Time in UTC at which the row is updated for the given province or country. (Not standardised and so please clean before using it)
Confirmed - Cumulative number of confirmed cases till that date
Deaths - Cumulative number of of deaths till that date
Recovered - Cumulative number of recovered cases till that date


### Libraries Used:
1. NumPy
2. Pandas
3. Matplotlib
4. Seaborn
5. Plotly
6. Statsmodels
7. Scikit Learn
8. Facebook’s Prophet

### Data Cleaning 
Columns which are not considered:
1. SNo
2. Province/State 
3. Country/Region
4. Last Update
Since we are predicting the number of worldwide cases, pandas groupby() function was used and the numbers were summed up. 

### Exploratory Data Analysis
1. Out of the 3.1 million cases, about 970k people (30.5%) have recovered and 227k (7.1%) people have lost their lives. 
2. The Recovered and Deaths add up to the closed cases which is approximately 37% of the total cases.
3. About 1.9 million cases are still active which is 62.4% of the total cases.
4. There were only 250k cases by the end of the first 8 weeks. 
5. But by the end of 15 weeks, the number of cases climbed up to 3.1 million.
6. This shows the rate at which the virus spreads. 
7. The US has the greatest number of confirmed cases. The UK has an insignificant number of recoveries. In Turkey, there is an insignificant number of deaths.

## Time Series Analysis
### Trend
A trend exists when there is a long-term increase or decrease in the data. It does not have to be linear. Sometimes we will refer to a trend as “changing direction”, when it might go from an increasing trend to a decreasing trend. 
#### Types of Trend patterns
Positive Trend – It has a positive slope.
Negative Trend – It has a negative slope.
No Trend – It is just a horizontal line with zero slope.
### Seasonal
A seasonal pattern occurs when a time series is affected by seasonal factors such as the time of the year or the day of the week. Seasonality is always of a fixed and known frequency. 
### Cyclic
A cycle occurs when the data exhibit rises and falls that are not of a fixed frequency. These fluctuations are usually due to economic conditions, and are often related to the “business cycle”. The duration of these fluctuations is usually at least 2 years.

### Forecasting Models which were used in this case study:
1. Holt’s model (Double exponential smoothing)
2. Autoregressive model
3. ARIMA model
4. Facebook’s Prophet model

## General Time Series Forecasting models
### Simple Exponential Smoothing
This model is suitable for forecasting data with no trend or seasonal pattern. The forecast plot is simply a horizontal line extending from the most recent value.

### Double Exponential Smoothing  
This model takes trend into account. Here the forecast plot is still a straight line extending from the most recent value, but it has slope.

### Triple Exponential Smoothing 
This model has (so far) the "best" looking forecast plot, as it takes seasonality into account. When we expect regular fluctuations in the future, this model attempts to map the seasonal behavior.
Since our data has a positive trend with no seasonality, we are choosing Double Exponential Smoothing method.

### Evaluating forecast accuracy (Holt’s model)
1. Standard Deviation of Test data : 325,029.92
2. Mean absolute error (MAE) : 59,530.96
3. Mean Squared error (MSE) : 4,102,198,558.34
4. Root Mean Squared error (RMSE) : 64,048.40
5. R2 value : 0.96

I. This model predicted 4,613,092 confirmed cases by May 14, 2020.
II. Number of Active cases by 14th May : 2,411,128
III. Number of Recoveries by 14th May : 1,538,211
IV. Number of Deaths by 14th May : 384,901

### Evaluating forecast accuracy (Autoregressive Model)
1. Standard Deviation of Test data : 325,029.92
2. Mean absolute error (MAE) : 193281.17
3. Mean Squared error (MSE) : 96379461983.61
4. Root Mean Squared error (RMSE) : 310450.41
5. R2 value : 0.08

I. his model predicted 4,727,363 confirmed cases by May 14, 2020.
II. Number of Active cases by 14th May : 2,350,483
III. Number of Recoveries by 14th May : 1,768,459
IV. Number of Deaths by 14th May : 673,726

## ARIMA Model
ARIMA, or Autoregressive Integrated Moving Average is actually a combination of 3 models:
AR(p) Autoregression - a regression model that utilizes the dependent relationship between a current observation and observations over a previous period
I(d) Integration - uses differencing of observations (subtracting an observation from an observation at the previous time step) in order to make the time series stationary
MA(q) Moving Average - a model that uses the dependency between an observation and a residual error from a moving average model applied to lagged observations.
pmdarima Auto-ARIMA is a third-party tool which shows a recommended (p,d,q) ARIMA Order of (0,2,2) with no-seasonal order component.

### Evaluating forecast accuracy
1. Standard Deviation of Test data : 325,029.92
2. Mean absolute error (MAE) : 23957.27
3. Mean Squared error (MSE) : 691817369.54
4. Root Mean Squared error (RMSE) : 26302.42
5. R2 value : 0.993

I. This model predicted 4,454,258 confirmed cases by May 14, 2020.
II. Number of Active cases by 14th May : 2,450,200
III. Number of Recoveries by 14th May : 1,625,422
IV. Number of Deaths by 14th May : 367,525

## Facebook's Prophet Library
This is specifically designed to forecast the daily business data sets that are common at Facebook, Inc. 
Prophet requires only a few lines of code to produce its forecast results.
Unlike with ARIMA models, the measurements do not need to be regularly spaced, and we do not need to interpolate missing values e.g. from removing outliers.
The input to Prophet is always a dataframe with two columns: ds and y.
The ds (datestamp) column should be of a format expected by Pandas, ideally YYYY-MM-DD for a date or YYYY-MM-DD HH:MM:SS for a timestamp. The y column must be numeric, and represents the measurement we wish to forecast.

### Steps in Prophet model 
1. Format the data
2. Create and fit a model. 
3. Create "future" placeholder dataframe.
4. Predict and fill in the Future
5. Plot the forecast. 
6. Evaluate the accuracy. 

### Evaluating forecast accuracy (Facebook's Prophet Library)
1. Standard Deviation of Test data : 325,029.92
2.  Mean absolute error (MAE) : 23503.46
3. Mean Squared error (MSE) : 668779741.09
4. Root Mean Squared error (RMSE) : 25860.77
5. R2 value : 0.999

I. This model predicted 4,402,222 confirmed cases by May 14, 2020.
II. Number of Active cases by 14th May : 2,673,383
III. Number of Recoveries by 14th May : 1,398,758
IV. Number of Deaths by 14th May : 328,023


### Summary
An R-squared-value of 1.00 depicts that the error is zero. Prophet Model has an R-squared-value of 0.999 and ARIMA model has an R-squared-value of 0.993. Thus, out of the four models, the results of Prophet and ARIMA models will be more accurate. 
The root-mean-squared-error is compared with the standard deviation of the test data to check the goodness of fit of that model.

1. From the results of the four models and if the same trend continues, we could expect around 4.42 million confirmed cases by May 14, 2020.
2. From the results of the four models and if the same trend continues, we could expect around 2.5 million active cases by May 14, 2020.
3. From the results of the four models and if the same trend continues, we could expect around 1.45 million recovered cases by May 14, 2020.
4. From the results of the four models and if the same trend continues, we could expect around 340,000 deaths by May 14, 2020.

### Actual number of cases on 14th May, 2020
- Confirmed cases      :   4,442,163  (Predicted : 4,420,000)
- Active cases         :   2,551,852  (Predicted : 2,500,000)
- Recovered            :  1,587,893   (Predicted : 1,450,000)
- Deaths                 :  302,418      (Predicted : 340,000)






