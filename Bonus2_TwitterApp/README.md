
## Overview
1. A model was developed to estimate the emotion of a tweet (the model was trained in CoLab).
2. The model was saved, and predictions were made using the flask framework.
3. Every time a user searches for something in the UI, it actually pulls relevant tweets from Twitter using the Twitter API and then informs us whether the speech is neutral, good, or bad.


## Technology used
- - 1.Flask Framework
- - 2.HTML 
- - 3.Python

# Description

## Summary
This paper provides information on how to gather data (tweets) from Twitter in real time using the Twitter API.
model that could foretell whether a tweet will be positive, negative, or neutral in mood. It further explains
about the pre-processing that went into the GaussianNB model that was used to train the data
The article concludes by describing how to utilize the Flask framework to construct an interface for interacting with the model.
on the basis of live tweets, make predictions.
## Twitter tweet collection and pre-processing
Twitter API ##
To access the twitter data via the services of the API, Twitter offers developer accounts.
assuming we have the appropriate access levels, a set of api keys, and a set of secrets. Tweepy is used in this text to obtain
info from twitter.


## Data labeling 
### Using textblob

Since the data obtained from Twitter is not labeled, text blob has been utilized to categorize the data into positive, negative, and neutral speech based on the polarity of the tweets. The csv has been manually reviewed for the accuracy of the labeling in order to confirm the resultsant labels.
### Data cleaning
The data has been processed to liberate the tweets of these undesired characters by removing some patterns that are not alphabets and other unneeded characters.


## Lemmatization 
Lemmatization is the process of combining a word's several inflected forms into a single unit for analysis. Similar to stemming, lemmatization adds context to the words. So it




### TF-IDF and a bag of words
When modeling text using machine learning techniques, one method of encoding text data is known as the bag-of-words model.
The bag-of-words approach has had considerable success in solving issues like language modeling and document classification because it is straightforward to comprehend and put into practice. Utilized TF-IDF as well because it has been shown to produce superior results to BOW.



### Data modeling 
### GaussianNB
Naive Bayes, a probabilistic classification model for machine learning that is simple but effective, is influenced by the Bayes Theorem. The Bayes theorem is a mathematical formula that provides a conditional probability that an event A will occur provided that an event B has already occurred. When the predictor values are continuous and are anticipated to follow a Gaussian distribution, the Gaussian Naive Bayes classifier is used.

The reason for training the model with both the bag of words and tf-idf is because the bag of words technique might not have completely removed the stop words, whereas in tf-idf, the idf removes the undesirable words, making it more clean and enabling the model to train with relevant data.

### Tensor flow-based model with LSTM

Defining the input layer comes first, then embedding. Words and their corresponding meanings are presented using embeddings. Similar to this, we are providing the maximum word count, the input word length, and the inputs from the preceding layer. Long-short-term memory (LSTM) stores the words and uses them to anticipate the next words. A sequence predictor of up and coming words is LSTM.
The Faltten layer sends inputs to the Dense layer, which decreases the outputs. The dense layer receives all of the inputs from the preceding layer, performs computations, and sends 256 outputs. A neural network model's activation function is a node that is positioned at the conclusion of or in-between the layers.



## Comparison of Models 
## Framework for UI Integrations using Flask

Python-based Flask is a microweb framework. Its status as a micro framework is a result of the fact that it doesn't need any special tools or libraries. One of the most popular frameworks for integrating ML models with the user interface is Flask, which is a strong framework.
Using the following code, the model from the colab has been imported and incorporated into the flask project structure. The get-related-tweets method, which retrieves the pertinent tweets from Twitter in real time as twitter, returns the tweet data that is needed to execute the model in the home.py file.would come up if we type something into the twitter search bar. Before being transmitted to the model for prediction, this data is then preprocessed.
The application's virtual environment has been given the name "Twitter" and all relevant packages have been installed. The folder hierarchy is displayed as follows. The github repository referred to at the beginning of the document contains the detailed code.

Below Screenshots.
