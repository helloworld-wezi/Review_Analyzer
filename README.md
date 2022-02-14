# Review Analyzer
The goal of this project is to design a classifier to use for sentiment analysis of product reviews.

## Training Set

The training set consists of reviews written by Amazon customers for various food products. The reviews, originally given on a 5 point scale, have been adjusted to a +1 or -1 scale, representing a positive or negative review, respectively.

Example:
![image](https://user-images.githubusercontent.com/87055709/153831205-672bce95-5411-46d0-961c-fe4a95b9e6a6.png)

## Complete Setup
Python 3.6 is used in this project. The complete setup is as follows:
1. The algorithms used are:
    1. Perceptron Algorithm
    2. Average Perceptron Algorithm
    3. Pegasos Algorithm
2. The review texts will be converted into feature vectors using a bag of words approach. For example, in a unigram model with dictionary set {Mary, loves, apples, red}, the sentences "Mary loves apples" and "Red apples" is converted into vectors (1, 1, 1, 0) and (0, 0, 1, 1) respectively. In the bigram case, using the dictionary set {Mary loves, loves apples, Red apples}, the sentences will be converted into vectors (1, 1, 0) and (0, 0, 1) respectively.
3. The goals of the project are to:
    1. Find the best hyperparameter for T (the number of times the feature vector is updated) and Lambda (the weight of the regularization term to avoid overfitting),
    2. Compare the performance and observe the convergence of the algorithms,
    3. Finding the most impactful words in predicting the positive labels, and
    4. Compare the performance of the method of generating feature vectors

## Conclusions
The conclusions are as follows:
1. The validation accuracies of the algorithms:
    1. Perceptron: 71.60%
    2. Average Perceptron: 79.80%
    3. Pegasos: 79.00%
2. Using the average perceptron algorithm, the test accuracy is 80.20%.
3. In finding the best hyperparameter of T (the number of times the feature vector is updated) using the values {1, 5, 10, 15, 25, 50} for each algorithm, it can be concluded that all algorithms perform the best using T = 25. In the same way, the algorithms also perform the best using Lambda = 0.01 (the weight of the regularization term to avoid overfitting).
4. The perceptron algorithm does not converge, meanwhile both average perceptron and pegasos algorithm converges. This is due to the nature of the perceptron algorithm, which will never converge is the data is not linearly separable.
5. The most impactful words in predicting the positive labels are:
    1. delicious
    2. great
    3. !
    4. best
    5. perfect
    6. loves
    7. wonderful
    8. glad
    9. love
    10. quickly
 6. By using the stop words (such as: i, me, my, myself, etc) the accuracy on the test set can be improved to 80.80%. However, changing the method of generating feature vector from binary features to count features decrease the accuracy on the test set to 77.00%.
