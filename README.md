# price_prediction_ai
# Stock Price Prediction with LSTM

## Overview

This project aims to predict future stock prices using a Seq2Seq LSTM (Long Short-Term Memory) model. By leveraging historical stock price data, the model is trained to forecast future stock prices over a specified time horizon. This approach is particularly useful for financial analysts and traders looking to make informed investment decisions.

## Libraries Used

- **pandas**: For data manipulation and analysis.
- **numpy**: For efficient numerical operations.
- **tensorflow/keras**: For building and training the LSTM model.
- **yfinance**: For downloading historical stock price data from Yahoo Finance.
- **matplotlib**: For visualizing actual and predicted stock prices.

## Project Steps

### 1. Load Data

The project starts by loading historical stock price data for a specified symbol (e.g., AAPL for Apple Inc.) over a given date range. This is done using the `yfinance` library, which retrieves adjusted closing prices and corresponding dates.

### 2. Normalize Data

Normalization is performed to scale the data, which helps improve the performance and training speed of the model. The data is normalized using the mean and standard deviation.

### 3. Split Data

The dataset is split into training and validation sets. Typically, 80% of the data is used for training and the remaining 20% for validation. This ensures that the model can be evaluated on unseen data to prevent overfitting.

### 4. Generate Sequences

Input-output pairs are generated from the time series data. These pairs are created based on a specified lookback period (the number of past days considered for predicting future prices) and prediction horizon (the number of future days to predict).

### 5. Build Model

A Seq2Seq LSTM model is constructed using the Keras API. The model consists of an encoder LSTM that processes the input sequences and a decoder LSTM that generates the output sequences. This architecture is well-suited for time series prediction tasks.

### 6. Train Model

The model is trained using the training dataset. Training involves optimizing the model's weights to minimize the mean squared error between the predicted and actual stock prices. The training process includes validating the model on the validation dataset to monitor its performance.

### 7. Predict Prices

After training, the model is used to predict future stock prices. The prediction process involves feeding the model with the most recent data and iteratively predicting the next set of future prices over the specified horizon.

### 8. Denormalize Predictions

The predicted prices are denormalized to convert them back to their original scale. This step is crucial for making the predictions interpretable and comparable to the actual stock prices.

### 9. Visualize Results

Finally, the actual and predicted stock prices are plotted using `matplotlib`. This visualization helps in assessing the model's performance and the accuracy of its predictions.

## Usage

1. **Set Parameters**: Define the stock symbol, date range, lookback period, and prediction horizon.
2. **Load and Preprocess Data**: Fetch the historical stock data, normalize it, split it into training and validation sets, and generate sequences.
3. **Build and Train Model**: Construct the Seq2Seq LSTM model and train it on the prepared data.
4. **Predict and Visualize**: Use the trained model to predict future stock prices and visualize the results alongside actual prices.

By following these steps, this project provides a robust framework for stock price prediction using advanced machine learning techniques. It combines data preprocessing, model training, and result visualization in a systematic manner, enabling users to make data-driven investment decisions.
