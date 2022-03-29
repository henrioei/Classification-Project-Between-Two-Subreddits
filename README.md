# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & Classification 

### Henri Oei, DSIF2 - Singapore

## Problem Statement

In this project we will be creating a model that can differentiate between a two subreddits, /r/dota2 and /r/leagueoflegends.

Both subreddits are similar in a sense that both shares under the same genre umbrella called "MOBA" or "Multiplayer Online Battle Arena."

## Executive Summary

We collected data from the subreddits /r/dota2 and /r/leagueoflegends by using their Reddit API and extracted 1000 posts from each subreddit. We then performed some pre-processing on the data listed as follows:

1. Tokenizing
2. Remove Stop Words
3. Lemmatizing/Stemming
4. Remove Punctuations
5. Remove Digits

We then created two models for our classification:

1. Random Forest Classifier with CountVectorizer

                 precision    recall  f1-score   support

          dota2       0.70      0.85      0.77       250
leagueoflegends       0.81      0.64      0.71       250

       accuracy                           0.74       500
      macro avg       0.76      0.74      0.74       500
   weighted avg       0.76      0.74      0.74       500

2. Multinomial Naive Bayes with TfidfVectorizer

                 precision    recall  f1-score   support

          dota2       0.70      0.79      0.74       250
leagueoflegends       0.76      0.66      0.71       250

       accuracy                           0.72       500
      macro avg       0.73      0.72      0.72       500
   weighted avg       0.73      0.72      0.72       500

## Conclusions and Recommendations

The Random Forest with CountVectorizer worked fairly well with an accuracy score of 74%. The Multinomial Naive Bayes with TfidfVectorizer worked well as well although it garnered a lower accuracy score of 72%.

The results that we obtained are decent even though both subreddits were fairly similar. However, we can improve our models by including the following:

1. Consider combining misspelled or alternately spelled words to a single representation (e.g. “cool”/”kewl”/”cooool”)
2. Consider lemmatization (reduce words such as “am”, “are”, and “is” to a common form such as “be”)
3. Tuning of parameters for random forest to get a better score.
4. Consider either boosting or bagging to get a more optimal outcome.

## Data

### *Data Dictionary*

|Feature|Type|Dataset|Description|
|---|---|---|---|
|subreddit|object|dotalol|Labels| 
|clean|object|dotalol|Combination of selftext and title that has been processed|
|leagueoflegends|int|dotalol|Target|