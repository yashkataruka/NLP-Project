# NLP-Project

The title of the project is Sentiment Analysis of Tweets in Hindi

Introduction - In this work, we focus on mining sentiments and analyzing them for Hindi language. Hindi is the 4th commonly spoken language in the world. With the increase in the amount of information being communicated via regional languages like Hindi, comes a promising opportunity of mining this information. Mining sentiments in Hindi comes with their share of issues and challenges.

Motivation - In the rural areas, where population is more, people usually speak in their mother tongue which is Hindi. Some of the biggest news channels of India use Hindi as their primary language. In order to know whether a particular rural section of the society is having a positive, neutral or a negative mindset towards a particular topic can be tough. Hence, we are doing Sentiment Analysis in Hindi to find out if there's a sense of support or not behind that particular agenda without having to do it manually.

We have considered a dataset that contains approximately 10,000 tweets in Hindi and whether that tweet was positive, neutral or negative

Link: https://github.com/sid573/Hindi_Sentiment_Analysis/blob/master/hi_3500.ods

We are following 2 types of models here. First one is a basic and simple one while the 2nd one is more advanced.

First Model - 

We are reading the data. After reading the data which is in Open Document Spreadsheet format, we are cleaning off any English Alphabets, Links, email IDs, Numbers, Hashtags, Mentions, Double quotes & Single quotes.
Then we are using two vectorizers - CountVectorizer and TFIDFVectorizer.

Considering three basic models in the first pipeline - Multinomial Naive Bayes, Logistic Regression and Stochastic Gradient Descent.
All three models perform the same type of operations. The fit and transform the inital data which is the training data, which is 70% of the complete datatset. It trains itself to perform further operations. 
It then tranforms the test data that contains the input and provides us with an output that is an array equal to the size of test input. It then matches it output to the test output which was optaines while splitting the data and gives us the accuracy.

The accuracy has been found out to be around 75% for all the 3 models, using both CountVectorizer and TFIDFVectorizer.

Taking a sample input, cleaning it, transfornming it and predicitng the value seems to give us the correct output.

Second Model:

The second model is fastai's ULMFiT model. We have used the pretrained AWD_LSTM weights. The AWD_LSTM is a ULMFiT model that has been trained on English datasets. We have used the same model to extract features and classify the Hindi dataset.

The ULMFiT model works in two parts. First we prepare the data for the language model without the labels by splitting it in train and test sets in a 90:10 ratio. Then in the second part we prepare the data, this time with the labels, for the classifier with the train-test ratio as 70:30. Trainig the classifier requires the trained language model.

Finally, fine tuning is done to improve the accuracy further.

## Using our trained model

Download the export.pkl file from the link below (size was too big to upload here)

Link: https://drive.google.com/file/d/1rLaRoIzGGea4ttWnDd5KsIqOfbK5q6PA/view?usp=sharing

Import the fastai libraries

Run the following:

varname = load_learner("path to the export.pkl file")

The trained model will be stored in the varname object and can be used for classification.
