# Ames Housing Data Exploration
**by Lubomir Straka**


## Dataset

The data consists of information regarding 1460 houses in Ames, Iowa, including their sale price, physical characteristics, space properties and location within the city. The dataset and feature documentation can be found among [Kaggle's datasets](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data). Before exploration, I encoded nominal and ordinal categorical variables in line with the data description, imputed zeros to numerical and None to categorical variables in case of missing values, and did some basic cleaning.


## Summary of Findings

In the exploration, I found that there was a strong relationship between the price of a house and its six aspects falling into three categories: space (above grade living area, garage area, basement area), building (year of construction, remodeling or addition, overall quality of house's material and finish), and location (neighborhood). The relationships are approximatelly linear between price and selected house characteristics when price is transformed by a logarithmic function.

When investigating an above grade living area, I found four unusual sales being partial, abnormal or simply unusual. I removed these outliers from the dataset. Another anomaly in the dataset is a high number of houses apparently constructed or remodeled in 1950. Furthermore, it looks like the missing values in overall quality variable occur exclusively in observations with the best overall quality. These anomalies has no profound effect on the analysis.

As neighborhood is a nominal categorical variable, correlation with house prices is rather low. To reveal the effect of location I've clustered neighborhoods using unit prices per square feet. After this transformation the effect of location is obvious.


## Key Insights for Presentation

For the presentation, I focus just on influence of three explanatory variables on the response variable (sale price). I start by introducing the price variable, followed by the pattern in above grade living area, overall quality and neighborhood cluster distributions.

Afterwards, I introduce each of the selected variable one by one. To start, I use the histograms of sale price before and after transformation and the histogram of above grade living area without outliers identified. The overall quality and neighborhood clusters are covered afterward, using violin plots. Next, I'm looking at the scatter plot of transformed prices versus above grade living area with neighborhood clusters distinguished by colors. Finally, I provide violin plots of transformed price versus overall quality for individual neighborhood clusters.
