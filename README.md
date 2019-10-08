# Election-prediction-using-Twitter
Using Python programming language to build a model that predicts the election result by getting the required data from Tweepy and by importing powerful python libraries like Numpy for all the arthematic and multi-dimensional array usage and Matplotlib for convenient graphical representations

# Description
Solution for the hierarchical location classification of Twitter users has been implemented using Python as the programming language.

# 'Prepare and insert a figure here'

These are the main python libraries used along with their usage:
# Tweepy: 
Tweepy is the Python library for the Twitter API. The API uses RESTful methods to access twitter. The authentication part in is handled by OAuth.
# TextBlob: 
Text Blob is a Python client for processing text strings. The main application of this API is to deal with NPL (natural language processing) . It is used to classification and sentiment analysis. 
# Numpy: 
NumPy is the basic package for computation in Python. NumPy can be used as an efficient multidimensional container of generic data. You can define arbitrary data types. This allows NumPy to integrate seamlessly with a wide variety of databases.
# Matplotlib: 
Matplotlib is a python library used to draw different types of graphics and figures. It can be imported and used in Python scripts and shells.

Authentication: OAuth consumer key and secret: Used the standard search API, with consumer key only per application is used to authenticate with the search Tweets. It is likely that that code base uses a language-specific OAuth package that abstracts all the underlying details of the "handshake". Conscious packages, the authentication route usually means configuring their keys and tokens, creating some type of HTTP object and then making requests with that object.

Request/Response behaviour: Using the parameters fromDate and toDate, we can request any period of time that the API supports. The 30-day endpoint provides Tweets for the most recent 31 days (although it is known as the 30-day endpoint, 31 days have been available for users to make full-month requests). The full file endpoint provides Tweets from the first tweet (March 21, 2006).

Each Tweet data request contains a parameter "maxResults" (range 10-500, with a default value of 100.Sandbox environments have a most of 100) that specifies the utmost range of Tweets to come back within the response. When the amount of data exceeds the "maxResults" setting (and will generally do so), the response will include a "following" token and paging will be required to receive all the data associated with your query.
Pagination: When making data and counting requests, there is likely to be more data than can be returned in a single response. If dealing with such a case, the response will have a "next" token. The "next" token is provided as JSON attribute. Each time a "next" token is provided, there is additional data to recover.
Here is a screenshot of our developer account in Twitter. We are using ‘Search Tweets: Full Archive/Sandbox’. The base URI for the premium search API is https://api.twitter.com/1.1/tweets/search/.
 
Figure3: Twitter API account
# Insert the snap shot at this place

•	First, created a Twitter Client class. It contains all the methods needed to interact with Twitter API and parsing tweets. Used a __init__ function to handle the authentication of API client.
•	In get tweets function, to fetch:
fetched_tweets = self.api. search (q = query, count = count)
to call the Twitter API to fetch tweets.
•	Text blob module used in get_tweet_sentiment.
analysis = Text Blob(self.clean_tweet(tweet))

Once we get the tweets, follow the following procedure:
First, use clean tweet function to get rid of links, special characters, etc from the tweet using simple regex. Then, as we pass tweet to create a Text Blob object then used text blob library to 

1.	Tokenize the tweet, i.e. split words from body of text.
2.	Remove stop words from the tokens. (stop words are the commonly used words which are irrelevant in text analysis like I, am, you, are, etc.)
3.	Do POS (part of speech) tagging of the tokens and select only significant features/tokens like adjectives, verbs, emotion words.
4.	The tokens are passed to a sentiment classifier which classifies the tweet sentiment as positive, negative or neutral by assigning it a polarity between -1.0 to 1.0.
Text Blob uses a Movies Reviews dataset in which we already have a training data set of positively or negatively labelled reviews. Positive and negative features are extracted from each positive and negative review respectively. Training data now consists of labelled positive and negative features. This data is trained using Naive Bayes Classifier. Then, sentiment is used. Polarity method of Text Blob class made into use to get the polarity of tweet between -1 to 1.
