<head>
  <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
  <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
      tex2jax: {
      skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
      inlineMath: [['$','$']]
      }
    });
  </script>
</head>


<div align="center"><img src="./cover1.png" width="800"></div>


- [What is Machine Learning?](#what-is-machine-learning)
- [Supervised learning 监督学习](#supervised-learning-监督学习)
  - [Linear regression model 线性回归模型](#linear-regression-model-线性回归模型)
    - [Cost function 代价函数](#cost-function-代价函数)
    - [Gradient descent 梯度下降](#gradient-descent-梯度下降)
      - [Learning rate choise](#learning-rate-choise)
      - [Kinds of gradient descent](#kinds-of-gradient-descent)
  - [Multiple linear regression](#multiple-linear-regression)
    - [Vectorization](#vectorization)
    - [The gradient descent in multiple linear regression](#the-gradient-descent-in-multiple-linear-regression)
    - [Feature Scaling](#feature-scaling)
    - [Checking if gradient descent is convergent](#checking-if-gradient-descent-is-convergent)
    - [How to choose learning rate](#how-to-choose-learning-rate)
  - [Polynomial regression](#polynomial-regression)
  - [Logistic regression](#logistic-regression)
    - [The model of logistic regression](#the-model-of-logistic-regression)
    - [Decision boundary](#decision-boundary)
    - [Cost function of logistic regression](#cost-function-of-logistic-regression)
    - [Gradient descent](#gradient-descent)



# What is Machine Learning?

The machine learning has two kinds of algorithms. One is **supervised learning**, one is **unsupervised  learning**.

- **supervised learning**
  1. Make regression:It has an input x then give an output y(the right answers also called data sets).
  2. Make classification: predict categories, like give a diagnos of breast cancer(benign or malignant).

- **unsupervised learning**
  Data only comes with inputs x, but not outputs y. The algorithm has to find the some structure through the data. 

# Supervised learning 监督学习

## Linear regression model 线性回归模型

 <div align="center"><img src="./Mpic/m1.png" width="400"></div>

 Definitions:
 1. training set: the data we give to train the model
 2. x: inpute variable
 3. y: output variable
 4. m: number of training examples
 5. f(model): the function 
 6. $\widehat{y}$ :the predicted value
 7. linear regressing with one variable[univariate linear regression]: like the line in the picture

### Cost function 代价函数

Definitions:
1. error: equals to $\widehat{y}^i-y^i$
2. cost function: It is used to show how closely the function $f$ fits the real value. It equals to 
   
   $$J=\frac{1}{2m}\sum_{i=1}^m(\widehat{y}^i-y^i)^2$$

We can use contour plots to see the J curve directly like the picture below.

 <div align="center"><img src="./Mpic/m2.png" width="400"></div>

### Gradient descent 梯度下降

 <div align="center"><img src="./Mpic/m3.png" width="400"></div>

 This picture shows how gradient descent works to find the local minima. That is:
 1. choose a starting point
 2. look around to see the steep way to take the fasted step
 3. repeat the steps above

**The gradient descent algorithm**

We have to repeat these two algorithms until convergence.

$$w=w-\alpha\frac{\partial}{\partial w}J(w,b)$$

$$b=b-\alpha\frac{\partial}{\partial b}J(w,b)$$

 <div align="center"><img src="./Mpic/m4.png" width="400"></div>

Here $\alpha$ is **learning rate**. It's a value between 0 and 1. It controls how big step we will make each time.

About the partial derivative part. This is how it works if we assume b=0 and there is just one parameter w.

 <div align="center"><img src="./Mpic/m5.png" width="400"></div>

  <div align="center"><img src="./Mpic/m7.png" width="400"></div>


#### Learning rate choise

If $\alpha$ is too small, the gradient descent will be very slow. But if $\alpha$ is too big, it will never get to the minimum and it's fail to converge.

 <div align="center"><img src="./Mpic/m6.png" width="200"></div>

#### Kinds of gradient descent

1. Batch gradient descent 批量梯度下降 :
   Each step of gradient descent uses all the training samples.

## Multiple linear regression

 <div align="center"><img src="./Mpic/m8.png" width="500"></div>

$$f_{\bar{w},b}(\bar{x})=\bar{w}\cdot \bar{x}+b =w_1x_1+w_2x_2+\cdots+b$$


### Vectorization

We can short our code by victorization. We can use a tool called numpy. Here is the example.

    w = np.array([1,2,3,4])
    b = 4
    x = np.array([10,20,30,30])
    f = np.dot(w,x) + b

### The gradient descent in multiple linear regression

 <div align="center"><img src="./Mpic/m9.png" width="500"></div>

**Normal equation**: An alternative for gradient descent. It's for linear regression and may become slow if the n is too big. 

### Feature Scaling

Feature scaling is aimed at helping fasting the process of gradient descent. Because some ranges of features are too large and some are too small. We should normalize them.

 <div align="center"><img src="./Mpic/m10.png" width="300"></div>

We have three ways to normalize the features:
1. the regular one
    <div align="center"><img src="./Mpic/m11.png" width="300"></div>

2. mean normalization
    <div align="center"><img src="./Mpic/m12.png" width="300"></div>

$\mu$ here is the average value of the feature.

3. Z-score normalization

 <div align="center"><img src="./Mpic/m13.png" width="400"></div>

here standard deviation is 标准差

### Checking if gradient descent is convergent

<div align="center"><img src="./Mpic/m14.png" width="400"></div>

We can draw this learning curve to check its convergence. The cost function should decrease after each iteration. If not, you should check your learning rate $\alpha$ to see if it's too big.

<div align="center"><img src="./Mpic/m15.png" width="300"></div>

This method is not very depensible.

### How to choose learning rate

<div align="center"><img src="./Mpic/m16.png" width="500"></div>

To check if there is a bug, we can use a very small learning rate to see if the cost function is decreasing. If not, there's a bug.

## Polynomial regression

It's like $y=w_0+w_1x+w_2x^2\cdots$ and in this case, feature scaling becomes more important.

## Logistic regression

positive class: The set you want and need to output.

negative class: The set you don't want and no need to do output.

### The model of logistic regression

<div align="center"><img src="./Mpic/m17.png" width="500"></div>

$$f(\bar{x})=P(y=1|\bar{x};\bar{w},b)$$

Means under the input x, the model think the possibility is 1 and it's under the influence of w and b.

### Decision boundary

The decision boundary is the curve when z=0. It can divide the positive and negative class.

<div align="center"><img src="./Mpic/m18.png" width="200"></div>

### Cost function of logistic regression

**The loss function:**

<div align="center"><img src="./Mpic/m19.png" width="500"></div>

When $\widehat{y} = 1$ :

<div align="center"><img src="./Mpic/m20.png" width="500"></div>

When $\widehat{y} = 0$ :

<div align="center"><img src="./Mpic/m21.png" width="500"></div>

**The cost function:**

$$J = \frac{1}{m} \sum_{i=1}^m L(f(x^{i}),\widehat{y}^i)$$

**Simplified cost function:**

The two loss functions are the same actually:

<div align="center"><img src="./Mpic/m22.png" width="500"></div>

Then the cost function will turn into:

$$J = \frac{1}{m}\sum_{i=1}^m -y^i \log f(x^i)-(1-y^i)\log(1-f(x^i))$$

### Gradient descent

<div align="center"><img src="./Mpic/m23.png" width="400"></div>

