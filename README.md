# LSTM Stock Predictor

![deep-learning.jpg](Images/deep-learning.jpg)

Due to the volatility of cryptocurrency speculation, investors will often try to incorporate sentiment from social media and news articles to help guide their trading strategies. One such indicator is the [Crypto Fear and Greed Index (FNG)](https://alternative.me/crypto/fear-and-greed-index/) which attempts to use a variety of data sources to produce a daily FNG value for cryptocurrency. Here I build and evaluate deep learning models using both the FNG values and simple closing prices to determine if the FNG indicator provides a better signal for cryptocurrencies than the normal closing price data.

I have used the recurrent neural network to model bitcoin closing prices. One model will use the FNG indicators to predict the closing price while the second model will use a window of closing prices to predict the nth closing price.

Steps:
1. Prepare the data for training and testing
2. Build and train custom LSTM RNNs
3. Evaluate the performance of each model

- - -

## Steps

### Prepare the data for training and testing

I have created a window of time for the data in each dataset for each RNN. 
For the Fear and Greed model, I haveused the FNG values to try and predict the closing price.
For the closing price model, I have used the previous closing prices to try and predict the next closing price. 
Each model is divided by a 70:30 ratio for the training and testing the data. 
I have scaled the data using MinMaxScaler to X and y to sclae the data. 
Finally, I have reshaped the X_train and X_test values to fit the model's requirement of samples, time steps, and features. 

### Build and train custom LSTM RNNs

In one notebook I fit the data using the FNG values. In the other one, I fit the data using only closing prices.

### Evaluate the performance of each model

Finally, I use the testing data to evaluate each model and compare the performance and answer questions such as:

- Which model has a lower loss?
- Which model tracks the actual values better over time?
- Which window size works best for the model?
