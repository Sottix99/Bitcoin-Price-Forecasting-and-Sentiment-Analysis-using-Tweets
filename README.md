![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)

This Repository refers to the Final Project of the course Data Driven Economics (DDE) at University Sapienza of Rome 2022/2023.

 
# Bitcoin Price Forecasting and Sentiment Analysis Using Tweets

This project aims to forecast Bitcoin prices by analyzing Twitter sentiment data. By combining machine learning techniques with sentiment analysis, we can identify leading indicators that correlate with Bitcoin price movements. The project uses various natural language processing models and forecasting methods to enhance prediction accuracy.

## Group members:
* [Giulia Luciani](https://github.com/Giulia-Luciani)
* [Alessandro Sottile](https://github.com/Sottix99)

## Table of Contents

- [Project Overview](#project-overview)
- [Data](#data)
- [Sentiment Analysis](#sentiment-analysis)
- [Forecasting Methods](#forecasting-methods)
- [Results](#results)
- [Conclusion](#conclusion)

## Project Overview

This project explores the relationship between Bitcoin prices and Twitter sentiment, leveraging techniques such as **DeBERTa sentiment classification**, **Word2Vec**, and **VADER sentiment analysis**. The analysis is conducted using a dataset of tweets from 2018 to 2022, alongside historical Bitcoin price data obtained from Yahoo! Finance.

## Data

- **Bitcoin Price Dataset**: Historical prices of Bitcoin (BTC-USD) from January 1, 2018, to December 31, 2022, sourced from [Yahoo! Finance](https://finance.yahoo.com/quote/BTC-USD/history/).
- **Twitter Dataset**: Tweets related to Bitcoin were preprocessed to remove bots and irrelevant content (https://drive.google.com/file/d/1y2VBx4GwzhYqukm-nl45xH6KeXJFHKht/view?usp=sharing)

### Data Preprocessing

- Removed bot-like tweets (e.g., those containing terms like "giveaway").
- Applied techniques like punctuation removal, emoji substitution with descriptions, and stopword elimination.
  
## Sentiment Analysis

Several sentiment analysis models and indices were applied to gauge public opinion:

### 1. **VADER (Valence Aware Dictionary and sEntiment Reasoner)**
   - Lexicon-based model designed for social media sentiment analysis.
   - Scores range from -1.0 (negative) to 1.0 (positive).

### 2. **DeBERTa Model**
   - Zero-shot sentiment classification model for Bitcoin tweets.
   - Applied during major price peaks and troughs to analyze sentiment from professionals versus non-professionals.

### 3. **Word2Vec**
   - Pretrained model that calculates sentiment scores based on positive/negative word similarity.
   - Positive words (e.g., "bullish") add to the score, while negative words (e.g., "bearish") reduce it.

## Forecasting Methods

We utilized multiple machine learning models to predict Bitcoin prices based on sentiment indicators:

### 1. **ARIMA (AutoRegressive Integrated Moving Average)**
   - Standard time series forecasting model.
   - Best performance was achieved using the **Word2Vec index**.

### 2. **Long Short-Term Memory (LSTM)**
   - Neural network model for time series data.
   - Exhibited good performance across all sentiment indices.

### 3. **XGBoost**
   - Decision tree-based ensemble model.
   - Best results were obtained using the **Vader Balanced index**, which combines VADER sentiment and the Fear and Greed Index.

## Results

- The **Word2Vec index** consistently performed well across most models, especially with ARIMA.
- **Vader Balanced** showed the best results in the **XGBoost** model.
- Overall, sentiment analysis effectively correlated with Bitcoin price movements, particularly during market highs and lows.

## Conclusion

This project demonstrates that Twitter sentiment, especially from professionals, can serve as a reliable predictor for Bitcoin price trends. Machine learning models like ARIMA and XGBoost, when combined with sentiment indices, offer effective forecasting capabilities.

## References

- **Word2Vec Model**: [word2vec-GoogleNews-vectors](https://github.com/mmihaltz/word2vec-GoogleNews-vectors)
- **Fear and Greed Index**: [Alternative.me Crypto Fear and Greed Index](https://alternative.me/crypto/fear-and-greed-index/)

