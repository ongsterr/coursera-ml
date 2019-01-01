# **Week 1: Machine Learning with Andrew Ng**

## Introduction
### **What is Machine Learning?**
Two definitions of Machine Learning are offered.

- Arthur Samuel described it as: 
  > "The field of study that gives computers the ability to learn without being explicitly programmed."
- Tom Mitchell provides a more modern definition:
  > "A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E."

Machine learning can be split into 2 broad categories:
- `Supervised Learning`
- `Unsupervised Learning`

### **Supervised Learning**
In `supervised learning`, we are given a data set and already know what our correct output should look like, having the idea that there is a relationship between the `input` and the `output`.

Supervised learning can be categorised into 2 broad categories:
- `Regression` problems
  - In a regression problem, we are trying to predict results within a continuous output, meaning that we are trying to map input variables to some continuous function.
- `Classification` problems
  - In a classification problem, we are instead trying to predict results in a discrete output. In other words, we are trying to map input variables into discrete categories.

### **Unsupervised Learning**
`Unsupervised learning` allows us to approach problems with little or no idea what our results should look like. We can derive `structure` from data where we don't necessarily know the effect of the variables.

Unsupervised learning can also be categorised into 2 broad categories:
- `Clustering`
  - Take a collection of 1,000,000 different genes, and find a way to automatically group these genes into groups that are somehow similar or related by different variables, such as lifespan, location, roles, and so on.
- `Non-clustering` - The Cocktail Party Algorithm

## Model and Cost Function
### **Model Representation**
To describe the `supervised learning` problem slightly more formally, our goal is, given a training set, to learn a function h : X → Y so that h(x) is a “good” predictor for the corresponding value of y.

When the target variable that we’re trying to predict is continuous, such as in our housing example, we call the learning problem a `regression problem`. When y can take on only a small number of discrete values (such as if, given the living area, we wanted to predict if a dwelling is a house or an apartment, say), we call it a `classification problem`.

### **Cost Function**
We can measure the accuracy of our hypothesis function by using a `cost function`. This takes an average difference (actually a fancier version of an average) of all the results of the hypothesis with inputs from x's and the actual output y's.

This function is otherwise called the "`Squared error function`", or "`Mean squared error`".

Cost function can have infinite number of parameters.
- If it has *only one parameter*, it can be visually presented with a quadratic graph, where the global minimum shows the ideal parameter for the hypothesis function.
- If it has *more than one parameter*, it can become more complicated to present visually, but the same concept applies with regards to finding the parameters that create a hypothesis function that best fit the training dataset.

## Parameter Learning
### **Gradient Descent**
- Imagine that we graph our hypothesis function based on its fields theta_0 and theta_1 (actually we are graphing the cost function as a function of the parameter estimates).

- We put theta_0 on the x axis and theta_1 on the y axis, with the cost function on the vertical z axis. The points on our graph will be the result of the cost function using our hypothesis with those specific theta parameters.

- We will know that we have succeeded when our cost function is at the very bottom of the pits in our graph, i.e. when its value is the minimum.

## Linear Algebra
### **Matrices and Vectors**
- Addition and Scalar Multiplication
- Matrix Vector Multiplication
- Matrix Matrix Multiplication
- Matrix Multiplication Properties
  - Identity Matrix
  - Associative Properties
  - Communicative Properties
- Matrix Inverse and Transpose