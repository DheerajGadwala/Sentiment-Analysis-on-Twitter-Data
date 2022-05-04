<h3> Introduction </h3>

Twitter is a popular online platform where large number of people post their opinions of variety of matters. These opinions could be with positive or negative connotation. Identifying the tone of the message can help filter the posts that are offensive or degrading. 

Applying Natural Language Processing techniques and Machine Learning algorithms we could train models to classify a given text into positive or negative message. Such models can be used to quickly filter out offensive or inappropriate content from social media platform making it interesting.

In this project, we train and test a different model such as Support Vector Machine, Decision Trees, KNearest Neighbors, Logistic Regression, etc. and compare their performance based on accuracy and choose the best model for the application. 

<h3> Dataset </h3>

We found a suitable datasetafter scouring through Kaggle. This <a href="https://www.kaggle.com/datasets/kazanova/sentiment140">dataset</a> contains 1.6M tweets that were extracted using the twitter developer API. The raw data from twitter was annotated with either a 0 indicating negative emotion, or a 4 indicating positive emotion. 

Instead of manually annotating the tweets, the creators used the twitter search API to collect tweets that had indicators of positive or negative emotion like presence of emoticons {for instance, :)-> positive and :(-> negative}. 

The dataset contains 6 fields in total: Target {polarity of the tweet}, Ids: tweet id, date: date on which the tweet was posted, flag: The query, if a query was involved in fetching the data else ‘NO_QUERY’, user: the user that posted the tweet, and text: the content of the tweet.

<h3> Data Preprocessing </h3>

The data set contains 6 columns but for classification of tweets, we only required the classified target column andtheir respective tweets column. Hence other unnecessary columns were dropped. The following preprocessing steps were taken only on the tweet columns:

<ol>
  <li>Removed URLs, web-addresses, and email ids.</li>
  <li>Convert the tweets to lower case.</li>
  <li>Tokenize the data: Remove the work.</li>
  <li>Remove stop-words: Dropping common words that do not add meaning or value to the classification. We obtains the list of stop-words in Englishfrom nltk.corpus library.</li>
  <li>Stemming: PorterStemmer algorithm</li>
  <li>Lemmatization: WordNetLemmatizer.</li>
  <li>Vectorization: TFIDF and Glove.</li>
</ol>

<h4> Evaluation Methodolgy </h4>

After training the model with 85% of the data, we test the model with 15% of the data and evaluate its performance using different metrics such as Accuracy, Classification Report, and Receiver Operative Characteristic (ROC) curve.

The Classification reports provides the count of True Negatives (0,0), False positives (0,1), False Negatives (1,0) and True Positives (1,1). With ROC curve, we can observe the trend of True Positive rate vs False Positive rate.

Comparing these metrics helps us evaluate the performance of a models for the given application.
