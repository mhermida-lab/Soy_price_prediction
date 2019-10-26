# Soy_price_prediction
Model created for Sadosky Foundation Meta Data and Matba Rofex competition. 
They needed a model to predict the price of soy beans in a future 20 days time serie.

In this repo I develop two models: 

1. A Multivariate Multi Step Neural Network with Long Short Term Memory neurons.
This model uses parallel time series with historical data (daily/monthly values 2004-2019) inflation in the US, historical oil prices, and historical soy prices for its training.
I arranged the data into an input matrix of 20 steps for each time serie (20x4) to return a prediction of 20 steps in the future for each time serie.
The objective is to predict soy prices taking into account the correlation with the variation of the other time series (inflation and iol prices).
I left this model fully trained but further tunning is needed.

2. An Univariate Single Step Neural Network with Long Short Term Memory neurons.
This model uses only one time serie with historical data (daily prices 2004-2019) of soy bean prices in the Rosario (Argentina) market for its training.
I arranged the data into a 20 step input vector to return a prediction of 1 step in the future. Then a loop function is needed  to use the predicted output as part of the input vector and then predict the next step into the future. The function iterates until 20 steps are completed. 

The univariate model won the first price of the competition.
