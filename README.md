# Stock Price Prediction Using Deep Learning

Predicting Stock Market with LSTM and Transformers  
Assaf Levanon & Tal Machavariani  
Deep Learning - Spring 2024 - 00046211

## Introduction
This project is a deep dive into predicting daily stock movements using deep learning techniques, with a primary focus on Long Short-Term Memory (LSTM) and BERT transformer models. Our initial aim was to predict the next day's closing price based on historical data and financial news. This README provides an overview of our approach, findings, and conclusions.

## Project Overview
In the financial markets, stock price prediction is a challenging task due to the inherent volatility and large number of external influencing factors. Our project explores the feasibility of using deep learning models to make informed predictions by leveraging two main data sources:

- Historical Stock Data: Previous closing prices of the stock.
- Financial News Sentiment: News articles and financial reports from the day, processed using BERT transformers for sentiment analysis and contextual understanding.

## Model Setup:

We started with an LSTM model that predicted the next day's closing price based solely on a sequence of previous closing prices.
Additionally, we utilized a BERT transformer model to analyze the day's financial news headlines and obtain sentiment-driven insights. These two submodels are then aggregated with a concatenation layer for the final output.  
![image](https://github.com/user-attachments/assets/9d46504d-e5e2-4ae3-a4ef-fe1d5057ab1b)

## Initial Results:

The models were able to produce predictions that visually resembled the actual stock price trends.
However, we observed a lag in predictions: the predicted prices consistently trailed the actual stock performance by a day or more, resulting in delayed responses.
## Refining the Objective:

We revised our approach to predict the day's gain or loss rather than the absolute closing price, hypothesizing that this could produce more actionable insights and reduce the lag.
Unfortunately, predictions for the day's gain/loss were not satisfactory, with low correlation to actual market outcomes.
## Conclusion
Our analysis led us to conclude that predicting daily stock gain/loss with this approach is not feasible given the current model setup and data limitations. The delayed predictions suggest that short-term stock movements are likely influenced by a broader range of factors than historical prices and news sentiment alone.


