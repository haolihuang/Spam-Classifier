# Spam-Classifier

The code can be viewed in a Jupyter notebook or an html file.

## Overview
This is an assignment for Applied Text Mining in Python on Coursera.

How I built the spam classifier:
- Tokenized labeled text messages into word or character n-grams using Count Vectorizer or Tfidf Vectorizer.
  - Word 2-gram for **to be or not to be** would be: **to be, be or, or not, not to, to be**.
  - Caracter 5-gram for  **to_be_or_not_to_be** would be: **to_be, o_be_o, _be_or**, etc.
  - Count Vectorizer converts a collection of text to a matrix of token counts.
  - Tfidf Vectorizer converts a collection of text to a matrix of token tf-idf (term frequency-inverse document frequency), which reflects how important a word is to a document.
- Added extra features, such as number of characters per message, number of digits per message, and number of non-word characters (other than letter, digit, or underscore) per document. 
- Trained Naive Bayes, Support Vector Machine, and Logistic Regression classifiers to recognize spam messages.  

Because the classes are imbalanced, we used the area under ROC score as the metric to evaluate the models.

## Takeaways
The best model is a **Logistic Regression model**, and the data was tokenized into **character 2- to 5-grams** with the **Count Vectorizer**. All three additional features mentioned above were included. This model has a area under ROC score of **0.978**. This is much improved from **0.942**, obtained using a preliminary Naive Bayes model.

It is interesting to find that character n-grams works significantly better than word n-grams. This might have to do with spam emails containing a lot of non-standard spellings, perhaps in order to bypass the spam filtering systems. The non-standard spellings would be picked up more easily using character n-grams.
