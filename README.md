# Stock Price Prediction with Deep Learning

## Project Overview

This project utilizes Long Short-Term Memory (LSTM) and Transformer models to predict stock prices based on historical data. It demonstrates how univariate time series forecasting can be approached using advanced deep learning techniques, specifically tailored to handle the nuances and complexities of financial market data.

## Data Preparation

The data preparation process involves extracting stock prices from Yahoo Finance, focusing on daily closing prices. The data is then organized into a format suitable for time series analysis, ensuring consistency in date formatting and handling any missing values through interpolation or forward filling.

## Data Preprocessing

Data preprocessing includes:

-   **Normalization**: Stock price data is normalized to ensure that the scale of the prices does not affect the model's ability to learn. Typically, Min-Max scaling is applied to transform the prices into a scaled range (e.g., 0 to 1).
-   **Sequence Creation**: The data is transformed into sequences that represent windows of consecutive days. Each sequence is used to predict the price at the next time step.

## LSTM Architecture

The LSTM model is designed to capture temporal dependencies and long-term relationships in the data:

-   **Input Layer**: Receives sequences of stock prices.
-   **LSTM Layers**: Multiple LSTM layers with dropout regularization to prevent overfitting. Each LSTM layer captures different temporal scales and dependencies.
-   **Dense Output Layer**: A fully connected layer that outputs the predicted stock price for the following day.

## Transformer Architecture

The Transformer model applies self-attention mechanisms to model sequences:

-   **Input Embeddings**: Transforms input sequences into dense embeddings which are then processed by the Transformer.
-   **Positional Encoding**: Adds information about the order of data points in the time series.
-   **Attention Layers**: Multiple layers of multi-head attention and feed-forward neural networks, allowing the model to focus on different parts of the input sequence for making predictions.
-   **Output Layer**: Similar to LSTM, a fully connected layer provides the final prediction.

## Evaluation Metrics

Model performance is evaluated using the following metrics:

-   **Mean Absolute Percentage Error (MAPE)**: This metric provides a clear percentage-based measure of how close the predictions are to the actual values, making it intuitive and straightforward for performance interpretation.
-   **Variance Ratio**: Compares the variance of the predicted values to the variance of the actual values to assess the consistency and stability of the model predictions over time.

# Next Steps

To further enhance the stock price prediction models, the following strategies can be explored:

-   [ ] **Multivariate Time Series Forecasting**: Incorporate additional features such as trading volume, technical indicators, or macroeconomic data to improve the model's predictive power.
-   [ ] **Candlestick Patterns**: Utilize candlestick patterns as input features to capture more detailed information about price movements and market dynamics.
-   [ ] **Hyperparameter Tuning**: Since only basic tuning was done, experiment with different configurations of model parameters to optimize performance, using techniques like grid search or random search.
-   [ ] **Ensemble Methods**: Combine the predictions from multiple models to improve accuracy and robustness, potentially integrating different model architectures.
-   [ ] **Advanced Feature Engineering**: Explore more complex features like technical indicators (e.g., moving averages, RSI, MACD) to see if they can provide additional predictive power.
