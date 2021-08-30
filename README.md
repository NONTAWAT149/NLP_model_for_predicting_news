# Data Science Udacity Nanodegree
# Project 4: Data Scientist Capstone

Nontawat Pattanajak (30 August 2021)

This project is one of 4 mandatory projects of Data Science Nanodegree. 


## Project Definition

### Project Overview

One of the most important factors relating to stock market trend is news. Positive and negative news could be a trigger to change price of stock market. Building an automatic trading system requires signal from news to input system. Not only does the trading system require, individual traders also need information from news to analyse the market trend.

This project uses BERT model - one of the most state-of-the-art Deep Learning models in Natural Language Processing, to develop a tool to analyse news. It analyses the news and provides output as two classes - positive/neutral and negative news.
The dataset of this project referred to "Sun, J. (2016, August). Daily News for Stock Market Prediction, Version 1. Retrieved from https://www.kaggle.com/aaron7sun/stocknews". The dataset that combines news from 25 sources and trend of stock market price of each day.

This project will show how to develop an NLP model to understand news relating to stock market trend (positive/neutral trend and negative trend).


### Problem Statement

News could be one of the most important factors in stock market prediction. It is challenging tasks to monitor news from many sources real time. Building a tool to understand news relating to stock market trend is important. This porject is to develop an NLP model to extract signal (positive/neutral or negative) from news.


### Metrics

This project uses "Model Accuracy" to measure the performance of an NLP model.


## Dataset Analysis

### Data Exploration
- The data is between 2018-08-08 and 2016-07-01.
- There are 1,989 data samples
- The source of data is from 25 sources (topics).
- The data is labelled into 2 groups (0 and 1).
-- 0: Price of stock market at close value rose or stayed the same
-- 1: Price of stock market at the close value decreased


## Methodology

### Data Preprocessing

The original dataset is .csv file. Pandas (data processing framework) is a tool to do preprocessing data. It is used to pull csv data, remove unexpected word, and sort/split the data into input data and label data.

For text preprocessing, BERT model already contains word embedding process. This means that we do not need to do data featuring. We can feed text data into the pre-train model directly.

### Implementation

In this project, BERT model [link](https://arxiv.org/abs/1810.04805) is considered to use. The pre-train model is called from TensorFlow Dev [link](https://www.tensorflow.org/text/tutorials/classify_text_with_bert). However, we add one layer at the end of BERT model as the classification layer. 

### Refinement

From the early state of development, the model experience two issues (1) low accuracy score and (2) over-fitting (accuracy gap of training and test data is about 50%). The model has been improved by adding Batch Normalisation layer to improve model accuracy and adding dropout to overcome an over-fitting issue.


## Result

During model is training, the accuracy of training data increases, while for the test data, the accuracy is slightly fluctuated but in overall, it remains the same. At the final state (epoch 30), the model accuracy of training data is 87.30% and unseen data (test data) is 51.51%. The accuracy of training data seems to be able to increase if we expand the number of epochs. On the other hand, the accuracy of unseen data is different. It stays remain and is not in the acceptable level. In addition to this, this model still experiences over-fitting issue. We may consider including other techniques to fix the issues such as adding L1/L2 regularization. 


## Conclusion

This project shows a possible way to implement the state of the art model in NLP (BERT model) to develop a tool to understand news relating to stock market trend. The accuracy of the model is still not in the acceptable level. There is some room for the improvement such as adding more process to clean the data in data pre-processing level. The data might contain too much noise for the BERT model.

[Report Link](https://nontawat149.medium.com/bert-for-sentiment-analysis-predicting-news-for-stock-market-trends-9e598a8433bb)
