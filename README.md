# ARIMA - Time Series Forecasting
Time Series Forecasting - ARIMA MODEL
Time Series is a current hot topic in the data world.Large amounts of data is getting accumulated in the servers but many do not know what to do with it.What if there is a way to analyse it and predict the future values so that the decisions can be made.
What is a Time Series ?
Time Series is a sequence where you record a particular feature at constant time intervals.
Using Time Series we can predict future values as well as other forms of analysis.
Time Series has two types of properties which makes it different from other problems like regression .
1)It is TIME dependent whereas in regression it is time independent.
2)So it will have some form of seasonality trends other than increasing and decreasing trends.(Because time dependent it varies accordingly.)
With these properties in place ,to analyse it , various models are used .
By using this time series if you want to predict the future values,you need to do a analysis over the data. In order to do analysis ARIMA MODEL is used .
Before that , How to check whether time series is stationary ?
A Time Series is said to be stationary if the properties like mean,variance remain constant over time.It is important to maintain because most of the Models work on the assumption that Time Series is stationary.We can say that if a time series has a particular characteristics over time, it is high probability that they remain same over future.So it is easier to implement the stationary than the non-stationary data.
So,stationary has to follow the statistical properties very strictly.They are :
1) mean constant over time
2) variance constant over time and
3)auto-co variance that does not depend upon time.
How to check the stationary ?
There are two ways to do it.They are Plotting Rolling Statistics and Dickey-Fuller Test.
Plotting Rolling Statistics : Plot the Moving Average and see if varies with time .
Dickey-Fuller Test : Here we use Hypothesis Testing. Consider Null-Hypothesis that time series is non-stationary . Results consists of Test Statistic and Critical Value for various confidence levels.If Test Statistic is less than Critical value then reject null hypothesis and say that the series is stationary.
If Time series is not stationary,How to make it ?
Generally in real life scenario , Time series data is non stationary.Though we cannot make it stationary entirely we can make it nearly.There are two reasons why a time series in non-stationary.They are Trend and Seasonality.
Trend is where mean varies over time and whereas Stationary varies at specific time intervals.
The general principle is to model or estimate by removing both of these properties from the series ,then apply the statistical forecasting techniques .At-last we have to transform them back to original by adding the trend and seasonality to the data.
How to Eliminate and Estimate the trend ?
First thing which occurs to our mind is Transformation.We apply this transformation which penalise the higher values than the smaller values.It can be square,cube,log etc.
But the problem is we cannot see the trend if there is noise in it.To estimate the model we have to remove it from the series .Some ways of doing it are :
1)Aggregation - taking average over a time interval like monthly etc.
2)Smoothing - taking rolling averages ??
3)Polynomial Fitting - fit a regression model
Ex: Moving Averages for Smoothing
The problem with yearly or any other periodic average is that it has to be strictly defined.So if we take in case of stock price we cannot come with a number.So we use 'Weighted Moving Average' in which the recent values are given more weight.So for assigning more weights we have a method called exponentially weighted moving average where weights are assigned to all the previous values with decay factor.
Eliminating Trend and Seasonality : There are two ways to remove trend and seasonality.They are Differencing and Decomposition.In both the cases we can use Dickey-Fuller test
Differencing : Take the present value and remove it past value.This itself makes most the series stationary.
Decomposing : In this, we separate both the trend and seasonality to model them by returning the remaining part of the series.
Forecasting a Time Series ?
Having performed the trend and seasonality estimation ,there can be two situations:
1) A strictly stationary series with no dependence among the values.This is easy case where we can model the residuals as white noise.
2)A series with significant dependence among the values.In this case we need to use some statistical methods like ARIMA to forecast the data.
In ARIMA MODELS,Based upon the past values , we can predict the future values.There are two types of Models in ARIMA. They are : 1) SARIMA & 2) SARIMAX models.
So How the data can be ??
Depending on the frequency , it can be either annually(budget), quarterly (expenses), monthly (), weekly (sales), daily , hourly (stock prices), minutes (call centre requests), seconds (Web traffic).
Forecasting is where you will predict the next step or values of the series is going to take.Forecasting will be helpful in demand and sales of a company etc.Forecasting a time series of demand and sales has greater use . So its important to get the forecasts accurate in order to save costs and is critical to business and its success.
Time Series forecasting can be applied in many ways.
Forecasting a time series can be divided into two types. They are 1)Uni-variate Time Series Forecasting and 2) Multi-Variate Time Series Forecasting
Uni-variate uses only its previous values to predict its future values.
Multi Variate uses predictors other than the series to forecast its future values. Ex: Some Predictors are:??
ARIMA algorithm's general idea is that the past values of the time series alone can forecast the future values.
2.Introduction to ARIMA Models: What is an ARIMA Model??
ARIMA stands for Auto Regressive Integrated Moving Averages. It uses its own lags and the lagged forecast errors so that we can forecast future values. or This model explains a given time series based on its past values to forecast the future values.
What is LAG ?
Lag is essentially delay. Just as correlation shows how much two time series are similar,auto-correlation describes how similar the time series is with itself.
Any non-seasonal time series that exhibits patterns and is without white noise can be modelled using ARIMA models.
ARIMA model has 3 parameters.They are d,p,q.where
d is the number of differencing required to make the time series stationary
p is the order of the AR(Auto-Regressive) term
q is the order of the MA(Moving Averages)term
If a time series has seasonal patterns then you need to add seasonal terms and it becomes SARIMA.
What p,d,q does mean ??
The first step to build an ARIMA model is to make the time series stationary.
Why?
Because, term 'Auto Regressive' in ARIMA means it is a linear regression model that uses its own lags as predictors. Linear regression models, as you know, work best when the predictors are not correlated and are independent of each other.
So how to make a series stationary?
By differencing it we can make the series stationary.Subtract the present value with immediate past value.Sometimes, depending on the series, more than one differencing may be needed.
The value of d, therefore, is the minimum number of differencing needed to make the series stationary. And if the time series is already stationary, then d = 0.
Next, what are the 'p' and 'q' terms?
'p' is the order of the 'Auto Regressive' (AR) term. It refers to the number of lags of Y to be used as predictors. And 'q' is the order of the 'Moving Average' (MA) term. It refers to the number of lagged forecast errors that should go into the ARIMA Model.
How to determine p ,q ?
We can use two types of plots to determine these numbers.They are Auto correlation Function(ACF) and Partial Auto correlation Function(PACF).
ACF :It is a measure of correlation between the time series with a lagged version of itself
PACF: It is a measure of correlation between the TS with a lagged version of itself but after eliminating the variations
So what are AR and MA models? what is the actual mathematical formula for the AR and MA models?
A pure Auto Regressive (AR only) model is one where Yt depends only on its own lags. That is Yt
is a function of the 'lags of Yt'.
Likewise a pure Moving Average (MA only) model is one where Yt depends only on the lagged forecast errors.
Use the Models AR ,MA and the combined one ,
ARIMA model in words :
Yt = Constant + Linear Combination of Lags of Y (upto p lags) + Linear Combination of Lagged Forecast errors (upto q lags)
Once when you have decided the p,d,q , take it back to original scale by adding the cumulative index to the new values .
Then predict the forecast values using those values (p,d,q) and compare it with original series.
