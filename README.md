[<img src="https://deepnote.com/buttons/launch-in-deepnote.svg">](https://deepnote.com/workspace/binh-hong-ngoc-a131-f8796abb-e60b-480f-8957-da759bc1ea9e/project/Time-series-fb855f0b-5d5f-43d2-a9d9-b4b5150d059e/%2FMonthly_revenue_time_series_A_liquor_company%2FMonthly_revenue.ipynb)

# Monthly revenue time series of a liquor company

## Introduction
In this project, I consider a time series of monthly revenue of Jim Beam Brands, a liquor company in Iowa State, USA. First of all, I explore the important characterizations of this time series, such as decompositions (both multiplicative and additive), stationary property, seasonal plot ... In the next step, I make some forecasts based on two models: SARIMA and Prophet. Trend changes detection, cross validation and more importantly, the hyperparameters tuning are also included.

## Dataset
The dataset used in this project is a part deduced from a huge dataset at [Iowa’s state-hosted open data portal](https://data.iowa.gov/Sales-Distribution/Iowa-Liquor-Sales/m3tr-qhgy), which has around 24 million rows and 24 columns.

For the purpose of this project, I filtered the vendor named `Jim Beam Brands`, resulting in `2180745` rows. The following columns are considered:
- `Date`: date that bottles were sold to retailers.
- `Item Description`: names of the sold bottles.
- `Bottle Volume`: volume of each bottle.
- `State Bottle Cost`: cost the Iowa State pays to Jim Beam Brands for sold bottles.
- `State Bottle Retail`: money the State receives from selling bottles to retailers.
- `Bottle Sold`: number of bottles sold to retailers.

## Methodologies

- After cleansing the data, I created a time series of monthly revenue of `Jim Beam Brands` and made some visualizations:

![](Pictures/monthly_revenue_plot.png?raw=true)

A first glimpse of seasonality as well as the distribution of revenue are also explored.

- For better understanding, I check the stationary property, seasonality and make decompositions in both multiplicative and additive cases.
- Finally, the forecasts are carried out based on two models: `SARIMA` and `Prophet`. 

In SARIMA, I use `auto_arima` to search for best possible parameters `p`, `q`, `d` and test the result on a training set. Due to fact that this dataset has unexpected trend changes and outliers, two training sets are used to validate the accuracy.

With Prophet model, a cross-validation is implemented, and later used in hyperparameters tuning, including `changepoint_prior_scale` and `seasonality_prior_scale`. These parameters are then put into the forecast to effectively the `RMSE` error.

## Results

### 1. The seasonality can be somewhat suggested by seasonal plot

<img src="https://user-images.githubusercontent.com/95805829/166657110-0670a864-f47c-44c0-9b02-1b67be735047.png" width=50% height=50%>
and the box plots:
<img src="https://user-images.githubusercontent.com/95805829/166657110-0670a864-f47c-44c0-9b02-1b67be735047.png" width=50% height=50%>

### 2. Decomposition

<img src="https://user-images.githubusercontent.com/95805829/166657110-0670a864-f47c-44c0-9b02-1b67be735047.png" width=50% height=50%>

### 3. Forecasts with SARIMA model

<img src="https://user-images.githubusercontent.com/95805829/166657110-0670a864-f47c-44c0-9b02-1b67be735047.png" width=50% height=50%>

On another training set containing info of outliers, the result is better

<img src="https://user-images.githubusercontent.com/95805829/166657110-0670a864-f47c-44c0-9b02-1b67be735047.png" width=50% height=50%>

### 4. Forecasts with Prophet model

<img src="https://user-images.githubusercontent.com/95805829/166657110-0670a864-f47c-44c0-9b02-1b67be735047.png" width=50% height=50%>

After hyperparameters tuning, we get an improvement

<img src="https://user-images.githubusercontent.com/95805829/166657110-0670a864-f47c-44c0-9b02-1b67be735047.png" width=50% height=50%>

