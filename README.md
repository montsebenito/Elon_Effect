## Elon Effect: Project Overview

Evaluated and optimized several supervised learning models (mae ~ $5900) to find out if there is a direct relationship between the content of Elon Musk's daily tweets and the price behavior of Bitcoin. 

This project follows the CRISP-DM process model:
- **Business Understanding**: Building a highly predictive model to forecast Bitcoin behavior, based on Elon Musk daily tweets, presents an undisputable lucrative advantage.  
- **Data Collection**: Crypto market data is collected using pandas data-reader library and yahoo finance API. Elon's tweets are fetched using tweepy.
- **Data Wrangling and Preparation**: Preprocessed tweets (removing stop words, hyperlinks, mentions,..) plus extracted most popular (tweeted) words and created new features considering if the tweet contains these words or not. Included training data from January-2019 to January-2022 (7278 tweets and replies) and 238 tweets on test data from January-2022 to February-2022.
- **Data Modeling**: Evaluated 3 different regression models to determine which algorithm will provide the lowest mean absolute error. Optimized Gradient Boosting Regressor using GridCV. Used MAE (mean absolute error) and not other model metric as it is very useful when the target follows a skewed distribution: outliers will not influence models attempting to optimize on this metric as much as if when the mean squared error is used in this case.
- **Results Evaluation**: Model predicts Bitcoin price with around 12% mean absolute error. Most interestingly, its trends and behaviour fits with real data with a preceeding offset that will allow a trader made buy/sell decisions in advance. 

You can take a look a [post](https://montsebenito.github.io/elonmusk/) about this project,too.


## Code and Resources Used
- Python Version: 3.8.5
- Packages: pandas, numpy, sklearn, matplotlib, seaborn, plotly, tweepy, nltk


## Repo Walk-Through
Please read this [project' post](https://montsebenito.github.io/elonmusk) for more detailed info.

- [01CryptoCollection:](https://github.com/montsebenito/eloneffect/blob/01CryptoCollection.ipynb) Collected Crypto market data using pandas data-reader library and yahoo finance API.
- [01TweetsCollection:](https://github.com/montsebenito/eloneffect/blob/01TweetsCollection.ipynb) Collected Elon Musk's tweets using tweepy. This method only allowed to fetch a few hundred of tweets per batch. Because of that, in the following sections, a dataset containing several years of Elon tweets and found in Kaggle is used.
- [02CryptoWrangling:](https://github.com/montsebenito/eloneffect/blob/02CryptoWrangling.ipynb) Very basic exploration of collected crypto data from 2019-01-02 to 2022-01-01.
- [02TweetsWrangling:](https://github.com/montsebenito/eloneffect/blob/02TweetsWrangling.ipynb) Consolidated a dataset with features extracted from collected tweets between 2019-01-01 and 2022-01-01. Cleaned and Tokenized Tweets content, word frequency and bag of words, engineered new features and feature selection.
- [03TestDataWrangling:](https://github.com/montsebenito/eloneffect/blob/03TestDataWrangling.ipynb) Consolidated a test dataset with BOW extracted in training set and tweets and bitcoin prices between 2022-01-01 and 2022-02-09.
- [04ML_PredictingBitcoin:](https://github.com/montsebenito/eloneffect/blob/04ML-Bitcoin.ipynb) Evaluated different regression models to determine which algorithm will provide the lowest mean absolute error. Optimized Gradient Boosting Regressor using GridCV.


## Thanks!:
- [Elon Musk Tweets] (https://www.kaggle.com/datasets/neelgajare/all-elon-musk-tweets-2022-updated)
- [Introduction to ML with Tensorflow](https://www.udacity.com/course/intro-to-machine-learning-with-tensorflow-nanodegree--nd230)
- Mehta, Neel; Agashe, Adi; Detroja, Parth. Buble or Revolution 
- Michael Jermaann [Predicting Stock Movement through Executive Tweets](https://web.stanford.edu/class/archive/cs/cs224n/cs224n.1174/reports/2743946.pdf)

