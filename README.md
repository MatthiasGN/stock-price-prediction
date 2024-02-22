# Stock Price Prediction using Artifical Intelligence
A project in Python. View spp.ipynb for implementation and spp_paper.pdf for research paper detailing method and results.

## Context

In the realm of stock market prediction, the primary goal is to predict the future value of a company’s stock price. This goal is difficult to achieve due to the irrational nature and volatility of stock price data. Many studies have been done using more traditional methods with low levels of success, especially when creating longer-term predictions. In recent years, the advances in machine learning have made this goal much more attainable. With highly accurate classifications and a dependency on large amounts of data, machine learning is one of the most effective tools that can be applied to this problem. Existing literature often focuses on very short-term predictions – the next-day closing price of the stock is typically predicted in regression models, while many classification models predict whether the closing price will increase or decrease the following day. Although accurate and impactful, these predictions are limited by their narrow scope.

## Abstract/Contribution

The aim of this project is to widen the scope to the medium-term, exploring the differences in accuracy when supervised machine learning models are trained to predict stock prices from one week all the way up to one month in the future. Predictions greater than one month into the future are deemed likely to be inaccurate given the highly erratic nature of the stock market. Regardless, if a long-term scope is even possible in this field, this project will aim to bridge the gap to it. The success of this project will have valuable impacts in the finance industry. Accurate short to medium-term stock price prediction will allow traders and investors to decrease their losses in short-term trading. There is the potential to lay down the basis for more successful strategies in personal finance, fund management, and portfolio management. Further to this, the exact nature of these predictions creates potential for them to be used in the development of automated trading bots in the future.

This project will focus on supervised regression models rather than classification. The set of algorithms to be applied are simple linear regression and the Long Short Term Memory (LSTM) Model, an advanced version of the Recurrent-Neural-Network (RNN). In existing studies, LSTM models often show very high accuracy when predicting day-to-day stock prices. The reason for this is that LSTM retains information from older stages in the neural network, in contrast to the more basic RNN. Although RNN may be accurate for short-term predictions, it is dependent on recent and current data because information from previous states does not persist. So, LSTM will prove to be more useful in predicting medium-term stock prices. Meanwhile, the application of a simple linear regression will provide a second set of results with which to compare accuracy with the more advanced LSTM model. The significance of the difference in accuracies may provide insight into future application of machine learning to longer-term predictions.

## Dataset/Features

Stock price data will be obtained from Yahoo Finance, with datasets containing the attributes of date, open, close, high and low. Date and close are the primary attributes of interest, where close represents the stock price when the market closes on that day. A number of further attributes can then be extracted from the closing price. In this case momentum, volatility, and exponential moving average will be used as features when training the machine learning models.

### Momentum
Momentum=0,close[i] < close[i-1]1,close[i] ≥ close[i-1]

### Volatility
Volatility=close[i-1] - close[i]close[i-1]

### Exponential Moving Average
The exponential moving average (EMA) is an advanced version of the moving average. The moving average calculates the average stock price over a given period of days. Meanwhile, the EMA applies higher weights to recent prices. This will be useful given the fairly short-term nature of the predictions. For greater variety, the 7-day, 20-day and 50-day EMAs will be tested as features.

{EMA}_{Today}\ =\ close[i]×21+n+close[i-1]×EMAYesterday

The models will be trained on these features to create predictions for the stock price for the following intervals: one week, one fortnight, one month. Depending on the resulting accuracies of the models, the time interval of the predictions may be changed for better results.

## Action Plan

Nov 4 – Nov 11: Data collection and preprocessing, feature extraction and scaling

Nov 12 – Nov 18: Train and test linear regression model

Nov 18 – Nov 25: Train and test LSTM model

Nov 26 – Nov 28: Evaluation of models and accuracies

Nov 28 – Dec 12: Final project writeup and editing

## Pitfalls

In the case that the trained regression and LSTM models perform to a low standard of accuracy, this will clearly be a large pitfall to the project. In this case, the number of features may be reduced or increased. Many more features can be extracted from the closing price, such as the volatility of the index in which the company belongs to, the index momentum, and so on. If this still fails to produce usable accuracy levels, the prediction time interval can be heavily shortened to between one day and one week such as two, three, four-day predictions and so on.
