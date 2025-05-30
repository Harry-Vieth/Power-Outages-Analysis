---
layout: default
title: Power Outages Analysis
---

# Power-Outages-Analysis

**EECS 398 data analysis project**

## Introduction
In this project I am looking at power outage information. I am asking …..

## Data Cleaning and Exploratory Data Analysis
I chose to analyze total price by state. To impute the missing states I used the most frequent state. To impute the missing values for total price I first converted
all the values to numbers as there was a mix of strings and numbers. Then I used conditional mean imputation to fill missing values with the mean value of their respective state.
<iframe src="/Power-Outages-Analysis/assets/CleanedData.html" width="800" height="400" frameborder="0"></iframe>

I did univariate analysis on TotalPrice by creating 10 bins. The majority of the prices are in the 5-15 range.
<iframe src="/Power-Outages-Analysis/assets/univariate-plot.html" width="800" height="600" frameborder="0"></iframe>

I found the average cost for most states was around 10 cents per killowat-hour. There were some outliers such as Hawaii which was 23 cents.
<iframe src="/Power-Outages-Analysis/assets/state-vs-price.html" width="800" height="600" frameborder="0"></iframe>

I found through the pivot table that cold weather had the highest prices, warm had the least expensive, and normal climate was in between.
<iframe src="/Power-Outages-Analysis/assets/pivot.html" width="800" height="600" frameborder="0"></iframe>

In terms of imputation the following shows the changes before and after imputation:
Here is Climate before and after --
<iframe src="/Power-Outages-Analysis/assets/Climate-Category-Pre-Imputation.html" width="800" height="600" frameborder="0"></iframe>
<iframe src="/Power-Outages-Analysis/assets/Climate-Category-Post-Imputation.html" width="800" height="600" frameborder="0"></iframe>

Here is Year before and after -- 
<iframe src="/Power-Outages-Analysis/assets/Year-Pre-Imputation.html" width="800" height="600" frameborder="0"></iframe>
<iframe src="/Power-Outages-Analysis/assets/Year-Post-Imputation.html" width="800" height="600" frameborder="0"></iframe>

Here is U.S. State before and after --
<iframe src="/Power-Outages-Analysis/assets/US-State-Pre-Imputation.html" width="800" height="600" frameborder="0"></iframe>
<iframe src="/Power-Outages-Analysis/assets/US-State-Post-Imputation.html" width="800" height="600" frameborder="0"></iframe>

## Framing a Prediction Problem
I used regression. 

## Baseline Model
Month is quantitative. Climate category is one-hot encoded and quantitative. Total price is quantitative. The mean absolute error is 2.43

## Final Model
I added a year input that was standardized. Adding year likely improved the performance since there is a time-based correlation. I used Ridge Regression to prevent overfitting. The hyperparameter was alpha. In terms of features month was feature engineered to be scaled month, quantile month, and poly month. The baseline model's mean absolute error was 2.43 and 2.40 for the final model.
