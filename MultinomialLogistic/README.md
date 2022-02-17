# Multinomial Logistic Regression

This notebook shows the implementation of a Multinomial Logistic Regression model to classify twitter data into one of three classes: `negative, neutral, positive`. 



## Dataset

The dataset used in this notebook is a condensed version of the [Twitter US Airline Sentiment Dataset]([Twitter US Airline Sentiment | Kaggle](https://www.kaggle.com/crowdflower/twitter-airline-sentiment)) containing 14,640 tweets about airlines labelled as positive, negative and neutral.



## Preprocessing

We use a `Bag-of-Words` model to create a feature representation of the tweets for our model to learn.
