# Predicting Stock Market Performance from Financial News Reports and Past Performance Using Transformer Architecture

Assaf Levanon & Tal Machavariani  
Deep Learning - Spring 2024 - 00046211

## Project Overview
This project aims to predict future stock market performance by leveraging both historical market data and relevant financial news reports. We use a Transformer architecture for integrating text data from news articles with past market performance and compare it to a traditional LSTM model that solely considers historical market data.


## Table of Contents
* Introduction
* Methodology
* Experiments and Results
* Conclusion
* Installation and Usage
* Acknowledgements


## Introduction
The goal of this project is to demonstrate that financial news reports contain valuable insights that can be leveraged to better understand future market performance. This information can be explicit, such as revenues, open lawsuits, layoffs, and bankruptcies, or implicit, like analysis opinions, public attitudes, and policymakers’ beliefs and ideas.


## Methodology
We developed a neural network to predict stock market performance using datasets of financial news headlines and historical market data. The architecture features an embedding layer to convert textual data into numerical form, followed by LSTM layers that capture temporal dependencies and sequential patterns in the news headlines. These layers are then succeeded by fully connected layers that map the processed text features to stock market gains or losses.

### Data
* Historical Market Data: S&P500 index and the 40 biggest companies that make up the index, from 2005 to 2020 (acquired from yfinance).
* Financial News Headlines: Used for training and testing the LSTM with BERT module.

### Models
* Plain LSTM: Predicts the next day’s Gain/Loss based solely on a sequence of previous day’s Gain/Loss.
* LSTM with BERT: Utilizes a BERT transformer model to analyze financial news headlines and obtain sentiment-driven insights.

![image](https://github.com/user-attachments/assets/9d46504d-e5e2-4ae3-a4ef-fe1d5057ab1b)

### Hyperparameter Tuning
* Optuna Library: Used for hyperparameter optimization.
* Optimizers: Adam, RMSprop, SGD.
* Scheduler: StepLR with step size and gamma as hyperparameters.
* Loss Criterion: Mean square error (MSE).


## Experiments and Results
* Plain LSTM: Mediocre results, predictions follow the general trend of the market on some occasions and produce random noise on others.
* LSTM with BERT: Produces a constant prediction for the gain, indicating a failure to extract useful insights from the news.
* Both modules performed poorly compared to two naïve models: constant market prices (Gain = zero) and constant market gain (10% annually). 


![Figures for README](https://github.com/user-attachments/assets/4f9e1dff-5c95-4f65-8dfb-63becf1ec24c)
![Comparison to Naive modules](https://github.com/user-attachments/assets/6ade6bf8-2274-4d4b-97ae-add955f84b49)



## Conclusion
* The project has failed to produce a module that outperforms the naive approach of Constant Gain. Yet, there is much room for further improvement and research. Our computational resources were scarce, and we gathered a relatively small amount of data. We believe that a deeper examination of the problem, cross-referencing multiple datasets, and combining other types of data (e.g., historical interest rates or US national debt) into the encoder-decoder architecture may produce superior results.
* We shall note a considerable fault of our research – the Plain LSTM and LSTM with BERT modules were trained on different stock market price datasets. This negatively affected our ability to compare the results of the two modules and should be avoided in future projects. The use of Optuna was extremely beneficial and will be of great importance in our future research.


## Installation and Usage
To use the project you should download the repository, install the required dependencies and run the source code from it's directory

### Repository Structure
* README.md: Project overview and instructions.
* requirements.txt: List of dependencies.
* Project_Report.pdf: contains In-depth examination of the project
* data/: Directory to store datasets.
* src/: Directory to store Source code.


### Clone the repository:
```
git clone https://github.com/AssafLe/DLproject.git
```

### Install the required dependencies:
```
pip install -r requirements.txt
```

## Acknowledgements
* Greg Hogg’s “Stock Price Prediction & Forecasting with LSTM Neural Networks in Python” YouTube tutorial.
* https://huggingface.co/docs/transformers/en/model_doc/bert
* https://github.com/tomer9080/Stock-Prediction-Using-RWKV/tree/main?tab=readme-ov-file
* https://github.com/tamirhaver129/Deep-Learning-Course-046211-Project-Predictinting-Stock-Prices?tab=readme-ov-file
