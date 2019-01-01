# **Week 2: Machine Learning with Andrew Ng**

## Multivariate Linear Regression
### **Multiple features**
Linear regression with multiple variables is also known as "multivariate linear regression".

In order to develop intuition about this function, we can think about `theta_0` as the basic price of a house, `theta_1` as the price per square meter, `theta_2` as the price per floor, etc. `x_1` will be the number of square meters in the house, `x_2` the number of floors, etc.

### **Gradient Descent for Multiple Variables**
The gradient descent equation itself is generally the same form; we just have to repeat it for our '`n`' features.

See image below for illustration:

![slide](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/MYm8uqafEeaZoQ7hPZtKqg_c974c2e2953662e9578b38c7b04591ed_Screenshot-2016-11-09-09.07.04.png?expiry=1533254400000&hmac=4VeWyD8Kh86mdBbLIKkYpRPEjcyoSWJ7QUc3NM6xTbk)

### **Feature Scaling**
We can speed up gradient descent by having each of our input values in roughly the same range. This is because `θ` will descend quickly on small ranges and slowly on large ranges, and so will oscillate inefficiently down to the optimum when the variables are very uneven.

**Two techniques** to help with this are: 
- `Feature scaling`
  - Feature scaling involves dividing the input values by the range (i.e. the maximum value minus the minimum value) of the input variable, resulting in a new range of just 1. 
- `Mean normalization`
  - Mean normalization involves subtracting the average value for an input variable from the values for that input variable resulting in a new average value for the input variable of just zero.

  ### **Learning Rate**
  **Debugging gradient descent.**
  - Make a plot with number of iterations on the x-axis. Now plot the cost function, `J(θ)` over the number of iterations of gradient descent. If `J(θ)` ever increases, then you probably need to decrease `α`.

  **Automatic convergence test.**
  - Declare convergence if `J(θ)` decreases by less than E in one iteration, where E is some small value such as 10−3. However in practice it's difficult to choose this threshold value.

  See below for illustrations:

  ![slide_1](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/FEfS3aajEea3qApInhZCFg_6be025f7ad145eb0974b244a7f5b3f59_Screenshot-2016-11-09-09.35.59.png?expiry=1533254400000&hmac=nswlxrseWd7OYm1FbG306IrWLLNUHBf0CTSugNJu4Hs)

  ![slide_2](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/rC2jGKgvEeamBAoLccicqA_ec9e40a58588382f5b6df60637b69470_Screenshot-2016-11-11-08.55.21.png?expiry=1533254400000&hmac=RxgLozqPjfDe42EcX48onyxsVz7Qmbek_R2s-r28fB0)

  To summarize:
  - If `α` is too small: slow convergence.
  - If `α` is too large: ￼may not decrease on every iteration and thus may not converge.

  ### **Features and Polynomial Regression**
  We can improve our features and the form of our hypothesis function in a couple different ways.

  - We can combine multiple features into one. i.e. We can combine feature x1 and x2 into x3 where x3 = x1 * x2
  - Our hypothesis function need not be linear (a straight line) if that does not fit the data well. We can **change the behavior or curve** of our hypothesis function by making it a quadratic, cubic or square root function (or any other form).
    - If you choose your features this way then `feature scaling` becomes very important.

## Computing Parameters Analytically
### **Normal Equation**
- Gradient descent gives one way of minimizing J. Let’s discuss a second way of doing so, this time performing the minimization explicitly and without resorting to an iterative algorithm.
- In the "Normal Equation" method, we will minimize J by explicitly taking its derivatives with respect to the θj ’s, and setting them to zero. This allows us to find the optimum theta without iteration.

See below for illustration:

![slide](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/dykma6dwEea3qApInhZCFg_333df5f11086fee19c4fb81bc34d5125_Screenshot-2016-11-10-10.06.16.png?expiry=1533254400000&hmac=Ek0b7BC0CA8LlCPxieZFd5eddZ3vm5ZD8Dy__XgSWiw)

Note: There is **no need** to do feature scaling with the normal equation.

With the normal equation, computing the inversion has `complexity O(n^3)`. So if we have a very large number of features, the normal equation will be slow. In practice, when `n exceeds 10,000` it might be a good time to go from a normal solution to an iterative process.

## Octave/Matlab Tutorial
### **Basic Operations**

### **Moving Data Around**

### **Computing on Data**
- Setting matrix []
- Matrix multiplication A .* B
- Matrix Power A .^ 2
- Matrix division A ./ 2
- Log(v) or exp(v) or abs(v)
- v + ones(length(v),1) or v + 1
- Transpose matrix A'
- val = max(A) and [val, ind] = max(A)
- find(a<3)
- sum(a)
- prod(a) - multiplication of all items in a
- floor(a) or ceil(a)
- max(A, [], 1) - max for each column in a matrix
- max(A, [], 2) - max for each row in a matrix
- max(A(:)) - turn A into a vector and get the max
