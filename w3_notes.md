# **Week 3: Machine Learning with Andrew Ng**

## Classification and Representation
### **Classification**
- To attempt classification, one method is to use `linear regression` and map all predictions greater than 0.5 as a 1 and all less than 0.5 as a 0. However, this method doesn't work well because classification is not actually a linear function.

- The classification problem is just like the regression problem, except that the values we now want to predict take on only a `small number of discrete values`.

### **Hypothesis Representation**
- Instead of using linear regression, we can use a the `Sigmoid Function` or `Logistic Function`
- The `Sigmoid Function` looks like the below:

  ![graph](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/1WFqZHntEead-BJkoDOYOw_2413fbec8ff9fa1f19aaf78265b8a33b_Logistic_function.png?expiry=1533340800000&hmac=5Z9Z2I9MSgR8eeYE_Yz88MXavJJVnBJnZ9NBIiQmGnQ)

- The function g(z), shown here, maps any real number to the (0, 1) interval, making it useful for transforming an arbitrary-valued function into a function better suited for classification.
- `h(x)` will give us the probability that our output is 1.

### **Decision Boundary**
- The **decision boundary** is the line that separates the area where y = 0 and where y = 1. It is created by our hypothesis function.

## Logistic Regression Model
### **Cost Function**
- When y = 1, we get the following plot for `J(θ)` vs `h(x)`:

  ![image](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/Q9sX8nnxEeamDApmnD43Fw_1cb67ecfac77b134606532f5caf98ee4_Logistic_regression_cost_function_positive_class.png?expiry=1533340800000&hmac=FEJsQ2II49QzCvftUIZaiB1qjP4G7f2wqaKL7hrnIxY)

- When y = 0, we get the following plot for `J(θ)` vs `h(x)`:

  ![image](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/Ut7vvXnxEead-BJkoDOYOw_f719f2858d78dd66d80c5ec0d8e6b3fa_Logistic_regression_cost_function_negative_class.png?expiry=1533340800000&hmac=4Vl9kep1i6wtZriiO53Rb1lOESogXxdbVDDM0SqPqRE)

- If our correct answer 'y' is 0, then the cost function will be 0 if our hypothesis function also outputs 0. If our hypothesis approaches 1, then the cost function will approach infinity.
- If our correct answer 'y' is 1, then the cost function will be 0 if our hypothesis function outputs 1. If our hypothesis approaches 0, then the cost function will approach infinity.

### **Simplified Cost Function and Gradient Descent**
- Refer to notes from lecture

### **Advanced Optimization**
- "`Conjugate gradient`", "`BFGS`", and "`L-BFGS`" are more sophisticated, faster ways to optimize θ that can be used instead of gradient descent. We suggest that you should not write these more sophisticated algorithms yourself (unless you are an expert in numerical computing) but use the libraries instead, as they're already tested and highly optimized.
- Refer to lecture notes for octave implementation of the advance optimization using `function "fminunc()"`

## Multiclass Classification
### **One-vs-All**
- Now we will approach the classification of data when we have more than two categories. Instead of y = {0,1} we will expand our definition so that `y = {0,1...n}`.
- Since y = {0,1...n}, we divide our problem into `n+1` (+1 because the index starts at 0) binary classification problems; in each one, we **predict the probability that 'y' is a member of one of our classes**.
- We are basically choosing one class and then lumping all the others into a single second class. We do this repeatedly, applying binary logistic regression to each case, and then **use the hypothesis that returned the highest value as our prediction**.
- The following image shows how one could classify **3 classes**:

  ![image](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/cqmPjanSEeawbAp5ByfpEg_299fcfbd527b6b5a7440825628339c54_Screenshot-2016-11-13-10.52.29.png?expiry=1533340800000&hmac=MOvZ9_XCsdTR2kT5WP9I3M7GpJPB3OBrkzvnF2c4DDA)
- Train a logistic regression classifier `hθ(x)` for each class￼ to predict the probability that `￼y = i￼`￼.
- To make a prediction on a new x, pick the class ￼that maximizes `hθ(x)`