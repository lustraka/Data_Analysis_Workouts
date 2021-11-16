# Ames Housing Data Exploration
**by Lubomir Straka**


## Dataset

> Provide basic information about your dataset in this section. If you selected your own dataset, make sure you note the source of your data and summarize any data wrangling steps that you performed before you started your exploration.

The data consists of information regarding 1460 houses in Ames, Iowa, including their sale price, physical characteristics, space properties and location within the city. The dataset and feature documentation can be found among [Kaggle's datasets](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data). Before exploration, I encoded nominal and ordinal categorical variables in line with the data description, imputed zeros to numerical and None to categorical variables in case of missing values, and did some basic cleaning.


## Summary of Findings

> Summarize all of your findings from your exploration here, whether you plan on bringing them into your explanatory presentation or not.

In the exploration, I found that ther was a strong relationship between the price of a house and its ... with modifying effects from ...

The relationship is approximatelly linear between price and ... when price is transformed to be on a logarithmic scale (and ... transformed to be on a ... scale).

I found a somewhat surprising result initially when the marginal trend for ... variables indicated that higher ... was associted with lower price. Howerer, higher ... was also associated with smaller ... When I isolated ... there was a clear positive relationship between ... and ...

Outside of the main variables of interest, I verified the relationship between ... and .... For the dataset given, there was an interesting interaction ...  The ... looked like they had slightly better distribution of ... then ... with ...


## Key Insights for Presentation

> Select one or two main threads from your exploration to polish up for your presentation. Note any changes in design from your exploration step here.

For the presentation, I focus just on influence of ... and leave out most of the intermediate derivations. I start by introducing the price variable, followed by the pattern in ... distribution, then plot the transformed scatterplot.

Afterwards, I introduce each of the ... variable one by one. To start, I use the violin plot of ... I'm only looking at ... here since it"s the clearest example of how the ... affect house pricing. The other ... variables are covered afterwards, using point plots. I've made sure to use different color palettes for each ... variable to make sure it is clear that they're different between plots.
