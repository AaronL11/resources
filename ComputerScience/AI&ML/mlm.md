\newpage

# Machine Learning Models

## Regression Analysis

### Linear Regression

### K-Nearest Neighbors (KNN)

### Polynomial Regression

## Support Vector Machines (SVM)

### The "Kernel Trick"

### Linear SVM

### Non-Linear SVM

## Bayesian Networks

### Bayesian Linear Regression

### Markov Chain Monte Carlo

## Decision Trees

## Gradient Boosting

Gradient Boosting is an important technique in machine learning and data science.s

Boosting is essentially the act of creating a prediction model $F$ as a sum of $M$ weak learners $f_i$:
$$
F(x) = \sum^M_if_i(x)
$$
Rather than capturing all the dynamics of the data in each learner $f$, we use the mistakes of $f_i$ to train $f_{i+1}$ etc.

An example of a weak learner $f$ could be a simple linear regression or SVM.

The first thing we need to consider when gradient boosting is our loss function $L$ which takes our true value $y$ and a prediction $\hat{y}$:
$$
L(y,\hat{y})
$$
The only condition on $L$ is that it is differentiable. More specifically, the gradient must exist.

Then we start with a simple function $f_0(x)=\bar{y}$

Then we take the partial derivative with respect to $\hat{y}_i$
$$
\hat{r}_{0i} = -{\partial L\over\partial\hat{y}_i}\big|_{\hat{y}_i=F_0(x)}
$$
we must do this for all data points $i$. The reason the gradient is negative is to reflect gradient decent.

Next we learn a new model were the target variable is $\hat{r}_1$ and the same features $x$. This model we can call $f_2$
Then we need to figure out how much of the new learner to add. Which is the previous model plus a step in the loss

$$
\hat{\gamma}_2 = \sum^N_{i=1}L\big(y_i,f_1(x)+\gamma_2x_i)\big)
$$
This is called a **Line Search**. It looks for the correct amount of the new weak learner to add so far.
$$
F_{m+1}(x)=F_m(x)+\gamma_{m+1}f_{m+1}(x)
$$
And we repeat this until we are satisfied.
