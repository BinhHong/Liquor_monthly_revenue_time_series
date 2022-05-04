[<img src="https://deepnote.com/buttons/launch-in-deepnote.svg">](https://deepnote.com/workspace/binh-hong-ngoc-a131-f8796abb-e60b-480f-8957-da759bc1ea9e/project/Time-series-fb855f0b-5d5f-43d2-a9d9-b4b5150d059e/%2FMonthly_revenue_time_series_A_liquor_company%2FMonthly_revenue.ipynb)

# Monthly revenue time series of a liquor company

## Introduction
In this project, I consider a time series of monthly revenue of Jim Beam Brands, a liquor company in Iowa State, USA. First of all, I explore the important characterizations of this time series, such as decompositions (both multiplicative and additive), stationary property, seasonal plot ... In the next step, I make some forecasts based on two models: SARIMA and Prophet. Trend changes detection, cross validation and more importantly, the hyperparameters tuning are also included.

## Dataset
The dataset used in this project is a part deduced from a huge dataset given by [Iowa’s state-hosted open data portal](https://data.iowa.gov/Sales-Distribution/Iowa-Liquor-Sales/m3tr-qhgy), which has around 24 million rows and 24 columns.

For the purpose of this project, I filtered the vendor named `Jim Beam Brands`, resulting in `2180745` rows. The following columns are considered:
- `Date`: date that bottles were sold to retailers.
- `Item Description`: names of the sold bottles.
- `Bottle Volume`: volume of each bottle.
- `State Bottle Cost`: cost the Iowa State pays to Jim Beam Brands for sold bottles.
- `State Bottle Retail`: money the State receives from selling bottles to retailers.
- `Bottle Sold`: number of bottles sold to retailers.

## Methodologies

1. In Exploratory Data Analysis, I created a time series of monthly revenue of `Jim Beam Brands`, made some visualizations:

![](plot1.png?raw=true)




