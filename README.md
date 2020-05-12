# ml
Machine Learnng - Group Assignments 1, 2, 3:

Group Assignment 1: 
Predicting Wine Quality with k-Nearest Neighbours
Instructions: This exercise should be done using Python. The source codes as well as all relevant
outputs should be included in the submission, as well as brief explanations of the code as well as
what you see.
Use the file “sparklingwine.csv”.
Build a k-Nearest Neighbours classifier in Python for “sparklingwine.csv” that:
1. loads the data file;
2. construct a new binary column “good wine” that indicates whether the wine is good
(which we define as having a quality of 6 or higher) or not;
3. splits the data set into a training data set (first 400 samples), a validation data set (next
200 samples) and a test data set (last 200 samples) — please do not shuffle the data,
as it is already shuffled;
4. normalises the data according to the Z-score transform;
5. loads and trains the k-Nearest Neighbours classifiers for k = 1,2, …,100;
6. evaluates each classifier using the validation data set and selects the best classifier;
7. predicts the generalisation error using the test data set.
How do you judge whether the classifier is well-suited for the data set?

Group Assignment 2: 
In this exercise, we try to predict defaults in student loan applications. To this end:
1. Load the data set loandata.csv into Python.
2. The data set contains some categorical predictors. Sklearn, which you should use
for this exercise, can only handle numerical predictors. Translate the categorical predictors
into numerical predictors. (You may want to look into the pandas function
get dummies.)
3. Shuffle the data set and split it into 50% training data, 25% validation data and 25%
test data.
4. Calculate the accuracy of the naiive benchmark (majority predictor) on the validation
set.
5. Train a decision tree using the default settings, and calculate the accuracy of this tree
on the training and the validation set. What do you think of this classifier?
6. Retry the previous step using different maximum depths for the tree. (Look at the
max depth parameter.) Plot the accuracy on the training data as well as on the
validation data as a function of the tree depth.
7. Choose the most appropriate tree depth and justify your choice. What do you think
of this classifier?
8. Retrain the best classifier using all the samples from both the training and the validation
set. Estimate the out-of-sample accuracy of this classifier on the test set. Discuss
what you observe.
9. Retrain the best classifier on all samples (including the test set) and describe the tree
that you obtain (e.g. via visualisation, or via textual description).

Group Assignment 3:
For this group assignment, download the SMS Spam Collection data set from
https://archive.ics.uci.edu/ml/machine-learning-databases/00228/
and follow the steps below to build a Naiive Bayes spam filter.
1. Load the data into a Python data frame.
2. Pre-process the SMS messages: Remove all punctuation and numbers from the SMS
messages, and change all messages to lower case (Please provide the Python code that
achieves this).
3. Shuffle the messages and split them into a training set (2,500 messages), a validation
set (1,000 messages) and a test set (all remaining messages).
4. While Python's SciKit-Learn library has a Naiive Bayes classifier, it works with continuous
probability distributions and assumes numerical features. Although it is possible
to transform categorical variables into numerical features using a binary encoding, we
will instead build a simple Naiive Bayes classifier from scratch.
5. Explain the code: What is the purpose of each function? What do 'train' and `train2'
do, and what is the difference between them? Where in the code is Bayes' Theorem
being applied?
6. Use your training set to train the classifiers `train' and `train2'. Note that the interfaces
of our classifiers require you to pass the ham and spam messages separately.
7. Using the validation set, explore how each of the two classifiers performs out of sample.
8. Why is the `train2' classifier faster? Why does it yield a better accuracy both on the
training and the validation set?
9. How many false positives (ham messages classified as spam messages) did you get
in your validation set? How would you change the code to reduce false positives at
the expense of possibly having more false negatives (spam messages classified as ham
messages)?
10. Run the `train2' classifier on the test set and report its performance using a confusion
matrix.
Hint: In the lecture we have discussed the formula for the Naive Bayes algorithm. 
While mathematically correct, the formula cannot be used `as is' in an implementation since the product of many probabilities 
leads to a very small number that causes numerical issues. Hence, the code above conducts a normalisation after each multiplication.
