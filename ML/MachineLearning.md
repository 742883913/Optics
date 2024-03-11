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

## What is Machine Learning?

The machine learning has two kinds of algorithms. One is **supervised learning**, one is **unsupervised  learning**.

- **supervised learning**
  1. Make regression:It has an input x then give an output y(the right answers also called data sets).
  2. Make classification: predict categories, like give a diagnos of breast cancer(benign or malignant).

- **unsupervised learning**
  Data only comes with inputs x, but not outputs y. The algorithm has to find the some structure through the data. 

## Supervised learning

### Linear regression model

 <div align="center"><img src="./Mpic/m1.png" width="400"></div>

 Definitions:
 1. training set: the data we give to train the model
 2. x: inpute variable
 3. y: output variable
 4. m: number of training examples
 5. f(model): the function 
 6. $\widehat{y}$ :the predicted value
 7. linear regressing with one variable[univariate linear regression]: like the line in the picture

## Cost function

Definitions:
1. error: equals to $\widehat{y}^i-y^i$
2. cost function: equals to 
   $$J=\frac{1}{2m}\sum_{i=1}^m(\widehat{y}^i-y^i)^2$$