# Beginners introduction to supervised machine learning
This course provides a short introduction to supervised machine learning. It covers:

- What is machine learning?
  - Including how supervised and unsupervised methods differ
- An introduction to supervised learning: linear regression and logistic regression

The course consists of two lectures and a number of problem sets.

## Lectures

The lectures are:

* AM: [An introduction to supervised machine learning methods](https://htmlpreview.github.io/?https://github.com/ben18785/introduction_to_supervised_ml/blob/main/presentations/intro_to_supervised_ml.html). This covers:
  * What is meant by machine learning?
  * Linear regression
  * How supervised machine learning models are trained?
  * Over- and under-fit models and validation / testing sets
* PM: [An introduction to logistic regression]

## Problem sets

There is an introductory problem set which is recommended for all newbies to machine learning:
- [using linear regression to predict house prices](https://htmlpreview.github.io/?https://github.com/ben18785/introduction_to_ml/blob/main/problem_sets/s_applied_regression.nb.html). Here participants apply linear regression modelling and investigate how the model complexity affects its performance on training, validation and testing sets. The dataset used in the problem set is [here](./problem_sets/data/housing_short.csv). The answers to this exercise are in both [R](https://htmlpreview.github.io/?https://github.com/ben18785/introduction_to_ml/blob/main/problem_sets/answers/s_applied_regression.nb.html) and [Python](https://github.com/ben18785/introduction_to_ml/blob/main/problem_sets/answers/s_applied_regression.ipynb).

There is also an additional problem set which encourages participants to code up a linear regression machine learning algorithm:

- [*Linear regression*](https://htmlpreview.github.io/?https://github.com/ben18785/introduction_to_ml/blob/main/problem_sets/s_linear_regression_problems.nb.html). Here, participants train their own linear regression model and investigate how the hyperparameters of gradient descent affect training efficiency. The answers to this problem set are [here](https://htmlpreview.github.io/?https://github.com/ben18785/introduction_to_ml/blob/main/problem_sets/answers/s_linear_regression_problems_answers.nb.html).


## How to learn more?

All available on Oxford library SOLO:

- "The hundred-page machine learning book", Burkov
- "Hands-On machine learning with Scikit-Learn & Tensorflow", Geron

Coursera:

- [Data Science: Statistics and Machine Learning Specialization, Johns Hopkins](https://www.coursera.org/specializations/data-science-statistics-machine-learning)

## Notes to self for next time I deliver

Reduce the material:

- include levels 1-2 for the "what is ML?" section
- focus only on supervised ML using linear regression and logistic regression

When I gave this course, I actually deviated from the lecture and drew on the screen using Jamboard. In this I had a series of examples:

linear regression:
- house price vs size; how to build a linear model for this; what do the parameters of the linear model mean
- how do we choose the parameters of the linear model? start off with least-squares loss
- how does changing the loss function (e.g. absolute vs 4th power vs square) affect the estimates?
- how do we actually estimate those parameters? For least squares we can estimate the parameters exactly (I don't show this); for other cases, it's generally better to use gradient descent
- explain gradient descent using a 1d graph of the loss function for one of the parameters; talk through why dL/dtheta <0 means that we step in the right direction
- talk about how we can make the model more complex by adding a quadratic term to the regression and show how this results in a curvy line that (may) better fit the data; explain that we can estimate this model via gradient descent
- model complexity: show underfit, fit and overfit models achieved by whatever cap we have on the number of polynomial terms
- training (~70%) / validation (~30%) split: explain that we choose a model of appropriate complexity by training on one set and testing on the validation; as part of this, I plot the loss vs model complexity for both the training and validation sets
- testing set: to avoid overfitting to the training set, we create another set ("testing" ~10%)

logistic regression:
- explain that it's a classifier
- lung cancer vs smoking example: plot lung cancer presence / absence vs number of cigarettes smoked; just some raw data
- explain how we can think about this presence or absence as like flipping a coin
- overlay a logistic-type on top of the data; explain how it's like flipping a coin with different biases according to the number of cigarettes smoked
- show the logistic equation and explain its shape
- ask the question: how do we estimate its parameters?
- back to coin flipping: write down and explain the Bernoulli distribution
- show that for two coin flips -- one heads, one tails -- how we could estimate the value of theta? Show this graphically as peaking at theta=0.5 (can also show by differentiation afterwards)
- now write down the likelihood for the logistic glm and explain that we estimate it using gradient descent; as we do for linear regression
- explain interpretation of logistic regression as a log odds of lung cancer
- show how we can increase model complexity by including a quadratic term and say that all the same things about overfitting etc still apply to logistic regression 
