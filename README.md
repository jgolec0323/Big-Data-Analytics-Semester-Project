# Big-Data-Analytics-Semester-Project
Semester Project for  Big Data Analytics at the University of Iowa

# Use Case 

## Data Understanding
Source: https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge

Columns:
- id: Column to represent the unique identifier for the user
- comment_text: String of data that represents the comment
- toxic: Binary label for the comment exhibiting toxic characteristics
- severe_toxic: Binary label for the comment exhibiting sever_toxic characteristics
- obscene: Binary label for the comment exhibiting obscene characteristics
- threat: Binary label for the comment exhibiting threat characteristics
- insult: Binary label for the comment exhibiting insult characteristics
- identity_hate: Binary labels for the comment exhibiting identity_hate characteristics

## Data Preprocessing

### Data Cleansing 

The first step, preprocessing, is mainly cleaning the data by removing any unnecessary and irrelevant words. To clean the data,
- Removed contractions (e.g. can’t to can not).
- Converted all words to lowercase
- Removed numbers, usernames, and IP addresses.
- Removed stop words (e.g. “and”, “or”, “the”, “that”, etc.)

### Feature Generation

TF-IDF (Term Frequency - Inverse Document Frequency)

The term frequency is the frequency of a word in each comment string. The Inverse data frequency is the weight of all words across all comments in the data (i.e. rare words have a high IDF score). Simply, TF-IDF values are associated with words with significance. This function allows the collection of comment strings to be transformed into a numeric vector.

## Modeling 

Multi-label classification:
The models were trained using the one-vs-rest strategy which trains an independent classifier for each toxic label. 

Models:
- Logistic Regression
- Linear Support Vector Classification
- Ridge Classifier
- Perceptron
- Stochastic Gradient Descent
- Passive Aggressive Classifier
- Naive Bayes (NB)

## Results & Discussion

In order to compare the results we used two quantitative metrics - ROC-AUC score and F1 score. 

The ROC-AUC score is the area under the Receiver Operating curve. The value of the ROC-AUC score can range from 0 to 1. In a perfect classifier, the ROC-AUC score is equivalent to 1. In a random classifier, the ROC-AUC score is equivalent to 0.5. The ROC-AUC curve is calculated by the true positive rate (sensitivity) vs false positive rate (1-specificity). This is calculated to show the trade-off between specificity and sensitivity. In an ideal model, a classifier will exhibit high sensitivity and specificity. 

The F1 score was also used for model evaluation and performance. The F1 score is the harmonic mean of precision and recall. Precision is the number of correctly classified positive instances out of the total number of instances classified as positive. Recall is the number of correctly classified positive instances out of total number of true positive instances.

